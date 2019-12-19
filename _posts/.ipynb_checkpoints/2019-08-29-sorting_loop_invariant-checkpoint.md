---
layout: post
title:  "MATH21: Loop Invariant: Sorting/Searching Algorithm"
description:
date:   2019-08-29
tags: [math, discrete_math]
category: MATH21
tagline: 
---
# Specification of problem:

- Input: Given a list of a,b,c,d,e..

- Output: rearrange to become a<b<c<d<e...

## Selection sort (Rosen 203, exercise 41-42)
To put the smallest to the front

## Bubble sort

## Insertion sort

## Bucket sort

## Merge sort

## Bogo sort: Monkey sort $O(n!)$

## Quick sort

## Binary search tree traversal

# Proving them: from HOW to WHY: Loop Invariant (Lec 07)[https://podcast.ucsd.edu/watch/wi19/cse21_b00/7/screen]

- loop not change: what does not change 

1. Look for a loop invariant, state the proerty precisely: subproblem of a smaller input
2. Prove that it is **invariant** over any number of iteration by **induction**
3. Use the invariant to prove correctness. Show that **when a loop is finished**, the invariant will leads us to the solution.

## Proving Selection Sort

1. What are the 2 loop invariants for selection sort?
- after t iterations, the first $t$ elements will be **in order**.
- after t iterations, the first $t$ elements are the **smallest**.

2. prove the loop invariant true
- what is the induction variable? what we want is when $t$ is true, $t+1$ is also true. (iterative algorithm)
    - if this is a **recursive algorithm**, $n$ might be the one to plug in. (cause we are pluggin the whole thing into itself)
- what is the base case? $t=0$ when the loop hasn't started yet, first 0 elements are sorted. (A set of nothing is trivially sorted).And they are smallest.
- during it $t+1$ iteration, we find the smallest among $t+1$ to $n$ and swap it with $t+1$. Thus we now have the first $t+1$ are the smallest.
	- say when $1$ to $t$ is smaller than all of $t+1$ to the end. 
	- Therefore before $t+1$ are all smallest than the rest.
	- $1$ to $t$ are sorted. $1$ to $t$ are smaller than $t+1$, therefore $1$ to $t+1$ are sorted.

3. prove the algorithm is correct?
- the list are of length $n$
- What implies correct: first $n$ elements in order.
- we execute n (when $t = n$)times, so the first $n$ elements are in order.

# Searching algorithm
find the index in the list of length $n$ for the value $x$ your are searching for.
return the index $i$ or return $0$ if it does not exist in the list.

- if the list is not sorted, you need to go through the whole list in the worst case.

1. Prove by loop invariant?
- after the first $t$ interation, we know the fist $t$ are NOT the item we are searching for. $ a_{1}$ to $a_{t} \neq x$

- We have two outcomes to consider:
    - if $ i \neq 0$ then $x = a_{i}$
	- if $ i = 0$, we iterated $n$ loops: now we need **loop invariant**.
	    - Base: $t=0$: $x \not\subset \emptyset$
		- Inductive hypothesis: assume $t$ is true, 
		- Inductive step: when $t+1$, $a_{t+1} \neq x$ so we make sure first $t+1$ are still not what we are looking for $x$.
		- conclusion: all the way to $n$ we are sure $x$ is not there

2. The complexity of algorithm.
- the worst case we need to find all $n$ elements.
- the best is we find at the first position.
- average? $n/2$

## Searching in sorted list: binary search

1. Prove the correctness of two things.
    - if return $p \neq 0$ then $a_{p} = x$
	- if return $p=0$ then there's no $a_{p} = x$
2. Prove the first case: we will find $i \leq p \leq j$
    - Base case: before the loop, $i = 1$, $j = n$ anything must be between them.
	- Indutive hypothesis: Assume after $t$ iterations, $i \leq p \leq j$
	- when $t+1$:
	    - if $ x = a_{m}$ where $m = (i+j)/2$, then we return $m$: $m$ is between $i$ and $j$.
		- if $ x > a_{m}$ then $i = m+1$, $a_{i} \leq x \leq a_{j}$ that makes $i \leq p \leq j$
	- prove invariant: the loop stops when $i=j$ and as $i \leq p \leq j$ is only case is $i = p = j$
3. How many run time?
- worst case $log(n) + 1 $
- But we use sorted array: and this costs more.
- if you need to search for more than 1 time.

# General questsion to ask about algorithm
- Specification: what problem
- algorithm description: how to solve
- correctness: why does this solve
- run time analysis: when do we get the answer.
	