---
layout: post
title:  "Generalizing algorithms"
description:
date:   2019-09-15
tags: [algorithm]
category: algorithm
tagline: 
---
CSE 202 lecture 1

# Example one: calculating polynomial

$P(x) = 5x^3 + 4x^2 + 5x + 6 $

Design an algorithm that computes $P(x)$ after we give x = 6

## The Naive Algorithm

1. compute $x^3$, $x^2$ ... $x$ which takes **4 multiplication**
2. calculate $5 x^3$ ..... which takes ** 4 more multiplications**
3. sum them, which takes ** 4 additions **

## Can we do it more efficiently?

Multiplication is expensive in computers. How do we use less multiplication to get the answer?

Do it **this way**: $ x(x(5x+4)+5) + 6 $

Describe the algorithm:
1. Start with the two high order terms: $5x^3 + 4x^2$
2. Retain the highest one with an $x$, the lower one without: $5x + 4$
3. multiply the sum of them with $x$: $x(5x + 4)$
4. add one more lower term $x(5x+4) + 5$
5. multiply the sum of them with an $x$: $x(x(5x+4) + 5)$
6. repeat 4,5 until reaching the constant $6$

## Why does it work?

We are extracting the **common part of multiplication**!

What we are doing here:$x(5x + 4)$

Instead of computing $5x^2$ and $4x$ seperately. We found they **both multiply by $x$**. Therefore we sum it (which is cheaper in a resource sense), and then multiply it(expensive operation).

## What do we learn here?

Extract the common operation. Do it together.

# One more example: find min and max from a series of numbers.

We have 4,19,6,20,28,1,300,8.

Design an algorithm to return the maximal and minimum.

## The Naive Algorithm
1. Set $max = -\inf$, $min = inf$: 
2. seach from the beginning of list, that is $4$
3. replace max if the current number is greater than max. replace main if the current number is lesser than min. ** Every number in the list takes 2 comparisons, in total 16**
4. stop when reaching the end.

In total we need $8*2$ comparisons. If the length of list is $n$ we need $2n$ comparisons.

## Can we do it more efficiently?

From example one, we learn to extract the common part of computation.

So here is the question: what is the common part of getting the max and getting the min?

We are both comparing two numbers!

Can we do it together?

Think of the max and the min: **the max must always be greater than min!**

So if we randomly take two number from the list, compare them. The lesser one is **impossible ** to be the max of the list cause someone is already greater than it.

So if we split the list into two, by pairwise comparing the numbers in the list:

like this: compare 4 to 19, 4 goes to the "small list", 19 into the "big list".

We now have the big list: $19, 20, 28, 300$ and the small one: $4,6,1,8$. 

And we are 100% sure the max must be in the big list!

So the algorithm is:
1. Split the list into big list and small list by pairwise comparing the numbers, which takes **4 comparison**
2. search max in the big list (** 4 comparisons**)
3. search min in the small list (** 4 comparisons**)

Now we reduce the original 16 comparisons to 12 comparisons.

## Further reducing it.

When searching the max in the big list.

Can we reduce more by doing a semi-final, final thing.

1. Within the big list, pairwise compare: $19, 20$ and $28, 300$ --> big-big list $20, 300$ small big list 19,28$ which we don't care cause max will only be in the big ones. Here it takes ** 2 comparisons$
2. and compare within big-big list: 300 is the max ** 1 comparison**.

Here we reduce the 4 comparison t 3 comparisons per big/small list.

## how many steps we take for a list of length $n$?

1. pairwise compare: $n/2$ comparisons.
2. pariwise copare within the big/small: $(n/2)/2$ per list, we have 2 lists: $n/2$ in total.
3. Do it until the remaining sub-list is of length 1. We will need to do $log_2 n$ times

In total there will be log_2 n * n/2 comparisons in total.

# Example 3: