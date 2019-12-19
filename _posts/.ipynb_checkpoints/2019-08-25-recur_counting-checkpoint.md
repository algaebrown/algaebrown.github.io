---
layout: post
title:  "MATH21: Recursive Counting(Lec04)"
description:
date:   2019-08-25
tags: [math, discrete math]
category: MATH21
tagline: 
---
# Recurrence
solve a problem by sucessively reducing to same problem of smaller.

Ex:
- Fabonacci: $F(n) = F(n-1)+F(n-2)$
- Factorials: $F(n) = n F(n-1)$
- Summation of integers: $S(n) = S(n-1) + n$

## getting the closed form

Ex: Summation of integer

$ S(n) = S(n-1) + n $
$ S(1) = 1 $

To get a close form:
$S(n) = 1+2+ ......+ n$
$S(n) = n+(n-1)... + 1$

Add the two together

$2 \times S(n) = (n+1)n$

Thus,

$S(n) = \frac{(n+1)n}{2} $

This is the **closed form**

### Writing in binomial coefficients?
$\frac{(n+1)n}{2}= C(n+1,2) $
- select 2 from a set of set n+1.
- n+1 binary strings of 2 ones.

How to count (n+1)-bit sequences with 2 ones **recusively**??

- string starts with 1: $C(n, 1) = n$
- string starts with 0: $C(n, 2) = S(n-1)$

Now we have recurrence:
S(n) = S(n-1) + n

## Getting the closed form: guess and prove by induction
$S(1) = 1$
$S(2) = 1+2 = 3$
$S(3) = 3+3 = 6$
$S(4) = 6+4 = 10$
...


These are [Triangle numbers](https://oeis.org/).

### Induction
- verify base case
- make S(k+1) by S(k)

## Getting the closed form: Unraveling: Plug into itself
$S(n) = S(n-1) + n$
$= S(n-2) +(n-1) + n$
$= S(n-3) + (n-2) + (n-1) + n$

...

$= S(n-k) + (n-k+1) + ... + n$


set $k = (n-1)$ so that $S(n-k) = S(1) = 1$

so we have $S(n) = 1 + 2 + 3 + ... + n = {n(n+1)}/2$

### Ex:
$a(1) = 2$
$a(n) = 2a(n-1) + 2^n$ for $n>2$

Ans:
$a(n) = 2a(n-1) + 2^n$
$= 2(2a(n-2) + 2^{n-1}) + 2^n$
$= 2^2 a(n-2) + 2\times{2^n}$
$= 2^2 (2a(n-3) + 2^{n-2}) + 2\times{2^n}$
$= 2^3 a(n-3) + 3 \times {2^n}$
...

$= 2^k a(n-k) + (k)\times {2^n}$


make $k = n-1$ to get base case where $a(1) = 2$

plug in:

$ 2^{n-1}\times a(1) + (n-1) \times {2^n}
= n{2^n}$

# Tower of Hanoi
[Tower](https://www.google.com/imgres?imgurl=https%3A%2F%2Fwww.tutorialspoint.com%2Fdata_structures_algorithms%2Fimages%2Ftower_of_hanoi.jpg&imgrefurl=https%3A%2F%2Fwww.tutorialspoint.com%2Fdata_structures_algorithms%2Ftower_of_hanoi.htm&docid=u4uxiv_fIw3X0M&tbnid=8q0EeM2QfkpEDM%3A&vet=10ahUKEwjB0OT6857kAhUCbq0KHVINBdcQMwh8KAMwAw..i&w=348&h=189&client=firefox-b-d&bih=575&biw=653&q=tower%20of%20hanoi&ved=0ahUKEwjB0OT6857kAhUCbq0KHVINBdcQMwh8KAMwAw&iact=mrc&uact=8)

rules:
- move 1 disk at a time
- big ones cannot be put on small ones

How many steps do we need to move n disks to another.

**if there's only 1 disk**: $Hanoi(1) = 1$

**if there are 2 disks:** 
1. move 1 -- $Hanoi(1)$
2. move 2
3. move 1 onto 2 -- $Hanoi(1)$

$Hanoi(2) = 2 Hanoi(1)+ 1 = 3$

**if there are 3 disks:**
1. move 1, move 2, and 1 onto 2 -- $Hanoi(2)$
2. move 3, 
3. do $Hanoi(2)$ again

$Hanoi(3) = 2 Hanoi(2) + 1$

Maybe,
$Hanoi(n) = 2(Hanoi(n-1)) + 1

**General Strategy**
1. Move smalled n-1 to empty --> $Hanoi(n-1)
2. Move largest to another empty
3. Move n-1 to the largest --> Hanoi(n-1)

The base case is $Hanoi(1) = 1$

**Unraveling**
$T(n) = 2T(n-1) + 1$
$= 2(2(T(n-2)+1) + 1$
$= 2(2(2T(n-3)+1)+1) +1$
$= {2^3}T(n-3) + 2^2 + 2^1 + 1$
...
$= {2^k}T(n-k) + 2^(k-1) ...... + 2^1 + 1$



To solve $2^n + 2^{n-1} .... + 1$:

$S(n) = 2^n + 2^{n-1} .... + 1$

$2S(n) = 2^{n+1} + 2^{n} .... + 2$

$2S(n) - S(n) = 2^{n+1}-1 = S(n)$ 

review geometric series


$T(n) = 2^n -1$

# Binary strings avoiding 00 by recursion

$B(n)$ = number og length n 00-avoiding binary strings

**Do the recursion**

$B(n)$ might start with 1:

1__ __ __ __ __ --> $B(n-1)$.

It might also start with 0:

then the first must be 1, 10_ __ __ __

and $B(n-2)$

We have **recurrence**: $B(n) = B(n-1) + B(n-2)$