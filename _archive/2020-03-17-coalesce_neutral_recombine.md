---
layout: post
title:  "Coalescent Theory"
description: "Simulate a population in $O(nm)$ time"
date:   2021-03-13
tags: []
category: genetics
tagline: 
---
# Goal

Given mutation rate, recombination rate and population size, simulate a population SNP matrix such that this matrix represents the output of a Wright Fisher Model.

# Time goes backwards in the coalescent theory.

Instead of starting from the ancestor, we will be thinking of a process where descendents choose ancestor from the last generation. If two descendants choose the same ancestor, they coalesce. For $n$ individuals, we need $n-1$ coalesce ($n-1$ is not given) for all population collapse into 1 a single ancestor.

## The probability of two descendants picking the same ancestor from last generation
Now there are $k$ individuals choosing from $2N$ ancestor. What is the probability that *none* of them choose the same one?

$1 (1-\frac{1}{2N})(1-\frac{2}{2N})....(1-\frac{k-1}{2N}) \approx \exp{-(\frac{1}{2N}+\frac{2}{2N}+\frac{k-1}{2N}) = \exp{-\frac{{k \choose 2} }{2N}}}\approx 1-\frac{k \choose 2}{2N}$. The first can choose whatever, the second don't choose what have been chosen... all the way to the kth individual.

# How many generations will it take to coalesce?
How many generation would it take until 1 pair coalesce?

$1-\frac{k \choose 2}{2N}$ is the failure rate for 1 generation. It means approximatly $p=\frac{k \choose 2}{2N}$ is the rate where a pair will coalesce in 1 generation. The number of generation it takes to get 1 success fits geometric distribution. Since the expected value of geometric distribution is $1/p$. The expected number of generations it takes to get a pair coalesce is $\frac{2N}{k \choose 2}$.

# Coalesce without recombination: How to simulate backwards in time?
Given total population size $N$, mutation rate $\mu$, we want to simulate the SNP matrix for genomic interval of length $L$ for $n$ individuals.
1. starting from $n$ individuals. Pick a pair to coalesce. Until 1 individual left.
2. Calculate the time needed to coalensce $k$ individuals to $k-1$ individuals by sampling from the geometric distribution: $t_{k} \sim Geom(p = \frac{k \choose 2}{2N})$. This will be the branch length of the tree, for the two individual to coalesce.
3. For every branch of the tree, put mutation onto it, according to the branch length. $\mu$ means the mutation rate per generation per b.p.. Therefore if the time of a branch is $t_{k}$ generations, the number of mutation that occurs on it is $\sim Poisson(\mu L t_{k})$. Give the mutation unique numbers because of the infinite site assumption.
4. Now you have the tree and mutations on it. Start from the root of the tree with binary 000000...0, the bits of the binary string equals how many total mutations you have. Convert 0->1 when coming across the mutation on the path from root to leaves.


# Expected time for all $n$ individuals to coalesce?
$T = t_{n}+t_{n-1}.....t{1} = \sum_{k=1}^{n} \frac{2N}{k \choose 2} = 4N(1-1/n)$

Insight from this: time it takes for last 2 individuls to colaesce = $4N(1-1/2) = 4N \time 1/2$ is about half of the total time for all $n$ individuals to coalesce. This dominates the tree shape.

# Measure in units $2N$ generation
In reality, we don't know total population size $N$. Instead we change all parameters' unit into $2N$ generations.

In the past, the geometric distribution is parameterized $p=\frac{k \choose 2}{2N}$, this means the probability to coalesce every 1 generation. Now we convert the success rate into unit $2N$ generations, $p = {k \choose 2}$. The expected time to coalesce in unit 2N generation becomes $\frac{1}{k \choose 2}$.

Mutation rate also need some modification. $\mu$ is the number of mutation per b.p. per 1 generation. We have a new term *scaled mutation rate* $\theta$, where $\theta = \mu * 4N$. The number of mutation on branch with time $t$ in $2N$ unit is $\sim Poisson(\mu t 2N) = Poisson (\frac{\theta t}{2})$.

# Colaensce with recombination
Given total population size $N$, mutation rate $\mu$, we want to simulate the SNP matrix for genomic interval of length $L$ for $n$ individuals. Now we also have scaled recombination rate $\rho = 4Nr$, where $r$ is the recombination rate per 1 generation per b.p..

What's different from the model without recombination is that now for every generation backwards, we can choose to either 1. coalesce or 2. recombine with certain probability 3. Nothing happen. If we choose to coalesce, 2 individuals collapse into 1, while when we choose to recombine, 1 new individual arise with the SNP matrix crossover.

The probability that no recombination happen in $1$ generation within $k$ individuals:
 $1- kr$.

The probability that no coalescence is $1-\frac{k \choose 2}{2N}$

When we measure time in $2N$ generation:
$1-2Nkr$ no individuals recombine. With probability $2Nkr = \frac{k\rho}{2}$ at least 1 pair recombine.
Simlarly, with probability $k \choose 2$ 1 pair coalesce.

The probability of "something happen" (either recombine or coalesce) is $p = \frac{k\rho}{2} + k \choose 2$. This is used to parameterize the geometric distribution for branch length: $t_{k} \sim Geom(p = \frac{k\rho}{2} + k \choose 2).

When "something happen" we choose "what happen" with probability proportional to $\frac{k\rho}{2}$ : $k \choose 2$.

Last but not least, put mutation on to branch according to the branch length.

## Creating SNP matrix from mutation tree with recombination.
With recombination, the path from root to leaf  isn't unique anymore.

Each path from root to a leaf corresponds to a region that is seperated by recombination.

Therefore, now we need simulate region of the SNP matrix by chunk. And then concatenate them. together.

# Number of mutations that will be create in the SNP matrix?

<TODO>
