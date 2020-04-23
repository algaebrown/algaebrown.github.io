---
layout: post
title:  "Max Flow Algorithm"
description:
date:   2019-11-12
tags: [algorithm]
category: 
tagline: 
---

# Definition of the graph
1. A **directed** graph $G(V,E)$, edge can written as $(u,v)$ which means this edge is from vertex $u$ to $v$.
2. Source node $s$ and terminal node $t$.
- $s$ has no incoming edge
- $t$ has no outgoing edge
3. **capacity** $C$ for each edge is denoted as $C_{u,v}$

# Rule of flow
4. **flow** $f_{u,v}$ is a *non-negative* value to each edge, such that $0< f_{u,v} < C_{u,v}$. Flow cannot exceed capacity!
5. **Conservation**: for all nodes, all incoming flow must be equal to outgoing flow.

# Define the max flow problem:

Given Graph with capacity, return maximal flow.

## idea 0: we can start from flow = 0.

## idea 1: augemented path

find any path from $s$ to $t$, along the path find minimal capacity, increase the flow by that number

## idea 2: to continue augumenting, create a new network with deducted flow: residual graph

if the deducted flow < 0, remove the edge.

## idea 3: what if the first selected path is not the best: adding edge to allow reversal (undo flow): full residual graph

the residual graph now has two kind of edges:

1. **forward edges**: with the deducted capacity
2. **backward edges**: sending back the flow that is already created.

## idea 4: instead of finding an augumented path in the original graph, we do it in the residual graph.

Why would it work?
- when we add new flow in forward edge, we add more flow to that original edge
- when we add new flow in backward edges, we substract flow to that original edge.
Now check conservation

## idea 5: terminate when we cannot find a path from s to t.

that means we have no way to augument flow, and we've reached max flow.

# Cut

seperate $V$ into **disjoint set** $A, B$ such that $s \in A$, $t \in B$.

## defining capacity in a "cut"

sum of all capacity of edges that bridges nodes in A to B. (but not the way back).

Formally:

$\sum_{u, v, u \in A, v \in B} C_{u,v}$


### Intuition about a cut
1. different cut has different capacity.
2. the cut capacity limits the maximum flow from s to t, since they are the only ways to get there.

'''
Theorem: max flow <= min {cut capacity}
'''

Does the most parsimonious cut $min {all cut's capacity} = max flow$??

## cut in residual graph

We define this cut that all nodes in $A$ must be **reachable by $s$**. Put the rest of the node in $B = V-A$.

In the termination stage, since there exist not path from $s$ to $t$, the flow from A to B is 0.

## flow f in a cut

for $u \in A, v \in B$,

f = $\sum f_{u,v} - \sum{v,u}$ = flow A to B - flow B to A. is the net flow from s to t.

When we reach max flow, sum of all flow from A to be = sum of all capacity

