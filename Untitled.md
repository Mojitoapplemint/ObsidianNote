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
$X:=\{s\}$       **//** $s$ is an arbitrarily chosen vertex
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
