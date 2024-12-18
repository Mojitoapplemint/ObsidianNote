# What is Algorithm?
Set of **well-defined** rules for solving computational problems
- Well-defined means you can't bend or change it
- Consist of basic operations: Addition and Simple Multiplication(between two 1digit numbers)

# 3 Principles for the Analysis of Algorithm
## Worst-Case Analysis
The performance of the algorithm varies depend on how good the input is
- But is there any input that can bend the running time?
- i.e. Is running time valid for all input?
	- If it can, assuption might be too vague or running time is wrong

## Big-Picture Analysis
We don't worry about small constant factors or lower-order terms in running time bounds
- We look at big picture
- To determine which algorithms tend to be faster

## Asymptotic Analysis
Focuses on the rate of growth of running time of the algorithm as the input size $n$ large
- As $n$ goes *infinitely large*, which algorithm is faster?

**Fast Algorithm**
- Algorithm whose worst-case running time grows slowly with input size

# Asymptotic Notation
$$\text{"Suppress Constant Factors and Lower-Order Terms"}$$
- Constant factors generally highly depend on the environment
- Lower Oder terms become increasingly irrelevant as inputs is getting large
- Consider $n$ approaches infinity (When size of input is infinitely large)

$6n\log_{2}(n)+6n$
 $\implies \mathcal{O}(n\log(n))$ (Big-O Notation)

# Big-O Notation ($\leq$)
$T(n)=\mathcal{O}(f(n))$ iff there exist positive constant $c$ and $n_{0}$ such that 
$$T(n)\leq  c\cdot f(n)$$ for all $n\geq n_{0}$
- There is function $T(n)$, defined on the positive integers
- It will denote a bound on the worst-case running time of an algorithm as a function of input size $n$
- $T(n)=\mathcal{O}(f(n))$ iff $T(n)$ is eventually **bounded above** by a constant multiple of $f(n)$
	- No matter how big $n_{0}$ is since asymptotic will anyway consider even larger state

## Little-O Notation
$T(n)=o(f(n))$ iff **for every positive constant** $c$, there exists a choice of $n_{0}$ such that 
$$T(n)\leq  c\cdot f(n)$$ for all $n\geq n_{0}$

## Example 1
Show that for 
$$T(n)=a_{k}n^{k}+a_{k-1}n^{k-1}\dots a_{1}n+a_{0}$$
where $k\geq 0$ is a nonnegative integer and $a_{i}'s$ are real numbers,
$$T(n)=\mathcal{O}(n^{k})$$
**Proof)**
Claim
- $n_{0}=1$
- $c=|a_{k}|+|a_{k-1}|\dots|a_{1}|+|a_{0}|$

Now, we need to prove: For $n\geq n_{0}=1$, $T(n)\leq c\cdot n^{k}$

1. For all $a_{i}'s$ since they are real numbers, $a_{i}\leq|a_{i}|$. Therefore,
$$T(n)\leq  |a_{k}|n^{k}+|a_{k-1}|n^{k-1}\dots |a_{1}|n+|a_{0}|$$

2. For all $n$ and $k$, since they are positive, $n^{k-1}, n^{k-2}\dots n, n^{0}\leq n^{k}$
$$\leq  |a_{k}|n^{k}+|a_{k-1}|n^{k}\dots |a_{1}|n^{k}+|a_{0}|n^{k}$$
$$=(|a_{k}|+|a_{k-1}|\dots|a_{1}|+|a_{0}|)n^{k}$$
$$=c\cdot n^{k}$$
Since this holds for every $n\geq n_{0}$, $T(n)=\mathcal{O}(n^{k})$

## Example 2
Let $k\geq 1$ be a positive integer and define $T(n)=n^{k}$. Show that $T(n)$ is not $\mathcal{O}(n^{k-1})$

**Proof)**
Proof by contradiction: Suppose $T(n) = \mathcal{O}(n^{k-1})$.

Then, there is some constant $c$ and $n_{0}$ that satisfies
$$n^{k}\leq  c\cdot n^{k-1}$$
for all $n>n_{0}$

Since $n>0$, we can divide $n^{k-1}$ to both side
$$n\leq  c$$

Consider that $n$ is variable and $c$ is just an constant. There is no such constant $c$ that greater than every positive integer.
- There is a contradiction, thus the initial assumption was wrong
- Therefore, $T(n)$ is not $\mathcal{O}(n^{k-1})$

# Big-Omega Notation ($\geq$)
$T(n)=\Omega(f(n))$ iff there exist positive constants $c$ and $n_{0}$ such that
$$T(n)\geq  c\cdot f(n)$$ for all $n\geq n_{0}$
- $T(n)$ is big-omega of $f(n)$ iff $T(n)$ is eventually **bounded below** by a constant multiple of $f(n)$

# Big-Theta Notation (=)
$T(n)=\Theta(f(n))$ iff there exist positive constants $c_{1}$, $c_{2}$ and $n_{0}$ such that
$$c_{1}\cdot f(n)\leq  T(n)\leq  c_{2}\cdot f(n)$$ for all $n\geq n_{0}$
- $T(n)$ is eventually **sandwiched** between two different constant multiples of $f(n)$
	- $T(n)=\Theta(n)$ iff $T(n)=\mathcal{O}(n)$ and $T(n)=\Omega(n)$


# Example
Let $T(n)=\frac{1}{2}n^{2}+3n$. Evaluate the validity of each statements

1) $T(n)=\mathcal{O}(n)$
	- **False:** $T(n)$ is quadratic. The linear term does not matter for big $n$

2) $T(n)=\Omega(n)$
	- **True:** $n$ is lower order than $n^{2}$, thus it will be a lower bound

3) $T(n)=\Theta(n^{2})$
	- **True:** Let $c_{1}=\frac{1}{3}, c_{2}=1,n_{0}=6$
$$\frac{1}{3}n^{2}<\frac{1}{2}n^{2}+3n<n^{2}\text{ for all }n>n_{0}$$
4) $T(n)=\mathcal{O}(n^{3})$
	- **True:** Since $n^{3}$ is higher order, it will be upper bound


Note that for 2) and 4), they are the true statements, but $f(n)'s$ themselves *are not the best answer*
- If we are supposed to calculate for $f(n)$, then we must give $n^{2}$

# Paradigm
1. **Divide** the input into smaller subproblems
2. **Conquer** the subproblem *recusively*
3. **Combine** the solutions for the subproblems into a solution for the original probelm

# Counting Inversion
Assume that you are asked to count the number of inversions in an array
- Inversion of an array is a pair of elements that are **out of order**

$$[1,3,5,2,4,6]$$
 $\to$ $(3,2)$, $(5,2)$, $(5,4)$

```
Input: An array A of distinct Integers

Output: The number of inversions of A -the number of pairs(i,j) of array indices with i<j and A[i]>A[j] 
```

$\to$ Write down the array in order and in the given order. Connect those two one by one. Count the number of crossing pairs

![[Pasted image 20240920104853.png|300]]
 $\implies$ 3 crosses

## Worst-Case Scenario
![[Pasted image 20240920105635.png|300]]
 $\implies$ 15 crosses

If the array is in backward order, then it gives the largest number of pairs

For input size $n$
 $=\frac{n(n-1)}{2}$

``` python
#Input: Array A of n distinct integers
#Output: The number of inversions of A

numInv := 0
for i:=1 to n-1 do
	for j:=i+1 to n do
		if A[i]>A[j] then
			numInv++
return numInv
```

Asymtotic Running Time: $\mathcal{O}(n^{2})$

## Divide and Conquer Approach
Divide the array with one recursive call for the left hald of the array and one for the right half of the array

Classify the inversions $(i,j)$ as follows
- Left Inversion
	- Both $i,j$ are in the first half
	- $i,j\leq\frac{n}{2}$
- Right Inversion
	- Both $i,j$ are in the second half
	- $i,j>\frac{n}{2}$
- Split Inversion
	- $i\leq\frac{n}{2}< j$

Let's utilize the MergeSort that we've learned
- Asymtotic Running Time: $\mathcal{O}(n\log(n))$

```python
# Sort_and_CountInv

# input: Array A of n distinct integers
# output: Sorted array B with the same integer, and the number of inversions of A

if n=0 or n=1 then          # Base Case
	return (A,0)
else
	(C,leftInv) := Sort_and_CountInv(First half of A)
	(D,rightInv) := Sort_and_CountInv(Second half of A)
	(B,splitInv) := Merge_and_CountInv(C,D)

return (B, leftInv+rightInt+splitInv)
```

``` python
# Merge_and_CountInv

# input: Sorted arrays C and D (length of n/2)
# output: Sorted Array B (length n) and the number of split inversions
# simplifying assumptions: n is even

i:=1, j:=1, splitInv:=0
for k:= to n do
	if C[i]<D[j] then
		B[k] := C[i], i++
	else
		B[k] := D[j], j++
		splitInv := splitInv+(n/2-i+1)

return (B,splitInv)
```

# Greedy Paradigm
Construct a solution iteratively, via sequence of myopic decisions, and hope that everything works out in the end

1. Easy to come up with one or more greedy algorithms
2. Easy to analyze the running time
3. Hard to establish correctness

**Warning)** Most Greedy Algorithms are not always correct

# Scheduling Example
Goal: Schedule tasks on one or more shared resources to optimize some object
- A schedule specifies an order for processing the jobs

Define jobs
- Jobs are the tasks to be completed
- They have a length $\mathscr{l}_{j}$, which is the amount of time required to process the job
- They have a weight $w_{j}$, which indicates the priority

Suppose we have $n$ jobs to schedule
- How many different schedule can be created: $n!$

## Completion Time $C_{j}(\sigma)$
The completion time $C_{j}(\sigma)$ of job $j$ in a schedule $\sigma$ is the sum of the lengths of the jobs preceding $j$ in $\sigma$ plus the length of $j$ itself
- Suppose $\mathscr{l}_{1}=1, \mathscr{l}_{2}=2, \mathscr{l}_{3}=3$ and the order is $1\to 2\to 3$
- Then completion time would be $1,1+2=3,1+2+3=6$

## Objective Function
To make trade-offs between jobs, we minimize the sum of weighted
$$\min_{\sigma} \sum^{n}_{j=1}w_{j}C_{j(\sigma)} $$
- Minimization is over all $n!$ schedules in $\sigma$

## Example)
Consider the same problem that has 3 jobs with the lengths $$\mathscr{l}_{1}=1, \mathscr{l}_{2}=2, \mathscr{l}_{3}=3$$
- Assuming earlier the tasks is, the higher weight

Schedule 1 $\implies \{j_{1}, j_{2}, j_{3}\} \implies w_{1}=3, w_{2}=2, w_{3}=1$
- $3\cdot 1+2\cdot 3+1\cdot 6=15$

Schedule 2 $\implies \{j_{1}, j_{3}, j_{2}\} \implies w_{1}=3, w_{2}=1, w_{3}=2$
- $3\cdot 1+1\cdot 3+2\cdot 6 =18$

Schedule 3 $\implies \{j_{2}, j_{1}, j_{3}\} \implies w_{1}=2, w_{2}=3, w_{3}=1$
- $2\cdot 1+3\cdot 3+1\cdot 6=17$

Schedule 4 $\implies \{j_{2}, j_{3}, j_{1}\} \implies w_{1}=1, w_{2}=3, w_{3}=2$
- $1\cdot 1+3\cdot 3+2\cdot 6=22$

Schedule 5 $\implies \{j_{3}, j_{1}, j_{2}\} \implies w_{1}=2, w_{2}=1, w_{3}=3$
- $2\cdot 1+1\cdot 3+3\cdot 6=23$

Schedule 6 $\implies \{j_{3}, j_{2}, j_{1}\} \implies w_{1}=1, w_{2}=2, w_{3}=3$
- $1\cdot 1+2\cdot 3+3\cdot 6=25$

$\{j_{1}, j_{2}, j_{3}\}$ is the schedule that minimizes the sum of weighted completion times

## Generalization
Minimize the sum of weighted completion times

**Input)** A set of $n$ jobs with positive lengths $\mathscr{l}_{1}, \mathscr{l}_{2}, \mathscr{l}_{3}\dots\mathscr{l}_{n}$ and positive weights $w_{1}, w_{2}, w_{3}\dots w_{n}$

**Output)** A job sequence that minimizes the sum of weighted completion times

**Q)** If job lengths are identical, should we schedule smaller or larger weight jobs earlier?
- Larger

Higher Weight $\implies$ Higher Priority

**Q)** If job weights are identical, should we schedule shorter or longer jobs earlier
- Shorter

The job scheduled the first contributes to the completion times of all the jobs. Because all jobs must wait for the first one to finish. Since they are all equal with respect to importance, scheduling the shortest job minimizes the negative impact.

# GreedyDiff and GreedyRatio
GreedyDiff
- Schedule the jobs in decreasing order of $w_{j}-\mathscr{l}_{j}$

GreedyRatio
- Schedule the jobs in decreasing order of $\frac{w_{j}}{\mathscr{l}_{j}}$
## Theorem: Correctness of Greedy Ratio 
For every set of positive job weights $w_{1}, w_{2}\dots w_{n}$ and positive job lengths $\mathscr{l}_{1}, \mathscr{l}_{2}\dots \mathscr{l}_{n}$, the Greedy RAtio algorithm outputs a schedule with the minimum possible usm of weighted completion times

# Huffman Code
# Definitions
**Alphabet**
- $\sum$
- Is a finite non-empty set of symbols

**Binary Code**
- A sequence of bits (0s and 1s)
- Binary code for an alphabet is a way of writing each of its symbols as a distinct binary string

**Fixed-Length Binary Code**
- Each symbol uses the same number of bits to be encoded

**Variable-Length Code**
- Each symbol may use different number of bits to be encoded

# Variable-Length vs Fixed-Length
Even though variable-length uses less bits, it can cause confusion while encoding

**Ex)** 

| Symbol | Variable | Fixed |
| ------ | -------- | ----- |
| A      | 0        | 00    |
| B      | 01       | 01    |
| C      | 10       | 10    |
| D      | 1        | 11    |
-> Variable-length can't distinguish AAD and AB, since both are encoded as 001

# Prefix-free Code
**Fixed-length codes can be too long
Variable-length codes are unclear**

Prefix-free code is variable-length code that none of the elements are not a prefix of other element

| Symbol | Encoding |
| ------ | -------- |
| A      | 0        |
| B      | 10       |
| C      | 110      |
| D      | 111      |
-> Becase 0 is used to encode A, the encodings of the other three symbols must start with 1

Variable-length codes can be more efficient than fixed-length *if some symbols of the alphabet occur much more frequently than others*

## Performance Comparison with different frequencies of uses
Prefix-free Variable length

| Symbol | Frequency | Encoding | bits |
| ------ | --------- | -------- | ---- |
| A      | 60%       | 0        | 1    |
| B      | 25%       | 10       | 2    |
| C      | 10%       | 110      | 3    |
| D      | 5%        | 111      | 3    |
- Average number of bits per symbol
	-> $1\cdot 0.6+2\cdot 0.25+3\cdot 0.1+3\cdot 0.05=1.55$

Fixed-legngth
- Average number of bits per symbol
	-> 2

Prefix-free is 22.5% more efficient

# Codes to Binary Tree
**Fixed-Length**
![[Pasted image 20241014222329.png|600]]

**Variable-Length**
![[Pasted image 20241014222404.png|600]]

**Prefix-Free**
![[Pasted image 20241014222423.png|600]]

## Proposition
For every binary code, the encoded length in bits of a symbol $a\in \sum$ equals the *depth of the node* with a label $a$ in the corresponding Binary Tree
- Depth: Number of edges on the path to it from the root

## Bottom up Approach
Start with $n$ nodes and build up a tree with successive mergers
![[Pasted image 20241014222939.png|400]]

![[Pasted image 20241014223001.png|400]]

![[Pasted image 20241014223017.png|400]]

![[Pasted image 20241014223037.png|400]]

# Forest
Huffman's greedy algorithm maintains a forest
- Forest: Collection of binary trees
- The leaves of the trees are in 1-1 correspondence with the symbols in $\sum$

Each iteration chooses two trees and merges them by making their roots the left and right children
- The algorithm stops when only one tree remains

# Huffman's Greedy Criterion
Merge the pair of trees that causes the **minimum-possible increase** in the average leaf depth
- First iteration merges the nodes with the smallest frequency
- The second merge is with the trees that have the *smallest sums of frequencies*
- And so on

## Example)

| Symbol | Frequency |     | Symbol | Frequency |
| ------ | --------- | --- | ------ | --------- |
| A      | 3         |     | B      | 2         |
| B      | 2         |     | E      | 2         |
| C      | 6         |     | A      | 3         |
| D      | 8         |     | C      | 6         |
| E      | 2         |     | F      | 6         |
| F      | 6         |     | D      | 8         |

![[Pasted image 20241014223832.png|300]]
![[Pasted image 20241014223841.png|300]]
![[Pasted image 20241014223918.png|300]]
![[Pasted image 20241014223938.png|300]]
![[Pasted image 20241014223958.png|300]]

Thus, the answer is
![[Pasted image 20241014224120.png|400]]












