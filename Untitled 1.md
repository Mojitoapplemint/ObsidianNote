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
For every set of positive job weights $w_{1}, w_{2}\dots w_{n}$ and positive job lengths $\mathscr{l}_{1}, \mathscr{l}_{2}\dots \mathscr{l}_{n}$, the Greedy Ratio algorithm outputs a schedule with the minimum possible usm of weighted completion times

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

# Spanning Tree Problem
Minimum spanning tree problem is about connecting a bunch of objects as cheaply as possible
- Modeled with Graphs
	- $G(V,E)$ has two ingredients: vertices and edges
	- For this problem, we will consider only undirected graph

**Input:** Undirected graph $G(V,E)$ in which each edge $e$ has a rea;-valued cost $c_{e}$

**Output:** Compute a spanning tree of the graph with the minimum possible fum of edge costs

**Properties of Spanning Tree**
1) It should not contain a cycle
2) Should include a path between every pait of vertices

# Prim's Algorithm
1. Choose an arbitrary vertex. 
2. Observe all possible edges from the vertex in the current spanning tree
3. Choose the cheapest edge if it doesn't cause a cycle
4. Repeat this until all vertex are included

---
## Pseudocode
$X:=\{s\}$   **//** $s$ is an arbitrarily chosen vertex
$T:=\emptyset$           **//** Invariant: the edges in $T$ span $X$

**//** Main Loop
**while** there is an edge $(v,w)$ with $v\in X$, $w\not\in X$ **do**
	$(v^{*}, w^{*}) :=$ a Minimum-cost such edge
	add vertex $w^{*}$ to $X$
	add edge $(v^{*}, w^{*})$ to $T$
**return** $T$

- $T$ keeps track of the edges chosen
- $X$ keeps track the vertices spanned
- Each iteration is responsible for adding one new edge to $T$
- After $n-1$ iterations, $X$ contains all vertices
---
## Running Time: $\mathcal{O}(mn)$
Assume there are $n$ vertices and $m$ edges

Consider 
$$\text{(Total Running Time)}=\text{(\# Iteration)}\times \text{(\# Operations per Iteration)}$$

1. $\text{\# Iteration}$
- While loop iterates until it contains all vertices in the graph
	- Thus it iterates $n-1$ times
	- $\mathcal{O}(n)$

2. $\text{\# Operations per Iteration }$
- In each iteration, it searches all possible edges for the cheapest one
	- There are total $m$ edges
	- $\mathcal{O}(m)$

3. $\text{Total Running Time}$
- $\mathcal{O}(mn)$

# Kruskal's Algorithm
Unlike Prim's, rather than growing a single tree from a starting vertex, it can grow multiple trees in parallel
- It will create a single tree at the end
- Can choose the cheapest edge that is not connected to the starting vertex

1. Sort the list of edges in increasing order
2. From the beginning of the list (the cheapest edge), observe an edge
3. If that does not cause cycle, then add them in the current spanning tree
4. Repeat this until all vertex are included

---
## Pseudocode
**//** Preprocessing
$T:=\emptyset$
$\text{sort edges of E by cost}$   **//** e.g. using MergeSort
**//** Main Loop
**for** each $e\in E$, in nondecreasing order of cost **do**
	**if** $T\cup \{ e \}$ is acyclic **then**
		$T:=T\cup \{ e \}$
**return** $T$

---

## Running Time of Preprocessing: $\mathcal{O}(m\log (n))$
Assume that there are $n$ vertices and $m$ edges. 
- Sorting $m$ edges by its costs
	- Assume that we use MergeSort
	- Then, it would be $m\log(m)$
	- However, we can express this in different way
- The minimum number of edges required to create the spanning tree is $n-1$
- And the maximum number of edges required is $_{n}C_{2}=\frac{n(n-1)}{2}$
- Then,
$$n-1\leq m \leq\frac{n(n-1)}{2}$$
$$\implies \log(n)\leq \log(m) \leq 2\log(n)$$
- Thus $\log(m)$ and $\log(n)$ are interchangeable
- $\therefore \mathcal{O}(m\log(n))$

## Running Time for Main Loop: $\mathcal{O}(mn)$
1. for loop is iterating for all edges, thus there are $m$ iterations
2. In each iteration, it checks whether termination vertex is included in $T$ or not, thus linear search
	- Therefore, $\mathcal{O}(n)$
3. Total Running Time for Main Loop is $\mathcal{O}(mn)$

## Total Running Time: $\mathcal{O}(mn)$
It would be 
$$\mathcal{O}(m\log(n))+\mathcal{O}(mn)\approx \mathcal{O}(mn)$$


# Union-Find Based Kruskal
Kruskal's Algorithm check cycle in every iteration
- Adding an edge $(v,w)$ to $T$ creates a cycle iff $T$ already contain $v-w$ path
	- $v-w$ path does not necessarily be an one edge

To identify whether $T$ contains a path between a given pair of vertices, we utilize the Union-Find Data Structure
- Maintain a partition of the static set of objects
- In the initial partition, each object is in its own set
- Once some sets are merged, they never split

$v$ and $w$ being in the same set of the partition means that $T$ contains $v-w$ path

## Use union-find data structure to keep track of the connected components of the so-far solution
1. Each vertex is in its own connected component at the beginning
	- Initialize
2. When $(v,w)$ is added to the so-far solution, components that contain $v$ and $w$ merge into one
3. Checking cycle is checking whether $v$ and $w$ are already in the same component

## Operators
**Initialize:** Given an array $X$ of objects, create a union-find structure with each object $x\in X$ in its own set
- $\mathcal{O}(n)$

**Find:** Find object $x$ in the data structure, and return the name of the set that contains $x$
- $\mathcal{O}(\log(n))$

**Union:** Merge the sets that contain $x$ and $y$ into a single set
- If two objects are already in the same set, do nothing
- $\mathcal{O}(\log(n))$

---
## Pseudocode
**//** Initialization
$T:=\emptyset$
$U:=\text{ Initialization(V)}$  
$\text{sort edges of E by cost}$ 
**//** Main loop
**for** each $(v,w)\in E$ in nondecreasing order of cost **do**
	**if** $\text{Find}(U,v)\neq \text{Find}(U,w)$ **then**
		**//** no $v-w$ path in $T$, so OK to add $(v,w)$
		$T:=T\cup \{ (v,w) \}$
		**//** update due to component fusion
		$\text{Union}(U, v,w)$
**return** $T$

---
## Total Running Time: $\mathcal{O}((m+n)\log(n))$
$\text{(Total Running Time)}=\text{(Preprocessing)}+\text{(Total Running Time for Find)}+\text{(Total Running time for Union)}$
1. $\text{(Preprocessing)}=\text{(Initialization)+(Sorting Edges)}=\mathcal{O}(n)+\mathcal{O}(m\log(n))$

2. $(\text{Total Running Time for Find})=\text{(\# Iteration)}\times \text{(\# Find per iteration)}\times \mathcal{O}(\log(n))$
	- There are 2 $\text{Find}$ operations per iteration
	- And we iterates this $m$ times
	- $=2\cdot m\cdot \log(n)\implies\mathcal{O}(m\log(n))$

3. $\text{(Total Running Time for Union)}=\text{(\# Iteration)}\times \text{(\# Union per Iteration)}\times \mathcal{O}(\log(n))$
	- There are one $\text{Union}$ operation per iteration
	- And we iterate this $n-1$ times
		- Technically, we iterate this $m$ times, but minimum required number of edges is $n-1$
	- $(n-1)\cdot\log(n)\implies \mathcal{O}(n\log(n))$

$\therefore \text{(Total Running Time)}=(m+n)\log(n)$

# The Weighted Independent Set Problem (WIS)
Let $G=(V,E)$ be an undirected graph

The independent set of $G$ is a subst of $S\subseteq V$ of mutually non-adjacent vertices
- For all $v,w\in S$, $(v,w)\not\in E$
- Includes $\emptyset$ and singleton

**Ex)**
![[Pasted image 20241113211121.png|150]]
- 6 Independent set
	- $\emptyset$
	- 5 singletons

## Maximum Weighted Independent Set
**Input)** An undirected graph $G=(V,E)$ and nonnegative weight $w_{v}$ for each vertex $v\in V$
**Output)** An independent set $S\subseteq V$ of $G$ with maximum possible sum $\displaystyle\sum_{v\in S}w_{v}$ of vertex weights
Maximum Weighted Independent Set(MWIS)
- Optimal Solution to the WIS


# Lemma: WIS Optimal Substructure
Let $S$ be an MWIS of a path graph $G$ with $n\geq{2}$ vertices
Let $G_{i}$ denote the subgraph of $G$ comprising its first $i$ vertices and $i-1$ edges

Then, $S$ is either 
- An MWIS of $G_{n-1}$
- An MWIS of $G_{n-2}$, supplemented with the final vertex of $G$, $v_{n}$

Singles out the only two possibilities of an MWIS. So Bigger one from them is the optimal solution

## Prove
Let $G=(V,E)$ denote a $n$-vertex path graph with edges $(v_{1},v_{2}), (v_{2},v_{3})\dots (v_{n-1}, v_{n})$
- Each vertex have a nonnegative weight $w_{i}$
- Suppose $S$ is MWIS with total weight $W$
	- Then, $S$ either contains the final vertex $v_{n}$ or does not

i) Suppose $v_{n}\not\in S$
- Obtain the $(n-1)$-vertex path graph $G_{n-1}$ by removing $v_{n}$ and $(v_{n-1},v_{n})$ from $G_{n}$
- Then, $S$ is an independent set of $G_{n-1}$ with total weight $W$
- If $S^{*}$ is an independent set of $G_{n-1}$ with total weight $W^{*}>W$, then $S^{*}$ would also constitute an independent set of total weight $W^{*}$ in the larger graph $G$
	- This would contradict that $S$ is the optimal solution

Once you know that an MWIS excludes that last vertex, you know exactly what it looks like-an MWIS of the smaller graph $G_{n-1}$

ii) Suppose $v_{n}\in S$
- Then $v_{n-1}\not\in S$
- We can obtain $(n-2)$-vertex path graph $G_{n-2}$ from $G$ by removing $v_{n}, v_{n-1}$ and $(v_{n-2}, v_{n-1}), (v_{n-1}, v_{n})$
	- $S$ is **not** an independent set of $G_{n-2}$ since $v_{n}\not\in G_{n-2}$ 
	- Consider $S-\{ v_{n} \}$, then it contains neither $v_{n}$ nor $v_{n-1}$
	- So, $S-\{ v_{n} \}$ can be regarded as an independent set of the smaller graph $G_{n-2}$, with total weight of $W-w_{n}$
	- That means $S-\{ v_{n} \}$ must be an MWIS of $G_{n-2}$
- Suppose that $S^{*}$ were an independent set of $G_{n-2}$ with total weight  $W^{*}>W-w_{n}$
	- Because $G_{n-2}$ does not  contain $v_{n-1}$ adding $v_{n}$ to $S^{*}$ is valid
	- Then, $W^{*}+w_{n}>W$
	- This contradicts that $S$ is the optimal solution

# WIS Recurrence
With the assumption and notation of WIS Optimal Substructure, let $W_{i}$ denote the total weight of an MWIS of $G_{i}$. Then,
$$W_{n}=\max\{W_{n-1}, W_{n-2}+w_{n}\}$$

Or more generally, for evey $i=2,3,\dots n$
$$W_{n}=\max\{W_{i-1}, W_{i-2}+w_{i}\}$$
---
## Pseudocode
- Input: A path graph $G$ with vertex set $\{ v_{1},v_{2}\dots v_{n} \}$ and nonnegative weight $w_{i}$ for each vertex $v_{i}$
- Output: A MWIS of $G$

**if** $n=0$ **then**
	**return** the empty set
**if** $n=1$ **then**
	**return** $\{ v_{1} \}$

**//** Recursion when $n\geq{2}$
$S_{1}:=$ recursively compute an MWIS of $G_{n-1}$
$S_{2}:=$ recursively compute an MWIS of $G_{n-2}$
**return** $S_{1}$ or $S_{2}\cup \{ v_{n} \}$, whichever has higher weight

---
## Running Time
Same with running time for Fibonacci Sequence
- At each level of recursion, the number of calling the algorithm gets doubled, so it grows exponentially

# Dynamic Programming Approach
So, the exponential running time of the recursive WIS algorithm is because of solving the same subproblems from scratch over and over again
- Let's store the solution of each subproblem 

Since there are total $n+1$ subgraph(including $\emptyset$), now its linear since we can solve each subproblem only once.

---
## Pseudocode 1: Return weight only
$A:=$ length$-(n+1)$ array  **//** Subproblem solutions
$A[0]:=0$    **//** Base case #1
$A[1]:=w_{1}$  **//** Base case #2

**for** $i=2$ to $n$ **do**
	$A[i]:=\max\{ A[i-1], A[i-2]+w_{i} \}$

**return** $A[n]$ **//** Solution to the largest subproblems

---
## Pseudocode 2: Return weight and MWIS
$A:=$ length$-(n+1)$ array  **//** Subproblem solutions
$A[0]:=0$    **//** Base case #1
$A[1]:=w_{1}$  **//** Base case #2

**for** $i=2$ to $n$ **do**
	$A[i]:=\max\{ A[i-1], A[i-2]+w_{i} \}$

**return** $A[n]$ **//** Solution to the largest subproblems

---
## Theorem
For every path graph and nonnegative vertex weights, the WIS algorithm runs in linear time and returns the total weight of a maximum-weight independent set.

# Dynamic Programming Paradigm
Systematically solve all the sub problems one by one, working from smallest to largest, and extract the f inal solution from those of the subproblems
1) Identify a relatively small collection of subproblems
2) Show how to quickly and correctly solve larger subproblems given the solutions to smaller ones
3) Show how to quickly and correctly infer the final solution from the solutions to all of the subproblems

## VS Divide-and-Conquer
### 1. Flexibility of Dividing the Input
Each recursive call of a typical DnC algorithm commits to a single way of dividing the input into smaller subproblem
Each recursive call of DP keep its options open, considering multipl ways of defining smaller subproblems and choosing the best of them

### 2. Repetitive Subproblem
In DP, subproblmes generally recur across different recursive calls. That's why we want to store these in some data structure
In DnC, all subproblems are distinct and there is no point in caching their solutions

### 3. Running Time Improvement
DnC often replace a straightforward polynomial-time algorithm with a faster DnC version
DP gives polynomial-time algorithm for optimization problem for which straightforward solution (eg. Exhaustive search) require an exponential running time

### 4. Purpose of Subproblem Selection
In DnC, subproblems are chosen to optimize running time, correctness often takes care of itself
In DP, subproblems are usually chosen for correctness, come what may with the running time

### 5. Size of Subproblem
DnC generally recurses on subproblem with sie at most a constant fraction(50%) of the input
DP can recurse on subproblem that are barely smaller than the input, if necessary

### 6. Range of Application
As the more sophisticated paradigm, dynamic programming applies to a wider range of problems than divide-and-conquer
The divide-and-conquer paradigm can be viewed as a special case of dynamic programming, in which each recursive call chooses a fixed collection of subproblems to solve recursively
