# Mathematical Statement
A statement is something which can be **assigned a truth value**
- Somethings is either true or false (or we don’t know) 

**Ex)**
- There are an infinite of prime number (O) 
- “Let x be a real number,” “What is a number?”(X)

## Different Type of Statement
Conjecture
- A statement which we believe to be true, but cannot yet prove 

Lemma -> Proposition -> Theorem
- All types of statements which *have been proven*
- Roughly in increasing order of difficulty and/or important 

Axiom
- A statement that is *assumed to be true*

# Logical Operation
## And( $\wedge$ )
True if both p and q are true, unless it’s false or unknown (True & Unknown) 

## Or( $\lor$ )
True at least one of them are true.

“$p\text{ XOR } q$ / $p\oplus q$"
- Only true if one of them is true, not both

## Implication( $p\longrightarrow q$  / $p\implies q$)
“$\text{if }p\text{, then }q$" : ( $p\longrightarrow q$ )
“$p\text{ implies }q$” : ( $p\implies q$ )
- **True if whenever p is true, q is also true **
- To show an implication is false, find counter example(p is true, but q is false)
- *The only case it’s false if p is true, but q is false *

**Note)**
If $p$ is always false, then we take "$p\longrightarrow q$" to *be true*, regardless $q$ is true or false 
- If 0=1, then 1+1=5 : is considered as true 

## If and only if ( $p\longleftrightarrow q$ / $p\iff q$ / $p\text{ iff }q$)
- True if whenever p is true, q is true, and whenever q is true, then p is true 
- Original statement and its converse are both true 

## Not P ( $\lnot p$ )
true if p is false, and false if p is true 

## Converse
For original statement $p\longrightarrow q$ , its converse statement is $q \longrightarrow p$ 
- Even if the original statement is true, converse can be false or true 

## Contrapositive
Converse + Not
- $p\longrightarrow q\text{ }\implies \text{ }\lnot q\longrightarrow\lnot p$
- *The boolean value of contrapositive is equal to its original statement*
- The contrapositive of “Not statement” is the converse of its original statement

# Prove Methods
## Proof by Cases
- Do different proofs depending different cases

## Proof by contrapositive
Since contrapositive has same true/false value with the original statement, **prove contrapositive to prove the original **

## Proof by contradiction
*Assume what you want to prove is false*, then do some calculations and/or other reasoning to **find something impossible as a result**

# Truth Table
Two statements are logically equivalent if their truth or falsity is exactly same in all cases
- Can do this with Truth Table: Listing all possible values of $p$, $q$ and what the truth value of the compound statements are

| p   | q   | $\lnot q$ | $p\wedge\lnot q$ |
| --- | --- | --------- | ---------------- |
| T   | T   | F         | F                |
| T   | F   | T         | T                |
| F   | T   | F         | F                |
| F   | F   | T         | F                |

# Logical Operation Properties
## deMorgan’s law
$$\lnot(p\wedge q) = \lnot p \lor \lnot q$$
$$\lnot(p\lor q) = \lnot p \wedge \lnot q$$

## Implication Equivalent
$$p\longrightarrow q \iff \lnot p \lor q$$

## Associativity
$$p\lor(q\lor r)\iff (p\lor q)\lor r$$
$$p\wedge(q\wedge r)\iff (p\wedge q)\wedge r$$
## Distributivity
$$p\wedge(q\lor r)\iff (p\wedge q)\lor (p\wedge r)$$
$$p\lor(q\wedge r)\iff (p\lor q)\wedge (p\lor r)$$

## Idempotency
$$p\wedge p \iff p\lor p \iff p$$

## Communitativity
$$p\wedge q = q\wedge p$$
$$p\lor q = q\lor p$$

## Double Inference Rule
$$p\longleftrightarrow q \iff(p \longrightarrow q)\wedge(q \longrightarrow p)$$

## Double Negation
$$\lnot(\lnot p)\iff p$$

## Operation with True and False
Let $T$ be truth statement and $F$ be false statement
- $p\wedge T\iff p$
- $p\wedge F\iff F$
- $p\lor T\iff T$
- $p\lor F\iff p$
- $p\lor\lnot p \iff T$
- $p\wedge\lnot p \iff F$

# Arguments
A series of statements, called the premises followed by another statement called the conclusion 
- Valid *if wherever all the premises are true, so is the conclusion* 

Notation: Premises each in a line, above the conclusion






$P_{1}$
$P_{2}$
$P_{3}$
*-----------*
$\text{Thus, }Q$

Constructing a truth table for the statement involved, and check that whenever the conclusion is always true if premises are all true

## Example
Show validity of following argument

$p\longrightarrow q$
$\lnot p$
*-----------*
$\lnot q$

| $p$ | $q$ | $p\longrightarrow q$ | $\lnot p$ | $\lnot q$ |
| --- | --- | -------------------- | --------- | --------- |
| T   | T   | T                    | F         | F         |
| T   | F   | F                    | F         | T         |
| F   | T   | **T**                | **T**     | **F**     |
| F   | F   | **T**                | **T**     | **T**     |
Since the conlcusion is not always true when all premises are true, this argument is not valid

## Standard Argument
$$
\small
\begin{array} \\
\text{1. Modus Ponens} & \text{2. Modus Tollens} & \text{3. Disjuctive Syllogism} & \text{4. Chain Rule} & \text{5. Resolution}  \\
p\longrightarrow q & p\longrightarrow q & p\lor q & p\longrightarrow q & p \lor r \\
p & \lnot q & \lnot p & q\longrightarrow r & q \lor \lnot r  \\
 \\
\hline
q & \lnot p & q & p \longrightarrow r & p \lor q
\end{array}
$$

- For Chain Rule, it doesn't means that combining premises are not equivalent to the conclusion

---
# Set
Set is some collection of objects, which don't have any type 
- Objects in one set don't have to be all the same type
- Another set can be an object
- Two sets A and B are equal, written A=B, if every element of A is an element of B, every element of B is an element of A 
	- Order and Repetition doesn’t matter: {1,2} = {1,2,2} = {2,1} 
- Notation: writing object in {}, 
	- **Ex)** {1,2}, {3, apple, 6.3}, etc. 
- One can also define sets using some pattern
	- **Ex)** {1,2,3,4…}, {…-2, -1, 0, 1, 2,….} 
- Can also specify a set builder notation 
	- **Ex)** $\{x|x\in\mathbb{R}, 1<x<10\}$

# Empty Set
Defined to be the unique set with **no element**
- $\emptyset$

$\emptyset\neq\{\emptyset\}$
- LHS: No element
- RHS: 1 element

# Subset
If $A$, $B$ are sets, say $A$ is a subset of $B$, and write $A \subseteq B$, if every element of $A$ is and element of $B$
- Even if $A=B$, $A$ is still a subset of $B$
- If $A$ is subset of $B$, but not equal to $B$, $A\subsetneq B$
- $\emptyset$ is **subset of all sets**

The number of subsets of a set is $2^{\text{Number of element}}$

## Power Set
Power set of $A$, is set of all subset of $A$
- $P(A)$

**Ex)**
$P(\{a,b,c\})=  \{\emptyset, \{a\}, \{b\}, \{c\},\{a,b\}, \{b,c\}, \{a,c\}, \{a,b,c\}\}$

$P(\emptyset) = \{\emptyset\}$

# Operation with Sets
## Union( $\cup$ )
If $A$ and $B$ are sets, union of $A$ and $B$, written as $A\cup B$, consists of all elements in $A$ **or** $B$
![[Pasted image 20240214141604.png|300]]

## Intersection( $\cap$ )
If $A$ and $B$ are sets, interesection of $A$ and $B$, written as $A\cap B$, consists of all elements in $A$ **and** $B$
![[Pasted image 20240214141103.png|300]]

# Set Properties
## Idempotency
- $A\cup A = A\cap A = A$
- $A\cup\emptyset = A$
- $A\cap\emptyset = \emptyset$

## Communitative
- $A\cap B = B\cap A$
- $A\cup B = B\cup A$

## Associativity
- $A\cup(B\cup C)=(A\cup B)\cup C$
- $A\cap(B\cap C)=(A\cap B)\cap C$

## Distributivity
- $A\cup(B\cap C)=(A\cup B)\cap (A\cup C)$
- $A\cap(B\cup C)=(A\cap B)\cup (A\cap C)$

# Set Difference
If $A$ and $B$ are sets, $A\text{ \\ } B$, $A-B$ are elements of $A$ which not not in $B$
- If all elements are removed, then it becomes an empty set

# Complement( $A^{C}$ )
If $A\subseteq X$, the complement of $A$ in $X$, written as $A^{C}$ that elements are $X$, but not $A$
- $(A^{C})^{C} = A$
- **deMorgan's Law** for sets
	- $(A\cup B)^{C} = A^{C}\cap B^{C}$
	- $(A\cap B)^{C} = A^{C}\cup B^{C}$
![[Pasted image 20240214141731.png|300]]

# Cartesian Product
Consider **ordered pair**, $(a,b)$
- Order matters
- Two ordered pairs, $(a,b)$ and $(x,y)$ are equivalent if $a=x\text{ \& }b=y$

If $A$ and $B$ are sets, their Cartesian Product, $A\times B$ of all ordered pair
$$\{(a,b)\text{ | }a\in A, b\in B\}$$

**Ex)** if $A=\{a,b\}$ and $B=\{x,y,z\}$
- $A\times B=\{(a,x), (a,y), (a,z), (b,x), (b,y), (b,z)\}$

if $A$ has $n$ elements and $B$ has $m$ elements, then $A\times B$ has $m\times n$ elements

## Properties
- $A\times B\neq B\times A$
- $A\times\emptyset = \emptyset$
- $A\times A =A$
- $A\times(B\times C)\neq (A\times B)\times C$
- $A\times(B\cup C) = (A\times B)\cup(A\times C)$
- $A\times(B\cap C) = (A\times B)\cap(A\times C)$

# Different Types of Sets
## Finite Set
If there is a natural number, $n$, so that $A$ has the same cardinality as $\{1,2,3\dots n\}$ or $A=\emptyset$

## Infite Set
If it is not finite

## Countable
If it is finite or has the same cardinality as $\mathbb{N}$ (Natural Number)
- Ex) $\{a,b\},\mathbb{N}, \mathbb{N}_{\text{even}}, \mathbb{P}$

## Countably Infinite
If it is countable and Infinite (same cardinality as $\mathbb{N}$)
- Ex) $\mathbb{N}, \mathbb{N}_{\text{even}}, \mathbb{P}$
- Countably Infite is a subset of Countable

## Uncountable
If it is not Countable
- $R, R_{+}, (0,1)$
- Can't list all their elements in **a sequence** $\{x_{1}, x_{2}, x_{3}\dots\}$

## If $A$ and $B$ are countable, then $A\cup B$ is also countable
We can write $A$ and $B$ as
$A=\{a_{1}, a_{2}, a_{3}\dots\}$
$B=\{b_{1}, b_{2}, b_{3}\dots\}$
since they are Countable.

Then, define
$f:N\to A\cup B$
   $1\longmapsto a_{1}$
   $2\longmapsto a_{2}$
   $3\longmapsto a_{3}$
   $4\longmapsto a_{4}$
   $\dots$

Then, $N$ and $A\cup B$ have the same cardinality, $A\cup B$ is countable

**Note)**
Using this logic, we can figure out that irrational number is uncountable. 

If irrational number if countable, then since rational number is countable, real number has to be countable. 

However, since real number is uncountable, irrational number can’t be countable, thus it is uncountable (Proof by contradiction) 
- So, there are more irrational numbers than rational numbers

---
# Relation
Well defined relationship between two sets

**Ex)**
1. $<, >, \leq, \geq\dots$

2. Divisibility( "$|$" )
	- For $a$ and $b$, $a$ is divisible by $b$ ($b|a$) if $\exists \text{ }m\in\mathbb{Z}$ such that $b\cdot m=a$

3. Subsets

**4.** Given sets $A$ and $B$, if $\alpha$ is any element of $A$ and $\beta$ is any element of $B$, a relation from $\alpha$ to $\beta$ **is subset of** $A\times B$
	- $R=\{(a,b)\in A\times B\text{ | (relation between }a,b)\}$
	- *Think of things in the subset as things in the relation
	  and things not in the ubset as things not in the relation*

5. Directly Specifying the exact subset is available
	- $A=\{a,b,c\}$, $B=\{x,y,z\}$
	  $R = \{(a,x), (b,x), (a,y), (c,z)\}$ is a valid relation since all ordered pair the in the relation are the element of $A\times B$

6. A relation on $A$ is a relation from $A\times A$

# Properties
## Reflective
If $R$ is a relation on a set $A$, $R$ is reflective if 
$$\text{for all } x\in A, (x,x)\in R$$

## Symmetric
If $R$ is a relation on a set $A$ and $a,b\in A$, $R$ is symmetric if 
$$\text{Whenever }(a,b)\in R, \text{then }(b,a)\text{ must be in } R$$

## Transitive
If $R$ is a relation on a set $A$ and $a,b,c\in A$, $R$ is Transitive *if following statement is satisfied:*
$$\text{if }(a,b)\in R \text{ \& }(b,c)\in R, \text{ then }(a,c)\in R$$

## Anti-Symmetric
If $R$ is a relation on a set $A$ and $a,b\in A$, $R$ is Anti-Symmetric *if following statement is satisfied:*
$$\text{if }(a,b)\in R \text{ \& }(b,a)\in R, \text{ then }a=b$$
- Meaning that $a=b$ has to be true

**Ex)**
$A=\text{Set of People}$
$R=\{(a,b)\in A\times A\text{ | } a\text{ and }b\text{ has the same height}\}$

This is not Anti-Symmetric
- If $\alpha$ and $\beta$ are any two different people who have the same height, then $(\alpha, \beta)\in R$ and $(\beta, \alpha)\in R$, but $\alpha\neq\beta$ since **they are still different people**

# Ex) $R=\emptyset$
For relation $R$ on $A=\{a,b,c\}$, if $R=\emptyset$, then
- $R$ is Symmtric, Trainstive, and Anti-Symmtric

[[1. Basic Logic Fundamentals#Logical Operation#Implication( $p longrightarrow q$ / $p implies q$)|If the hypothesis can’t be true, then the whole implication become true]]

### Proof for Non-Reflectivity
Since $(a,a)\in\emptyset$ is false, $R$ is not Reflective

### Proof for Symmetricity
For Symmetric condition, 
$$\text{If }(a,b)\in \emptyset, \text{then }(b,a)\in \emptyset$$
Since the hypothesis( "$(a,b)\in \emptyset$" ) can't be true, the statement is true.
Thus, $R$ is Symmetric

### Proof for Transitivity
For Transitive condition,
$$\text{If }(a,b)\in \emptyset \text{ \& }(b,c)\in \emptyset, \text{ then }(a,c)\in \emptyset$$
Since the hypothesis( "$(a,b)\in \emptyset \text{ \& }(b,c)\in \emptyset$" ) can't be true, the entire statement is true.
Thus, $R$ is Transitive

### Proof for Anti-Symmetricity
For Anti-Symmetric condition,
$$\text{If }(a,b)\in R \text{ \& }(b,a)\in R, \text{ then }a=b$$
Since the hypothesis( "$(a,b)\in \emptyset \text{ \& }(a,b)\in \emptyset$" ) can't be true, the entire statement is true.

# Ex) Relation Satisfies All Properties 
For any set of $A$, the relation $R$,
$$R=\{(x,y)\in A\times A \text{ | }x=y\}$$
satisfies all four properties.

## Proof for Reflectivity
Consider $(\alpha, \alpha)$ which $\alpha$ is any element of $A$.
- $\alpha=\alpha$ is always true for any $\alpha$

Thus, $R$ is Reflective

## Proof for Symmetricity
Consider $(\alpha, \beta)$ which $\alpha, \beta \in A$.
- From hypothesis of Symmetricity, $\alpha=\beta$
- Then, since $\alpha=\beta$, $\beta=\alpha$ is also true

Thus, $R$ is Symmetric

## Proof for Transitivity
Consider $\alpha, \beta, \gamma\in A$
- From Hypothesis, $(\alpha,\beta)\in R\text{ \& }(\beta,\gamma)\in R$, thus $\alpha=\beta \text{ \& } \beta=\gamma$
- This leads to $\alpha=\gamma$, thus $(\alpha, \gamma)\in R$

Thus, $R$ is Transitive

## Proof for Anti-Symmetricity
Consider $\alpha, \beta\in A$
- From hepothesis, $(\alpha,\beta)\in R\text{ \& }(\beta,\alpha)\in R$, thus $\alpha=\beta \text{ \& } \beta=\alpha$
- This automatically proves $\alpha=\beta$

Thus, $R$ is Anti-Symmetric

# Ex) Relation Satisfies None of Properties
For set $A=\{a,b,c\}$, relation $R$ on $A$,
$$R=\{(a,a), (a,b), (b,a), (b,c)\}$$

## Proof for Non-Reflectivity
$(b,b), (c,c)\not\in R$
Thus, $R$ is not Reflective

## Proof for Non-Symmetricity
$(b,c)\in R, \text{but }(c,b)\not\in R$

Thus, $R$ is not Symmetric

## Proof for Non-Transitivity
$(a,b)\in R\text{ \& }(b,c)\in R, \text{ but }(a,c)\not\in R$

Thus, $R$ is not Transitive

## Proof for Non Anti-Symmetricity
$(a,b)\in R\text{ \& }(b,a)\in R, \text{ but }a\neq b$

Thus, $R$ is not Anti-Symmetric
\
# Equivalent Relation
A relation on set $A$ that is *Reflective*, *Symmetric*, and *Transitive*
- Regardless of Anti-Symmetric
- If $R$ is an equivalence on a set $A$, write $a$ ~ $b$, if $(a,b)\in R$

**Ex)**
$A=\mathbb{Z} \text{ (integer)}$, $R=\{(a,b)\text{ | } (a,b\text{ are both odd}) \text{ or } (a,b\text{ are both even})\}$

$A=\mathbb{Z} \text{ (integer)}$, $R=\{(a,b)\text{ | } a-b \text{ is divisible by 3}\}$

## Equivalent Class
An equivalent relation on a set $A$ "divides up the set $A$ into different classes"

If $R$ is Equivalence Relation on a set $A$ and $x\in A$, define the equivalence class of $x$, $\bar{x}$, to be 
- $\bar{x}=\{y\in A\text{ | }x$ ~ $y \text{ }(\text{a.k.a }(x,y)\in R)\}\longrightarrow\{\text{Set of all }y\text{ satisfy }x$ ~ $y\}$
- Some equivalent classes are exactly the same

**Ex)**
For Equivalent Relation, $A=\mathbb{Z} \text{ (integer)}$, $R=\{(a,b)\text{ | } a-b \text{ is divisible by 3}\}$

$\dots$
Equivalent class of 1, $\bar{1}=\{\dots-5, -2, 1, 4, 7\dots\}$
Equivalent class of 2, $\bar{2}=\{\dots-4, -1, 2, 5, 8\dots\}$
Equivalent class of 3, $\bar{3}=\{\dots-3, 0, 3, 6, 9\dots\}$
Equivalent class of 4, $\bar{4}=\{\dots-5, -2, 1, 4, 7\dots\}$
$\dots$

Thus, $\bar{1}=\bar{4}$ and so on

## Properties
If $R$ is and Equivalent Relation on a set $A$, then
### 1. For any $x\in A, x\in \bar{x}$
**Proof)**
$R$ is reflective, thus for any $x\in A$, $(x,x)\in R$

Therefore, $x\in \bar{x}$
### 2. For any $x,y\in A$, $\bar{x}=\bar{y}\text{ iff }(x,y)\in R$
**Proof)**
$\bar{x}=\bar{y}\implies(x,y)\in R$
- From property 1, $x\in \bar{x}$ and $y\in \bar{y}$
  Since $\bar{x}=\bar{y}$, $y\in \bar{x}$
  From the definition of Equivalent Class, since $y\in \bar{x}$, $(x,y)\in R$
	
$(x,y)\in R\implies\bar{x}=\bar{y}$
- Let $\alpha$ is **any element** in $\bar{x}$, $\alpha\in \bar{x}$
  By the definition of Equivalent Class, $(x,\alpha)\in R$
  Since $R$ is symmetric, $(\alpha,x)\in R$
  From hypothesis, since $(\alpha,x)\in R\text{ \& }(x,y)\in R$, $(\alpha,y)\in R$ as $R$ is Transitive
  Since $R$ is symmetric, $(y,\alpha)\in R$
  By the definition of Equivalent Class, $\alpha\in \bar{y}$
  Thus, all elements in $\bar{x}$ are the elements in $\bar{y}$.
  If we do the same thing start from $\bar{y}$, then we can prove that all elements
  in $\bar{y}$ are the elements in $\bar{x}$
  Thus, $\bar{x}=\bar{y}$

Since both direction satisfy, the original statement is true

### 3. For any $x,y\in A$, either $\bar{x}=\bar{y}$  or  $\bar{x}\cap \bar{y}$
**Proof)**
There are only two cases: $(x,y)\in R$ and $(x,y)\not\in R$

Case 1: If $(x,y)\in R$
- From Property 2, $\bar{x}=\bar{y}$
	  
Case 2: If $(x,y)\not\in R$
- We want to prove "If $(x,y)\not\in R$, then $\bar{x}\cap \bar{y}=\emptyset$"
  Proof by Contradiction: Assume $\exists \text{ }m$ such that $\bar{x}\cap \bar{y}=m$.
  Then, $m\in \bar{x}$ and $m\in \bar{y}$, thus $(x,m)\in R$ and $(y,m)\in R$
  Since $R$ is Symmetric, $(m,y)\in R$
  Since $R$ is Transitive, from $(x,m)\in R$ and $(m,y)\in R$, we can get $(x,y)\in R$
  However, this is contradictive since $(a,y)\in R$ as hypothesis.
  Thus, there is no such $m$ that satisfy $\bar{x}\cap \bar{y}=m$
  Therefore, "If $(x,y)\not\in R$, then $\bar{x}\cap \bar{y}=\emptyset$" by proof by contradiction

All this tells us that an Equivalent Relation on $A$ divide up the set $A$ into **non-overlapping parts**

# Quotient Set
If $R$ is an Equivalent Relation on a set $A$, the Quotient Set of $A$ by $R$, written as 
$$A/R\text{ or }A/N$$
is simply the **set of all Equivalent Classes**
- $\{\bar{x}\text{ | }x\in A\}$

Quotien Sets can be used to construct certain complex "spaces"
- Ex) Points which satisfy $x^{2}+y^{2}=r^{2}\implies$ circle


**Ex)**
For $A=\mathbb{Z} \text{ (integer)}$, $R=\{(a,b)\text{ | } a-b \text{ is divisible by 3}\}$

Then, $A/R=\{\dots \bar{0}, \bar{1}, \bar{2}, \bar{3}\dots\}$. Since all Equivalence are equal to either $\bar{0}, \bar{1}, \bar{2}$
$$A/R=\{\bar{0}, \bar{1}, \bar{2}\}$$

**Ex)**
For $A=\{a,b,c\}, R=\{(a,b)\text{ | }a=b\}$

Then, $\bar{a}=\{a\},\bar{b}=\{b\}, \bar{c}=\{c\}$
$$A/R=\{\bar{a}, \bar{b}, \bar{c}\}=\{\{a\}, \{b\}, \{c\}\}$$
Which is not equivalent to $A$

# Partial Order
Relation $R$ in set $A$ that is **Reflective**, **Transitive**, and **Anti-Symmetric**

**Ex)** Is Partial Order
1. $R=\{(a,b)\text{ | } a\leq b\}$

2. $A=\mathbb{N}\text{ (Natural Num)}$, $R=\{(a,b)\text{ | }a\text{ divides } b\}$

**Ex)** Is not Partial Order
$A=\mathbb{Z}\text{ (Integer) }$, $R=\{(a,b)\text{ | }a\text{ divides } b\}$
- Not Anti-Symmetric

## Total Order
If $R$ is Partial Order on $A$, say elements $x,y\in A$ are **comparable** if either
$$(x,y)\in R\text{ or }(y,x)\in R$$

Say $R$ is Total Order $\text{iff}$ *any 2 elements are comparable*
- i.e. For all $x,y$, either $(x,y)\in R\text{ or }(y,x)\in R$

## Hasse Diagram
Make a diagram with the elements, of $A$, $a,b$, drawing a line from $a$ up to $b$
- For drawing $(a,b)$, $a$ has to be lower than $b$

**Ex)** 
$A=\{1,2,3,5,6,12,15\}$, $R=\{(a,b)\text{ | }a\text{ divides } b\}$
![[Pasted image 20240727111527.png|200]]

$A=P(\{a,b,c\})$, $R=\{a,b\in A\text{ | }a\subseteq b\}$
![[Pasted image 20240727111817.png|200]]

## Maximum & Minimum
If $R$ is  Paritial Order on set $A$, an element $x$ is called

**Maximum:** For any $y\in A$, $(y,x)\in R$
- All other elements in $A$ locate lower than $x$ in Hasse Diagram

**Minimum:** For any $y\in A$, $(x,y\in R)$
- All other elements in $A$ locate higher than $x$ in Hasse Diagram

### Maximum or Minimum are Unique
If $m_{1}$ and $m_{2}$ are both maximum(or both minimum), then $m_{1}=m_{2}$

**Proof)**
Since $m_{1}$ is maximum, $(m_{1}, m_{2})\in R$
Since $m_{2}$ is maximum, $(m_{2}, m_{1})\in R$

Since $R$ is Partial Order, it is Anti-Symmetric, thus $m_{1}=m_{2}$

## Maximal & Minimal
If $R$ is  Paritial Order on set $A$, an element $x$ is called

**Maximal:** For any $y\in A$, if $(x,y)\in R$, then $x=y$ 
- No element above $x$

**Minimal:** For any $y\in A$, if $(y,x)\in R$, then $x=y$ 
- No element below $x$

### If $m$ is Maximum, then it is Maximal (Same for Minimum and Minimal)
Suppose $m$ is Maximum of $A$. we want $m$ to be Maximal. 
- To be Maximal, we need to show that if there is some element $x$ so that $(m,x)\in R$, then $m=x$.

So suppose there is some $x$ so that $(m,x)\in R$ But since $m$ is maximum, $(x, m)\in R$
- By Anti-Symmetric, $m=x$

---
# Function
Function from set $A$ to set $B$ is defined to be relation from $A$ to $B$ so that for any $x$ in $A$, there is **exactly one** $y$ in $B$ that $(x,y)\in f$
- $A$ is called *domain*
- $B$ is called *codomain*\

![[Pasted image 20240727120638.png|300]]

Notation)
$f:A\to B$

$f:A\to B$
   $\text{(input 1)}\longmapsto \text{output 1}$
   $\text{(input 2)}\longmapsto \text{output 2}$
   $\dots$

# Properties
## 1-1(One to one)
Every single input leads to different output
- If input is different, then output is different
- If $f(m_{1})=f(m_{2})$, then $m_{1}=m_{2}$

## Onto
Every single elements in codomain, there is at least one input that corresponds to it
- For all $b\in B$, $\exists \text{ }a\in A$ such that $f(a)=b$
- *Codomain is equivalent to range*

# When are the functions equal?
1. Their Domain and Codomain are equal
2. And their values are equal on all inputs

# Composite
For function $f$ and $g$, if $f: A\to B$ and $g:B\to C$, then
$$g(f(x)): A\to C$$
is a composite of $f$ and $g$
- Also written as $g*f(x) \text{ or } (g*f)(x)$
- If both $f$ and $g$ are 1-1 or onto, then composite is also 1-1 or onto

## Proof for 1-1
Let $f$ and $g$ are 1-1. We need to prove for any $a_{1}, a_{2}\in A$,
$$\text{If }g(f(a_{1}))=g(f(a_{2}))\text{ , then } a_{1}=a_{2}$$

If $g(f(a_{1}))=g(f(a_{2}))$, then $f(a_{1})=f(a_{2})$ since $g$ is 1-1

If $f(a_{1})=f(a_{2})$, then $a_{1}=a_{2}$ since $f$is 1-1

Thus, $g(f(x))$ is 1-1

## Proof for Onto
Let $f$ and $g$ are Onto. We need to prove for all $c\in C$, 
$$\text{There is some } a\in A \text{ so that } g(f(a))=c$$

Since $g$ is onto, there is some $b\in B$ so that $g(b)=c$ 

Then, since $f$ is also onto, there is some $a \in A$ that $f(a) = b$ 

Thus, for $c\in C$, there is some $a\in A$ that $g(f(a)) = g(b) = c$


# Inverse Function
If $f:A\to B$ is a function, an inverse for $f$ is a function $g:B\to A$ for so that all $a\in A$,
$$g(f(a))=a\text{ \& }f(g(b))=b$$
- We need to prove **both directions** of $g(f(a))=a\text{ \& }f(g(b))=b$
- If inverse exist, then **it is unique**

## The function satisfy both 1-1 and onto if and only if it has in inverse function
### Direction 1: If $f$ has an inverse function, then $f$ is 1-1 and onto

**For 1-1**, suppose that we have $a_{1}, a_{2}\in A$ so that $f(a_{1})=f(a_{2})$
- We need to prove $a_{1}=a_{2}$

Since $g$ is also a function, $g(f(a_{1}))=g(f(a_{2}))$

Then, since $g$ is an inverse function of $f$, $g(f(a_{1}))=a_{1}$ and $g(f(a_{2}))=a_{2}$
- Thus $a_{1}=a_{2}$

**For onto**, we need to show that for any $b\in B$, there is some $a\in A$ so that $f(a)=b$

Since $g$ is an inverse function, we can define it as $g(b)=a$
- This is valid since $g:B\to A$

Then, $f(a)=f(g(b))=b$

Thus, we found an $a\in A$ so that $f(a)=b$, so $f$ is onto

### Direction 2: If $f$ is 1-1 and onto, then $f$ has an inverse function $g:B\to A$
Since $f$ is onto, for any $b\in B$, there is at least one $a\in A$ so that $f(a)=b$

Why can't there be more than one such $a$? Because $f$ is 1-1, *there can be only one* $a$

So we can define $g(b)$ to be unique element of $a\in A$ so that $g(b)=a$

Therefore, for any $a\in A$, $g(f(a))=a$by how $g$ is defined, and for any $b\in B$, $f(g(b))=f(a)=b$

## Bijection
Function that is 1-1 and onto
- Inverse function of a bijection is also a bijection
- If we have a bijection, $f:A\to b$, we can think of this as a way of uniquely matching each element of $A$ to each element of $B$
	- If there is a bijection $f:A\to B$, then we say that **they have the same cardinality**

# Cardinality
## Cardinality for [[2. Set#Finite Set|Finite Sets]]
If $A$ and $B$ each have a **finite number** of elements, then *they have the same Cardinality iff they have the same number of elements*
### Proof 1 )
Suppose $A=\{a_{1}, a_{2}, \dots a_{n}\}$ and $B:\{b_{1}, b_{2}, \dots b_{n}\}$ have the $n$ elements.

Then define function
$f:A\to B$
   $a_{1}\longmapsto b_{1}$
   $a_{2}\longmapsto b_{2}$
   $\dots$
   $a_{n}\longmapsto b_{n}$

Then, $f$ is bijection, $A$ and $B$ have the same cardinality

### Proof 2 )
[[1. Basic Logic Fundamentals#Proof by contrapositive|Prove by contrapositive]]: If $A$ and $B$ have a different number of elements, then $A$ and $B$ can't have the same cardinality

Suppose $A=\{a_{1}, a_{2}, \dots a_{m}\}$ and $B:\{b_{1}, b_{2}, \dots b_{n}\}$
- If $m>n$, then there is no function $f:A\to B$ that is 1-1
- If $m<n$, then there is no function $f:A\to B$ that is onto
Since either case can't have bijection, $A$ and $B$ can't have the same cardinality

## Cardinality for [[2. Set#Infite Set|Infinite Sets]]
Having the same cardinality is [[3. Relation#Equivalent Relation|Equivalence Relation]]
### Reflexive
For any set A, we need to show that $A$ has the same cardinality with A, meaning that we have to find a bijection $f:A\to A$ 
	- Define 
	 $f:A\to A$
		$a\longmapsto a$
	 This is clearly 1-1 and onto, thus it is bijection, they have the same cardinality 

### Symmetric
If $A$ has the same cardinality as $B$, have bijection $f:A\to B$, we need $B$ to have same cardinality as $A$, i.e need a bijection $g:B\to A$
	- Since $f$ is bijection, it will have an inverse, $g$, and we stated that inverse to a bijection is also bijection. Thus $g$ is bijection, they have the same cardinality 

### Transitive
Suppose $A$ has same cardinality as $B$, and $B$ the same as $C$, i.e there are bijection $f_{1}=A\to B$ and $f_{2}=B\to C$ we have to show the existence of bijection $A\to C$ 
	- Compose of $f_{1}$ and $f_{2}$, is also 1-1 and onto, $A$ and $C$ have the same cardinality

**Ex)**
- $A=\mathbb{N}=\{1,2,3\dots\}$ and $B=\{2,4,6\dots\}$, do they have the same cardinality?
Define 
$f:A\to B$
   $x\longmapsto 2x$
- Then this function is 1-1 and onto, thus bijection. They have the same cardinality

- $\mathbb{R}$ and $\mathbb{R}^{+}$ have the same cardinality
- $\mathbb{N}$ and $\mathbb{N}\times\mathbb{N}$ have the same cardinality

