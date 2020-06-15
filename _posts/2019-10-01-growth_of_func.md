---
layout: post
title:  "Divide and Conquer"
description:
date:   2019-10-01
tags: [algorithm]
category: algorithm
tagline: 
comments: true
---
**CSE 202 Lecture 2-4**
- Divide and Conquer

# Divide and Conquer
- recursion is to break into **smaller** subproblems (**of the same type**), solving it recursively (use the same solution).
- divide and conquer is a very specific form of recursion.

## Example 1: Given a list of numbers, sort them.
Input: $a_1 .... a_n$
Output: sorted list

Key Questions: 
- How to make $a_1 .... a_n$ of smaller size? 
- How do we put the solutions together? 
- When does the recursion stop?

### Merge-Sort ($a_1.....a_n$), length of list = y
1. cut the list in half `subproblem`, do merge-sort on each half to sort it, whenever y >= 2.
    - when y = 1 we cannot split. This also prevents infinte recursion.
2. how to combine two sorted list? $O(n)$

### Prove of correctness.
prove by induction.

when n= 1, sorting them is trivial.
assume n<k, it's true.
let's see n=k+1, subproblems of size smaller, as long as merging is correct, it is correct.
mergine we are extracting the smallest? Cause we are taking the smallest in the sorted. Therefore merge is correct.

### Analyze complexity
- Define time complexity: $T(n)$ = **worst case** # of steps taken to sort a **list of length n**.
- why n? cause longer the list, the longer it will take to sort.
- why worst case? becuase sometimes we are lucky yo have a sorted list. Most of the time we have no control over the input to the program.
- it's possible to do best, average case.

#### Recursive helps us figure out complexity.
T(1) = 1
T(n) = 2(T(n/2)) + time it takes to merge(linear time) = 2T(n/2) + cn ( c depend on what kind of operation bout count on)

** Solving recursion relationship into explicit function like logn**
- review theta, omega, big-O
- solve the T(n) = n logn


### Quick Sort
1. select pivot element, partition the list into left (less than pivot) right side.
    - all in left are <= right
	- partitioning algorithm. prove the correctness. list with pointer with both end
	- how to select pivot? so that each part is not empty, and subproblem is of smaller size.
2. for each part, recursive do quick sort.
3. put them together is just concatenation. O(1)

** if we select a bad pivot and bad partition algorithm**
T(n) = T(1) + T(n-1) ==> O(n^2) worst case.

** simple way to fix it. **
- select randomly? hope we can get a more even partition?? *randomized algorithm*
    - the probability is 1/n to get exactly in the middle. Luck is not on our side.
	- T(n/4) + T(3/4n) solve? **worst case** 50% of change we will randomly select a pivot here is no worse than this. this end up to be nlogn.
	    - why? see all elements as sorted. The middle 50% falls into the 25%-75%.
		- we expect to try twice, to get a right split.
		- try twice, success with right partition, and then proceed with recursion.
		- average case analysis nlogn.
- if we select two and use the average as pivot??
- there's a O(n) to find the median algorithm. But the time constant is bigger.
- randomness don't care about the input.

#### Proof of correctness
- correctness of partition algorithm.
  all left <= pivot; pivot <= all right thus all right >= left
  **make sure not empty.** <-- the partitioning algorithm takes care of it.
  what if all elements are them same??
  prove by induction.

### What is the best sorting used in practice nowadays.

## Example 2: Integer multiplication
Given 2 n-bit numbers $x$ ans $y$, return the $x \times y$.

### Naive algorithm: elementary school way 
- takes $\theta(n^2)$

### Divide and conquer
- break x into $x_1, x_0$. $x= x_1*2*(n/2) + x_0$
- break y using similar ways.

- $x*y = x_1*y_1*2^n + x_1*y_0*2^(n/2)...$
- we now make 1 multiplication into 4 multiplication.

#### Time complexity
- recursion: $T(n) = 4T(n/2) + cn$
    - addition takes $\theta(n)$ time
- solve it. $\theta(n^2)$ It's not more efficient than the elementary school way.

### Divide and conquer: fix it!!
- It turns out we can make 4 multiplications into 3 by doing some small math trick.
- $x_1 y_0 + x_0 y_1$ = (x_1 + x_0)(y_1 + y_0) - x_1 y_1 - x_0 y_0$
- The last two diagonal term $x_1 y_1 , x_0 y_0$ is already computed!
- Now we only divide into 3 multiplication!

#### Time complexity


### Divide it to get even better: Toom-Cook algorithm, Schonhage-Stramen, Furer

## Example 3: Closest pair of points.
- Input: $(x_1, y_1)....(x_n, y_n)$
- Output: two **distinct** point such that distance between them are the cloestest among all points.

### Naive algorithms
- examine all $n(n-1)/2$ points.
- $\theta(n^2) time$

### Divide and Conquer
- How to divide points into halfs by a vertical line? Find the median of $x_1, x_n$? sort Takes \theta(n logn), and draw a vertical line.
    - the points on the line. sort y, compare one to the next \theta(n logn)
- merge = min(L cloest pair with delta distance, R cloestest pair) also need to find the points close to the line. (points from different sides can also form close distance) but how close is close
    - How far can these points from the midline? Must be delta within the midpoint. Draw parallel lines around the midline. We only need to consider the points within that range.
	- Do we need to consider ALL pair of points within the lines? Draw grids of size 2/delta.
	    - cannot have 2 points in the grid. cuase the smallest distance is delta but the diagonal is smaller than delta!
		- There are only 10 relevant cells on the other side. \theta(10n)
		- we are not constructing the cells. go the most similar y, go up and down 5 points at most.
		- you can even optimize the constant 10!

## Example 4: Fast Fourier Transform
Given two polynomial

Input:
- $A(x) = a_0 + a_1 x + ..... a_n-1 x^(n-1)$ n coefficients 
- $B(x)$
Return:
- $C(x) =  $A(x) \times B(x)$ 2n coefficients
    - c_i = \sum_j  a_j b_{i-j} 左上角到右下角的斜線總合
	- cumulation sum = **convolution sum**
	- whenever you have function you have Fourier Transform ?!
	
### Naive algorithm
- each c_i takes i, i from 0...2n-2, $\theta n$ times

### Fast Fourier Transform.
- Go polynomial value representation.
- ex:
    - A(x) = 1-2x+x^2
    - B(x) = 1+2x+3x^2
- If we know three points for these polynomial, we can reconstruct it.
- **interpolationg problem** coefficient v.s. value = time v.s. frequency.
- A(1) = 0, A(2) = 1, A(-1) = 4
- B(1) = 6 B(-1) = 2, B(2) = 17
- $A(x)B(x) = C(x)$ for each value, $C(1) = 0, C(2) = 17, C(-1) = 8$ done in $\theta(n)$ time.
- But C(x) is x^4, we need 4 distinct points to reconstruct. Highest degree *2.
- How do we get back to the coefficient here? values --> coefficient??

- we need to keep the number of point > max degree.

- when we are computing A(1), A(2), what are the **commonality** of computation.
    - Cut A(x) in half. A_0(x1), a_0(x2), A_0(x_3)....factor out common.
	    - bad divide and conquer cause the subproblem become a different problem
		- polynomial are evaulted in doubled points which makes it different.
		- we also need to pick the points carefully.
	- Cut A(x) into even and odd terms. (Different kind of divide)
	    - replace y = x^2: to make degree half. 
		- Now we need less points.
	- How to make 8 points --> 4 points --> 2 points. Think of x^2.
	    - Select the pairs of points carefully so that after square, two points between 1.
		- these points need to further pair up **even when (x^2)^2.**
		- what if we choose $i$ and $-i$, when they square they both become $-1$
		- if we need 8 points. (1, -1), (i, -i), square root them, square root again.
		- it either be 2,4,8,16 points.
		use the 2n roots.
- Roots of unity.
    - every polynomial of degree $n$ has $n$ roots while you work in the complex number system.
    - we want these that have n **distinct** roots.
	    - $x^4$
		- \omega^n = 1; (\omega^n)^2 = 1 one of the solution is 
#### Time complexity
T(n) = 2T(n/2) + cn


# Problem solving session
## Recursion: Time complexity
1. $T(n) = 2T(n/2) + cn$
    - draw the recursion tree
	    - in each node write the size of the subproblem: 1, 1/2, 4/1
		- to decide how many branch: how many subproblem: 2
	- calculate time per subproblem: 
	    - $cn$ decide the time to divide and merge the problem of size $n$
		- therefore for subproblem of size $n/2$ it will take $nc/2$
	- calculate time for every layer = number of subproblem * time per subproblem
	- sum over every layer.
2. Go through and **prove** [master theorem](http://www.cse.unt.edu/~tarau/teaching/cf1/Master%20theorem.pdf)

3. Sample questions he gone through over class
- $T(n) = 4T(n/2) + cn$
    - need to review [geometric series](http://mathworld.wolfram.com/GeometricSeries.html)
	- In geometric series lopital rule
- $T(n) = 2T(n/2) + 1$
- $T(n) = 4T(n/2) + n^2$
- $T(n) = T(n/2) + 1 $ binary search
- $T(n) = T(\sqrt{n}) + 1$ results in O(loglogn)
    - need to review calculus.
- $T(n) = T(n/5) + T(3n/5) + cn$
- $T(n) =  T(9n/10) + cn$
- $T(n) = 3T(n/2) + cn$


## Hints he gave for homework
- hw0-1 Dynamic programming:
   - step 1 define subproblem
   - step 2 recursion formulation
   - step 3 prove it
- hw0-2 Do it in the right order will help you generalize for hw0-3. hint is also on lecture 0.
- hw0-4 Think of the pond as connected components in a grpah and use BFS/DFS
- hw0-5 Read resource 3 on website where's there's an algorithm for frequent element > 2/n and try to generalize with it.

## Miscellanous