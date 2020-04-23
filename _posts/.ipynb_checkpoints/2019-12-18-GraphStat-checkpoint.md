---
layout: post
title:  "Structure and Models of Networks"
description:
date:   2019-12-19
tags: [graph]
category: graph
tagline: 
---
# Real World's graph property
- power law: log-log plot of degree distribution is linear. skewed degree distribution
- resilience: randomly remove nodes don't usually mess up with connectivity (won't split graph into 2)
- community structure:
	- usually most nodes are within a few reach
	- methods: spectral clustering, Hierachial clustering, combinatorial algorithm(min cut style), block model, diffusion method
- spectral property: skewed eigenvalue ~ powerlaw. Can embed graph in low dimensional space
- evolving properties: as time went by,
    - constant average degree
	- densification: $ E(t) \propto N(t)^{a}$ where $E(t)$ is number of edge at time $t$, $N(t)$ is number of node at time $t$. $a$ must fall in interval $1<a<2$ which means the growth of edge is faster than nodes, leading to denser graph
	- smaller diameter as time goes by

# Graph models
To have the null distribution of real world graph, crazy math people has a bunch of ways to generate synthetic models that can mimic the behaviour of real-world graphs. Each types of model have their advantage and disadvantages. Some are mathematically easy to estimate but don't mimic real world graphs, others are mathematically ugly and computationally expensive to calculate while fits the real graphs well.

|                     | Erdos Renyi Random Graph                                      | Exponential Random graph                           | Small world model                                      | Preferential attachment                                                                           | edge copying model                                                                                              | community guided attachment                                                            | Forest Fire Model                                                         | Kronecker graph                                                           |
|---------------------|---------------------------------------------------------------|----------------------------------------------------|--------------------------------------------------------|---------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------|---------------------------------------------------------------------------|---------------------------------------------------------------------------|
| how is it generated | Each node is connected to other nodes with equal distribution | probability distribution based on graph properties | start from low dimensional lattice and randomly rewire | "richer get richer". when we have a new node, add edges to nodes that already have a ton of edges | add a node and choose k edges to add. Sometimes add to k random nodes, othertimes copy all edges from one node. | Assume we know community structure. attach more within community, less cross-community | randomly following some ambassador nodes' edge to other node, recursively | copying the graph itself by some matrix operation of adjacency matrix     |
| degree distribution | binomial(choose k nodes from N-1 nodes) ~ Poission            |                                                    | don't fit powerlaw                                     | power-law, but nodes have constant out degree.                                                    | power-law                                                                                                       | power-law                                                                              | power-law                                                                 | power-law                                                                 |
| math                | a lot of good property                                        |                                                    |                                                        | need to know every node have how many edge --> expensive                                          |                                                                                                                 | but we don't explicitly know community structure                                       | picking optimal forward and backward probability is not easy (narrow)     | expensive to do parameter estimation. But there are ways to deal with it. |
| transivity          |                                                               | X                                                  | O                                                      |                                                                                                   |                                                                                                                 |                                                                                        |                                                                           | fits very well                                                            |
| community           |                                                               |                                                    |                                                        | -                                                                                                 | +                                                                                                               |                                                                                        |                                                                           |                                                                           |
| densification       |                                                               |                                                    |                                                        |                                                                                                   | -                                                                                                               | +                                                                                      | +                                                                         | +                                                                         |
| shrinking diameter  |                                                               |                                                    |                                                        |                                                                                                   |                                                                                                                 | +                                                                                      | +                                                                         | +                                                                         |

# Fitting Model: 
- Maximum likelihood estimation: Given graph $G$, change $\theta$ which is the probability matrix of the Krochecker graph, so that $P(G|\theta)$ is maximized.
    - $\theta$ here is that matrix that we use to do the kronecker product. What number should we put into those grids?
	- likelihood: say we start with some random number and do kronecker product several times until we fit the size of $G$. Then based on $G$'s adjacency matrix (binary) and the kronecker matrix, we just multiply all probabilities of potential edges to calculate likelihood.
	    - $G$'s adjacency matrix is $\big(\begin{smallmatrix} 1 & 0\\ 1 & 1 \end{smallmatrix}\big)$
		- The kronecker is $\big(\begin{smallmatrix} 0.8 & 0.2\\ 0.6 & 0.9 \end{smallmatrix}\big)$ describe how likely each edge exist
		- likelihood is $ 0.8 * 0.8 * 0.6 * 0.9 $
	- do some math and get the gradient of the likelihood. and let's do gradient descent.
- Challenges:
    1. How do I know which node is which node:
	    - calculate all permutation takes $O(N!)$, too expensive!
		- Just sample some of them (metropolis sampleing)
	2. Calculate likelihood takes $O(E)~O(N^2)$ time. too expensive!
	    - start from emtpy graph. They have some magic formula to correct for the true likelihood. (please see ref 1)
- Do gradient descent converge?
Yes! Though non-convex most of the time it works well so don't worry. 
# Reference
1. [Tools for large graph mining](https://cs.stanford.edu/people/jure/talks/www08tutorial/)
2. [Random Graph Model of Social Network](https://www.pnas.org/content/99/suppl_1/2566)
3. [Densification Power Law](https://www.cs.cornell.edu/home/kleinber/kdd05-time.pdf)
4. [Network Densification](https://arxiv.org/abs/physics/0603229)
5. [Transivity](https://transportgeography.org/?page_id=6171)
6. [Exponential random graph](https://sci-hub.tw/10.1016/j.socnet.2006.08.002)
7. [Kronecker graph](https://cs.stanford.edu/people/jure/pubs/kronecker-jmlr10.pdf)
8. [Kronecker graph](https://www-cs.stanford.edu/~jure/pubs/kronFit-icml07.pdf)