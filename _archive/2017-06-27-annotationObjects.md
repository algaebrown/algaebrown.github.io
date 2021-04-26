---
layout: post
title:  "Coalescent Theory with selection"
description: "Coalescent Theory assumes neutrality. So if the statistics deviate from it..."
date:   2021-03-17
tags: []
category: genetics
tagline: 
---

# Expected number of heterozygous sites in the SNP matrix? Waterson's estimate of $\theta$

Denote $S$ as total number of mutation. We simulate for $n$ individuals. Assume total population is $2N$.

Mutation is put onto the branch, with respect to the branch length and mutation rate $\mu$.

$E(S) = \mu \times E(L)$ where $L$ denotes sum of all branch length.

$E(L) = \sum_{k=2}^{n} k \times E(t_{k})$ where $t_{k}$ is the time for $k$ individuals to coalesce to $k-1$. We have described $t_{k} \sim Geom(p = \frac{2N}{k \choose 2}$ and therefore $E(t_{k}) = \frac{k \choose 2}{2N}$

$E(L) = \sum_{k=2}^{n} k \frac{k \choose 2}{2N} = 4N \sum_{k=2}^{n} \frac{1}{k-1} \approx 4N(ln(n) + \gamma)$. [Harmonic series](https://en.wikipedia.org/wiki/Harmonic_series_(mathematics)); $\gamma$ is Euler constant.

$E(S) = \mu 4N(ln(n) + \gamma) = \theta (ln(n) + \gamma)$

This simulation assume neutrality. No ancestor genotype is preferentially chosen. From the above formula, we can estimate $\theta$ from data where $\theta = \frac{S}{ln(n) + \gamma} ~ \theta = \frac{S}{ln(n)}$. This is the Waterson estimate of theta.

# Making a test for neutrality
Suppose we collected data from a population of crocodile, and created a SNP matrix where there are 10 rows, 55 columns (55 mutations). In this matrix, it happens to have 5 rows that are identical. Is this population under selection?

We can then simulate many population using coalescent theory many many times. We estimate mutation rate from data $\theta = \frac{S}{ln(n) + \gamma}$. The simulation result becomes our null distribution. We can see how many idential rows there are in simulated data. if $5$ idential row is rare;y seen in null, maybe this is a hint that this population of crocodile departs from neutrality.

# When population grow exponentially
When the population starts expanding exponentially at time $T_{k}$, more individuals coalesce into 1 ancestor. The shape of the tree diverges from the neutral coalescent tree.

# Formulating selection in coalescent theory
Here we define selection coefficient $s$. An ancestor is more likely selected by its descendants by $(1+s)$.

# Taijima's Estimate of $\theta$.

Denote the expected hamming distance (heterozygosity) between row $i,j$ in the SNP matrix as $k = E(\pi_{ij})$.

Recall how we simulate individuals. The two individuals colaesce into a common ancestor, and then we drop mutation based on the time it takes.

For 2 individual to select the same ancestor from $2N$ of them, the probability is $\frac{1}{2N}$. We expect the time needed to be $2N$, by parameterzing $p=\frac{1}{2N}$ for the geometric distribution. Based on branch length $2N$, we drop mutations on it. The expected number of mutation per branch is $2N \mu$. The individuals are apart from 2 branches, thus the expected mutation that sets them apart (that is the hamming distance, or heterozygosity) is $2N\mu + 2N\mu = 4N\mu = theta$. This is the Tajima's estimate of 
theta.

To estimate theta, we use every pair of row $i,j$ and take the average heterozygosity as the estimation. $k = E(\pi_{ij}) = \frac{\sum_{i,j} \pi_{ij}}{n \choose 2}$.

# Comparing the two types of estimate gives us some hint about selection.

If the population is neutrally evolving, then Watterson's estimate $\theta_{w} = \frac{S}{ln(n) + \gamma}$ should be similar to Taijima's estimate $k= \frac{\sum_{i,j} \pi_{ij}}{n \choose 2}$.

This is formally described as Taijima's D statistic: $D = \frac{k = \theta_{w}}{stdev}$

Under positive selection (say at locus x: 11 is fitter than 10, 01 is fitter than 00), some ancestor will carry an allele that is favorable. Therefore more descendants will choose them. These descendant from the fit ancestor will have lower heterozygousity than expected, resulting in $k<\theta_{w}$ and a negative $D$.

When the heterozygous is the fittest - 10 is fitter than 00 and 11, the tree will be very balanced, where each diploid individual have a chromosome from each side of the tree. Ex: Sickle cell anemia. The very balanced tree will cause heterozygosity to be higher than expected, resulting in a positive $D$.

# Limitation of Taijima's $D$
1. distinguish exponential growth versus selection on certain locus
2. Cannot detect very recent selection

