# What are the Real Numbers?
The real numbers are a set $\mathbb{R}$ which has binary operations: **Addition**("$+$") and  **Multiplication**("$\cdot$"), and a relation, **Less Than**("$<$"). 

## Binary Operations
Binary Operation on a set $A$
- A function: $A\times A \rightarrow A$
- Takes two elements from $A$ as inputs and we can get something from $A$ as output

# Axioms for $\mathbb{R}$
Axiom
- Statement or proposition which is regarded as being established, accepted, or self-evidently true
- Fact that we don't prove but consider as true

## Field
### R.1 Associativity of Addition
For all $x,y,z\in\mathbb{R}$
$$x+(y+z)=(x+y)+z$$

### R.2 Commutativity of Addition
For all $x,y,z\in\mathbb{R}$
$$x+y=y+x$$

### R.3 Unitality of Addition
There is an element $0\in\mathbb{R}$ such that
$$\forall \text{ }x\in\mathbb{R},\text{ } x+0=x$$

### R.4 Inverse of Addition
For all $x\in\mathbb{R}$, there is an element $-x\in\mathbb{R}$ such that 
$$x+(-x)=0$$

### R.5 Associativity of Multiplication
For all $x,y,z\in\mathbb{R}$
$$x\cdot(y\cdot z) = (x\cdot y)\cdot z$$

### R.6 Commutativity of Multiplication
For all $x,y,z\in\mathbb{R}$
$$x\cdot y = y\cdot x$$

### R.7 Unitality of Multiplication
There is an element $1\in\mathbb{R}$ such that 
$$\text{For all }x\in\mathbb{R}\text{, }x\cdot1=x$$
and
$$1\neq 0$$

### R.8 Inverse for Multiplication
For all $x\in\mathbb{R}$, if $x\neq 0$, then there is an element $x^{-1}\in\mathbb{R}$ (also written as $\frac{1}{x}$) such that
$$x\cdot(x^{-1})=1$$

### R.9 Distributivity
For all $x,y,z\in\mathbb{R}$
$$x\cdot(y+z)=x\cdot y+x\cdot z$$

## Followings are additional Axioms that gives Totally Ordered Field
### R.10 Order is Transitive
For all $x,y,z\in\mathbb{R}$, 
$$x<y\text{ \& }y<z \implies x<z$$

### R.11 Order is Total
For all $x,y\in\mathbb{R}$, exactly one of the following is true:
- $x=y$
- $x<y$
- $y<x$

### R.12 Addition is Order-Compatible
For all $x,y,z\in\mathbb{R}$, 
$$y<z\implies x+y<x+z$$

### Positive Multiplication is Order-Compatible
For all $x,y,z\in\mathbb{R}$,
$$x>0\text{ \& }y<z\implies x\cdot y<x\cdot z$$

# Further Rules can be proved
## Lemma 1. For any $x,y,z\in\mathbb{R}$, if $x+y=x+z$, then $y=z$
Assume $x+y=x+z$

By $R.4$, there is a $-x\in\mathbb{R}$. Add it to both sides
- $-x+(x+y)=-x+(x+z)$
Then, by Associativity of Addition ($R.1$), 
- $(-x+x)+y=(-x+x)+z$
By Communitativity of addition ($R.2$)
- $(x+(-x))+y=(x+(-x))+z$
By Inverse of Addition ($R.4$)
- $0+y=0+z$
By Communitativity of addition ($R.2$)
- $y+0=z+0$
By Unitiality of Addition ($R.3$)
- $y=z$

### Claim: $1+1\neq 1$
If it was true, then $1+1=1$
Then, $1+1=1+0$ by $R.3$
Then, $1=0$ by lemma 1
$\rightarrow$ This contradicts $R.7$

## Lemma 2. For any $x\in\mathbb{R}, x\cdot {0}=0$
Consider $x\cdot {0}$
	$= x \cdot (0+0)$ by R.3
	$= x\cdot 0+x\cdot 0$ by R.9

So, $x\cdot 0= x\cdot 0 + x\cdot 0$ 
	$x\cdot 0+0 = x\cdot 0+x\cdot 0$ by R.3
	$0=x\cdot 0$ by Lemma 1

## Lemma 3. For any $x,y,z\in\mathbb{R}$ if $x\neq 0$ and $x\cdot y = x\cdot z$ then $y=z$
 Since $x\in\mathbb{R}$ and $x\neq 0$, $x^{-1}\in\mathbb{R}$ by R.8. Multiply this to both sides of $x\cdot y = x\cdot z$, then we can get
  $\implies x^{-1}\cdot(x\cdot y) = x^{-1}\cdot(x\cdot z)$
 
 Then, by Associativity of Multiplication (R.5), 
  $\implies(x^{-1}\cdot x)\cdot y = (x^{-1}\cdot x)\cdot z$
 
 Then, by Inverse for Multiplication (R.8),
 $\implies1\cdot y = 1\cdot z$

Then, by Unitality of Multiplication (R.7),
 $\implies y=z$

## Lemma 4. For any $x,y\in\mathbb{R}$, if $x\cdot y=0$ then $x=0$ or $y=0$
 (Proof By Contrapositive): If its contrapositive is true, then the original statement is true:
 "if $x\neq 0$ and $y\neq 0$, then $x \cdot y\neq0$"

 (Proof By Contradiction): Assume if $x\neq 0$ and $y\neq 0$, then $x \cdot y=0$

 Then, since $x,y\in\mathbb{R}$, there are $x^{-1}, y^{-1}$ by Inverse for Multiplication (R.8) Multiply $x^{-1}$ and $y^{-1}$ to both sides:
 $$x^{-1}\cdot y^{-1}\cdot (x\cdot y) = (x^{-1}\cdot y^{-1})\cdot 0$$

By Associativity of Multiplication (R.5)
$$x^{-1}\cdot (y^{-1}\cdot x)\cdot y = (x^{-1}\cdot y^{-1})\cdot 0$$

 By Commutativity of Multiplication (R.6)
 $$x^{-1}\cdot (x\cdot y^{-1})\cdot y = (x^{-1}\cdot y^{-1})\cdot 0$$

By Associativity of Multiplication (R.5)
$$(x^{-1}\cdot x)\cdot (y^{-1}\cdot y) = (x^{-1}\cdot y^{-1})\cdot 0$$

By Commutativity of Multiplication (R.6)
$$(x\cdot x^{-1})\cdot (y\cdot y^{-1}) = (x^{-1}\cdot y^{-1})\cdot 0$$

By Inverse for Multiplication (R.8)
$$1\cdot 1 = (x^{-1}\cdot y^{-1})\cdot 0$$

By Unitality of Multiplication (R.7)
$$1 = (x^{-1}\cdot y^{-1})\cdot 0$$

By Associativity of Multiplication (R.5)
$$1 = x^{-1}\cdot (y^{-1}\cdot 0)$$

By Lemma 2, 
$$1 = x^{-1}\cdot 0$$

By Lemma 2, 
$$1 = 0$$

This contradicts the Unitality of Multiplication (R.7)

Thus, by proof by contradiction, $x\neq 0$ and $y\neq 0$, then $x \cdot y\neq0$

Since "$x\neq 0$ and $y\neq 0$, then $x \cdot y\neq0$" is true, the original statement is true by proof by contrapositive

## Lemma 5. For any $x\in\mathbb{R}$, $-(-x)=x$
We know $x+(-x)=0$ by R.4
- And we know for $(-x)$, there is $-(-x)$ that satisfy $(-x)+-(-x)=0$

Then, $x+(-x)=(-x)+ -(-x)$
$\implies (-x)+x=(-x)+ -(-x)$ by R.2
$\implies$ $x=-(-x)$ by Lemma 1

## Lemma 6. $-0=0$
 For $-0$, there is some $-(-0)\in\mathbb{R}$ that satisfy 
	 $-0+-(-0)=0$ 
 by R.4. Then by Lemma 5, $-(-0)=0$, thus
	$-0+0=0$
 Then by R.3, 
	$-0+0=-0$
 Therefore, 
	 $-0=0$
## Lemma 7. For any $x, y\in\mathbb{R}$, $(-x)\cdot y=-(x\cdot y)$
$x+(-x)=0$ by R.4 
 $\implies(x+(-x))\cdot y=0\cdot y$

by R.6(LHS) and Lemma 2(RHS)
 $\implies y\cdot(x+(-x))=0$

by R.9
 $\implies x\cdot y+(-x)\cdot y=0$ 

By R.4, for $x\cdot y$, there is some $-(x\cdot y)$ that satisfy $x\cdot y+ -(x\cdot y)=0$
 $\implies x\cdot y+(-x)\cdot y = x\cdot y+ -(x\cdot y)$

By Lemma 1 
 $\implies(-x)\cdot y = -(x\cdot y)$

## Lemma 8. For any $x,y\in\mathbb{R}$, $(-x)(-y)=x\cdot y$
 By Lemma 7, 
	$(-x)\cdot(-y)=-(x\cdot(-y))$

Then, by R.6
	$(-x)\cdot(-y)=-((-y)\cdot x)$

 Meanwhile, by Lemma 7
	$(-y)\cdot x = -(y\cdot x)$

Then we can substitute $-(y\cdot x)$ instead of $(-y)\cdot x$
	$(-x)\cdot (-y) = -((-y)\cdot x)=-(-(y\cdot x))$

Then by Lemma 5 and R.6,
	$-(-(y\cdot x)) = y\cdot x = x\cdot y$

Therefore, 
	$(-x)\cdot(-y)=x\cdot y$

## Lemma 9. If $x_{1},x_{2},y_{1},y_{2}\in\mathbb{R}$ and $x_{1}<x_{2}$ and $y_{1}<y_{2}$ then $x_{1}+y_{1}<x_{2}+y_{2}$
From $x_{1}<x_{2}$ ,  $y_{1}+x_{1}<y_{1}+x_{2}$ by R.12
 $\implies x_{1}+y_{1}<y_{1}+x_{2}$ by R.2

From $y_{1}<y_{2}$ , $x_{2}+y_{1}<x_{2}+y_{2}$ by R.12
 $\implies y_{1}+x_{2}<x_{2}+y_{2}$ by R.2

Then, by R.10 $x_{1}+y_{1}<x_{2}+y_{2}$

## Lemma 10. If $x<y$, then $-y<-x$
By R.12, we can add $-x$ to both sides
	$(-x)+x<(-x)+y$

Then by R.2 and R.4
	$(-x)+x = x+(-x) = 0$

Thus, 
	$0<(-x)+y$

Then, by R.12, we can add $-y$ to both sides
	$(-y)+0<(-y)+((-x)+y)$

Then, by R.2 and R.1
$(-y)+((-x)+y)=((-y)+(-x))+y=((-x)+(-y))+y = (-x)+((-y)+y)$

Then, by R.2 and R.4
	$(-x)+((-y)+y)=(-x)+(y+(-y))=(-x)+0$

Thus, 
$(-y)+0<(-x)+0$
	
Then, by R.3
	$(-y)+0=-y, (-x)+0=-x$

Therefore, if $x<y$, then
	$-y<-x$

## Lemma 11. $0<1$
By R.11, one of $0=1$ or $0<1$ or $1<0$ is true
By R.7, we know $0\neq1$, thus either $0<1$ or $1<0$
(Proof By Contradiction) Assume $1<0$
By Lemma 10, $-0<-1$
By Lemma 6, $-0=0$, thus $0<-1$
- Since -1 is positive, by R.13, we can multiply it at both side
- $0\cdot(-1)<(-1)(-1)$
By Lemma.2(LHS) and Lemma.8(RHS)
- $0<1$

This indicates that $0<1$ and $1<0$ are both true, which contradicts R.11. Thus, the initial assumption can't be true. Therefore, the only left possibility is $0<1$

## Lemma 12. If $x>0$ then $x^{-1}>0$
By Lemma 11,  $0<1$

By R.8, for $x$, there is $x^{-1}\in\mathbb{R}$ such that $x\cdot(x^{-1})=1$. Then,
 $\implies 0<x\cdot(x^{-1})$

And again by R.8, we can multiply $x^{-1}$ to both sides,
$\implies (x^{-1})\cdot0<(x^{-1})\cdot x \cdot(x^{-1})$

By R.6 and R.8(RHS)
$\implies (x^{-1})\cdot 0< (x^{-1})\cdot x \cdot(x^{-1}) = x\cdot (x^{-1}) \cdot(x^{-1}) = 1\cdot (x^{-1})$

By Lemma 2 (LHS) and R.7
$\implies (x^{-1})\cdot 0=0<1\cdot (x^{-1})=(x^{-1})$

Therefore
$\implies 0<x^{-1}$

# Upper Bound
**Notation)**
$$x\leq y \text{ if } x=y \text{ or }x<y$$

If $S$ is a subset of $\mathbb{R}$, an element $b\in\mathbb{R}$ is said to be an **"Upper Bound"** for $S$ if
$$\forall \text{ }x\in S,\text{ } x\leq b$$
- We say $S$ is bounded above if there is some upper bound for $S$
- Upper Bounds are not unique

Every element in $\mathbb{R}$ is an upper bound for $\emptyset$ 
- There is no element in $\emptyset$, thus hypothesis of the statement is always false, the entire statement is always true

$\mathbb{R}, \mathbb{N}$ has no upper bound

## Least Upper Bound
If $S\subseteq \mathbb{R}$, a **"Least Upper Bound"** for $S$ is an element $\mathscr{l}\in\mathbb{R}$ such that
- $\mathscr{l}$ is upper bound of $S$
- If $b$ is any upper bound of $S$, then $\mathscr{l}\leq b$
- Notation: $\mathscr{l}=\text{sup}(S)$

Not necessarily in $S$
- $\{x\in\mathbb{R}:0<x<1 \} \implies$ 1 is a least upper bound

$\emptyset$ doesn't have any least upper bound

## Lemma 13. $\leq$ is partial order
Reflexive: $\forall \text{ }x\in\mathbb{R}, x\leq x$
Transitive: $\forall \text{ }a,b,c\in\mathbb{R}, \text{ if }a\leq b\text{ and }b\leq c, \text{ then }a\leq c$
Anti-Symmetric: $\forall \text{ }a,b\in\mathbb{R}, \text{ if }a\leq b\text{ and }b\leq a\text{, then }a=b$

## Lemma 14. $\forall \text{ }x\in\mathbb{R}, x-1<x<x+1$


# Natural Number, $\mathbb{N}$
Define Natural Number $\mathbb{N}$ as the set, $\{1,1+1, 1+1+1\dots\}$

## Lemma 15. Each of numbers in the $\mathbb{N}$ is Distinct, Positive and if $k\in\mathbb{N}$, so is $k+1$


## Lemma 16. Least Upper Bound is Unique
I.e. if $\mathscr{l}_{1}$ and $\mathscr{l}_{2}$ are both least upper bounds for $S$, then $\mathscr{l}_{1}=\mathscr{l}_{2}$
- Since $\mathscr{l}_{1}$ is least upper bound and $\mathscr{l}_{2}$ is still a upper bound, $\mathscr{l}_{1}\leq\mathscr{l}_{2}$
- Since $\mathscr{l}_{2}$ is least upper bound and $\mathscr{l}_{1}$ is still a upper bound, $\mathscr{l}_{2}\leq\mathscr{l}_{1}$
- By Lemma 13, $\mathscr{l}_{1}=\mathscr{l}_{2}$


# Completeness Axioms
The 13 axioms we have so far also apply to the rational numbers, so from this, we could see that these axioms alone can't give us
- "The real number $\sqrt{ 2 }$"
- I.e. A number $x$ so that $x\cdot x=2$

## R.14 $\forall \text{ }S\subseteq \mathbb{R}$ that is non-empty and bounded above, $S$ has a Least Upper Bound
$\implies$ It turns that one can prove there is a unique set which satisfies these 14 axioms

# Results using 14 axioms
## Prop 17. $\mathbb{N}$ is not bounded above $\mathbb{R}$
I.e. there is no $x\in\mathbb{R}$ such that $\forall \text{ }n\in\mathbb{N}, n\leq x$

Proof by Contradiction: Suppose we have some upper bound

By R.14, since $\mathbb{N}$ is non-empty ($1\in\mathbb{N}$), and by assuption, it's bounded, $\mathbb{N}$ has a least upper bound, $\mathscr{l}=\text{sup}(\mathbb{N})$

Consider $\mathscr{l}-1$. Since $\mathscr{l}-1<\mathscr{l}$ and $\mathscr{l}=\text{sup}(\mathbb{N})$, $\mathscr{l}-1$ cannot be upper bound for $\mathbb{N}$
- There is some $n\in\mathbb{N}$ so that $n\nleq \mathscr{l}-1\text{ }(\mathscr{l}-1<n)$

Add 1 to both side $\implies \mathscr{l}<n+1$
- This contradicts since $n+1$ is also natural number, $\mathscr{l}$ is not an upper bound for $\mathbb{N}$

## Prop 18. Archimedean Property of $\mathbb{R}$
For any $a,b\in\mathbb{R}$ if $0<a<b$, then there is some $n\in\mathbb{N}$ so that $n\cdot a>b$

Suppose for Contradiction, no such $n$ exists, so by totality $\forall \text{ }n\in\mathbb{N}$, $n\cdot a\leq b$

Since $a>0$, $a^{-1}$ exists and $a^{-1}>0$ by Lemma 12, $(n\cdot a)\cdot a^{-1}=n\leq b\cdot a^{-1}$
- This indicates $\forall \text{ }n\in\mathbb{N}\text{ , }n\leq b\cdot a^{-1}$, which means $b\cdot a^{-1}$ is an upper bound of $\mathbb{N}$. This contradicts prop 17

Therefore, proof by contradiction, there must be $n\in\mathbb{N}$ so that $n\cdot a>b$

## Lemma 19. Suppose that $S$ and $T$ are non-empty bounded-above sets of real numbers such that $S\subseteq T$, then $\text{sup}(S)\leq \text{sup}T$
Let $x$ be an element of $S$. SInce $S\subseteq T, x\in T$ and since $\text{sup}(T)$ is an upper bound for $T$, $x\leq \text{sup}(T)$. THus, $\text{sup}(T)$ is an upper bound for $S$. Thus, since $\text{sup}(S)$ is the least upper bound for $S$, $\text{sup}(S)\leq \text{sup}(T)$

## Lemma 20: For any 2 real numbers, $x$ and $y$, if $x<y$, there is some real number $z$ so that $x<z<y$
Take $z=\frac{x+y}{2}$ (Exercise)

## Lemma 21: If $F\subseteq\mathbb{R}$ is non-empty and finite, then $\text{sup}(F)$ exists and equal to the largetst element in $F$
By Totality, each pair of elements $a,b\in F$ has either $a<b$ or $b<a$
- If we compare all the pairs, and we get that $F$ consists of elements
- $a_{1}<a_{2}<a_{3}\dots<a_{n}$

Claim that $\text{sup}(F)=a_{n}$
- It is an upper bound since all other elements are smaller than $a_{n}$
- Any $b\in\mathbb{R}$ is any upper bound for $F$, then $a_{n}\leq b$ since $a_{n}\in F$

So, $a_{n}$ is a least upper bound for $F$

So, for finite set, the $\text{sup}$ always *exists* and *is in the set*

**For Infinite set,** the $\text{sup}$ either
1) May not exist
	- $\mathbb{N}$
2) May exist and be in the set
	- $\text{sup}(x\in\mathbb{R}:0\leq x\leq 1)=1$
3) May exist an not be in the set
	- $\text{sup}(x\in\mathbb{R}:0< x< 1)=1$
	- First, $1$ is an upper bound, since by definition of the set
		- Suppose for contradiction, $b$ is an upper bound and $b\leq 1$, then by Lemma 20, $\exists \text{ }z\in\mathbb{R}$ so that $b<z<1$. This contradicts $b$ being an upper bound 
		- So, any upper bound is $\geq 1$, so 1 is least upper bound

# Lower Bound
If $S\subseteq \mathbb{R}$
1) A lower bound for $S$ is an element $b\in\mathbb{R}$ such that $\forall \text{ }x\in S, b\leq x$
2) $S$ is bounded below if there is lower bound for it
3) The greatest lower bound for $S$ is element $\mathscr{l}\in\mathbb{R}$ such that
	1) It is a lower bound for $S$
	2) For any lower bound $b$ of $S$, $b\leq\mathscr{l}$

If $\exists \text{ }$ lower bound, it is unique and we write $\text{inf}(s)=\mathscr{l}$

## Prop 22. If $S\subseteq \mathbb{R}$ is non-empty and bounded, $\text{inf}(S)$ exists
Let $L=\{\text{Set of lower bound}\}$ and take $a=\text{sup}(L)$ and show this is the $\text{inf}$ of $S$

Let $L=\{a\in\mathbb{R}:a\text{ is a lower bound for }S\}$
 $\implies$ it is Non-empty by assumption
 $\implies$ *Have to prove bound above, then we can use R.14*

Since $S$ is non-empty, let $s\in S$. Claim it is an upper bound for $L$. Indeed by definition, $a\in L$, $a\leq s$, \therefore $L$ is bounded above
- By R.14, $c=\text{sup}(L)$ exists

Then, we want to show that $c=\text{inf}(S)$
  $\implies$ i) Show $c$ is lower bound
  $\implies$ ii) Show $c$ is the greatest lower bound

For i),
Suppose for contradiction that $c$ is not a lower bound for $S$. Thus, $\exists \text{ }x\in S$ such that $x<c$

But $\forall \text{ }a\in L$, $a\leq x$ since $x\in S$. Thus $x$ is an upper bound for $L$

This and $x<c$ contradicts $c$ being the least upper bound of $L$. By contradiction, $c$ is $\text{inf}(S)$

For ii),
This is immediate since $c$ is upper bound for $L$

# Exercise
## Prove that If $\exists \text{ }$ lower bound, it is unique 

## Prove Prop 22
Could take $-S=\{-x:x\in S\}$, and show it is bounded above