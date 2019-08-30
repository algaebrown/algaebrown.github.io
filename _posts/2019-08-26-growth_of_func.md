---
layout: post
title:  "MATH21: Growth of function"
description:
date:   2019-08-25
tags: [math, discrete_math]
category: MATH21
tagline: 
---

# Who has the same rate of growth?

- rate of growth = derivative
- $2^n$, $n^2$, $3n^2$ all have different rate of growth, **if you think calculus-wise**
- **This is not a calculus class **


Ex: $f(n) = n^2, g(n) = 3n^2$, when you double the input?

Ans: both grow by 4, they **grow by the same rate**

# Big-O Notation

if $g(n)$ grows just *as fast or faster* than $f(n)$:

$f(n) = O(g(n))$ or $f(n) \in O(g(n))

formally, we need to find the **witness** $C$ and $k$:

that sastisfies: $f(n) \leq C g(n) $ for all $n \geq k$

# How to determine if f is a big O of G?

1. Domination: $if f(n) < g(n) for all n$
2. Transitivity: if $f \in O(g) and g \in O(h) then f \in O(h)$
3. Additivity and Multiplicativity:
- if $h(n)$ is **non-negative** then $f \times h \in O(g \times h)$
4. Sum is maximum: $f(n)+g(n) \in O(max{f(n), g(n))$. The big one dominates.
5. Ignore the constant. 

Ex: $3n^2 + nlog(n) + 2n$ find its Big-O

Ans: $n^2, n^3$ but $n^2$ is a stricter upper bound.

# Limit rules:

$ \lim_{x\to\infty} /frac{f(n)}{g(n)} = c$ where c is constant

Ex: is $3^n = O(2^n)$

Ans:

$3^n / 2^n = (3/2)^n$ limit of that will not approach c

No.

# Big-Omega and Big-Theta
- Big-Omega (kinda the opposite of Big-O)
    - $ \lim_{x\to\infty} /frac{f(n)}{g(n)} = c > 0 or infinite$
- Big theta is when both big-O and Omega works
    - $ \lim_{x\to\infty} /frac{f(n)}{g(n)} = c > 0 and finite$

Ex: what functions are in family $\theta(n^2)$

Ans: $an^2+b$ whereever a>0 

Ex: show $ n log(n^2) \in O(n \sqrt{n})$

- simpify: $n log(n^2) = 2n log(n)$ simplify into $ n log(n)$
- limit rule: $n log(n)/(n^(1.5)) = n^(-0.5)log(n)
- solve this using **L' Hospital's rule**(上下都一起 d/dx)

# Exercises: Prove or disprove (limit rule or by induction)
- $n^2 \in O(2^n)$ yes
    - [derivative of 2^n](https://www.youtube.com/watch?v=Mci8Cuik_Gw)
- $2^n \in O(2^n)$ no
- $3 n^4 + 2n^3 + 6n + 1000 \in O(n^4)$ yes
- $n log(n) \in O(n^2)$ yes
    - [derivative of log](https://www.khanacademy.org/math/calculus-all-old/taking-derivatives-calc/logarithmic-functions-differentiation-calc/v/derivative-of-log-with-arbitrary-base)
- $C(n,3) \in O(n^2)$ no
- $Fabonacci(n) \in O(2^n): hard to do the limit. (covert to closed form)

# Induction example: Fabonacci

Claim for $F_{n} <= n^2$ whenever $n >= 1$:

when $n = 1$ it's true.

let's assume when $n = k$: $F_{k} = F_{k-1} + F_{k-2} <= 2^k$
and btw $F{k-1} < 2^{k-1}

When $n = k+1$:

$F_{k+1} = F_{k} + F_{k-1} <= 2^k + 2^{k-1} < 2 * 2^{k} = 2^{K+1}$

proved.

# Ex:
if $\lim_{x\to\infty} /frac{f(n)}{g(n)} = 20$

- Big O, theta, Omega all fits

if = 0
- Big O

# ranking of growth rate functions



