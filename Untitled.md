In this course, function we talk about with be ones whose domain is $\mathbb{R}$ (or some subset of $\mathbb{R}$), and whose codomain is $\mathbb{R}$

# Precise Definition of $\lim_{ x \to a }f(x)$
$\lim_{ x \to a }f(x)$ may...
1) Not exist
2) Exists, but not equal to $f(a)$
3) Is $f(a)$
	- Later we will define $f$ to be continuous if this happens for all $a$

# Why Consider $\lim_{ x \to a }f(x)$?
1) Want to understand this kind of behaviour
2) We can define function be continuous
	- $\lim_{ x \to a }f(x)=f(a)$ gives meaning to "the function" has no breaks or jump
3) Define derivative precisely requires considering limit of function whose value doesn't even exist at that point

# Epsilon-Delta Definition of limit
![[Pasted image 20241011115203.png|250]]
Suppose $f(x)$ is a function
- Whose domain is some subset of $\mathbb{R}$ and codomain $\mathbb{R}$
and $a,L\in\mathbb{R}$, then we say that "the limit of $f(x)$ as $x$ approaches a equals to $L$", and write $\lim_{ x \to a }f(x)=L$ if for all $\epsilon>0$, there exists $\delta>0$ so that for all $x$ such that 
- If $0<|x-a|<\delta$, then $|f(x)-L|<\epsilon$

"No matter how close you want $f(x)$ to set to $L$, you can do this so long as $x$ is sufficiently close to $a$, but except at $x=a$"

**Note)** as with the definition of sequence convergence, the $\delta$ wil vary depending on $\epsilon$

## Example) $\lim_{ x \to 5 }(4x-3)=17$
Rough Work) 
Given any $\epsilon>0$, we need to set $|f(x)-L|<\epsilon$ and we can make $|x-a|$ small

$$|4x-3-17|=|4x-20|=|4| |x-5|<\epsilon$$
$$\implies|x-5|<\frac{\epsilon}{4}$$
Let $\epsilon>0$ and set $\delta=\frac{\epsilon}{4}$
- Let $x$ be such that $0<|x-5|<\delta$

Then consider $|f(x)-17|$
$$=|4x-3-17|=|4x-20|=4 |x-5|<4\delta=4\cdot\left( \frac{\epsilon}{4} \right)=\epsilon$$

So since $\epsilon$ was arbitrary, we have shown that $\lim_{ x \to 5 }(4x-3)=17$

**Note)**
- **Let** is indicating that some value is arbitrary and **set** is fixing some value

## Example)
If $f(x)$
- $5x\text{ }(x\in\mathbb{Q})$
- $0\text{ }(x\not\in \mathbb{Q})$
Does $\lim_{ x \to a }f(x)$ exist some $a$'s?
- One can show that it doesn't exist for any $a\neq{0}$
- And it does exist for $a=0$

Claim: $\lim_{ x \to 0 }f(x)=0$
Given $\epsilon>0$, let $\delta=\frac{\epsilon}{5}$
Suppose $x$ is such that $0<|x-a|<\delta$, then there are two cases, either $x$ is rational or irrational

i) $x$ is irrational
$$|f(x)-0|=|0-0|=0<\epsilon$$

ii) $x$ is rational
$$|f(x)-0|=|5x-0|=5|x|<5\delta=5\cdot\left( \frac{\epsilon}{5} \right)=\epsilon$$

Regardless $x$ being rational or irrational, if $0<|x-a|<\delta$, then $|f(x)-0|<\epsilon$, 
so since $\epsilon$ is an arbitrary, $\lim_{ x \to 0 }f(x)=0$

Note) Even if this function is defined as $f(0)\neq {0}$, this definition would still work since $0<|x-0|$, thus $0<|x|$
- It only cares points near 0, not at 0

## Example) What is $\lim_{ x \to 0 }|x|$?
Let $\epsilon>0$, set $\delta=\epsilon$

Let $x$ such that $0<|x-0|<\delta$
- We need $|f(x)-0|<\epsilon$
- We can have $x>0$ or $x<0$

i) $x>0$, $|f(x)-0|=|f(x)| = |x|<\delta=\epsilon$

ii) $x<0$, $|f(x)-0| = |-x|=|x|<\delta=\epsilon$

So in all cases, $|f(x)-0|<\epsilon$

Since $\epsilon$ is arbitrary, this shows $\lim_{ x \to 0 }|x|=0$

# Theorem 39. Sequence Criterion for Function Convergence
Relationship between Sequence Convergence and Function Convergence

Let $a,L\in\mathbb{R}$. Suppose $f(x)$ is a function. 
Then $\lim_{ x \to a }f(x)=L$ **iff** for any sequence $\{x_{n}\}$ which converges to $a$, $\{f(x_{n})\}$ converges to $L$
- No $\{x_{i}\}$ equals $a$

## Forward Proof)
Assume $\lim_{ x \to a }f(x)=L$ and we have sequence $\{x_{n}\}$ which converges to $a$, we need to show $\{f(x_{n})\}$ converges to $L$

Let $\epsilon>0$
i) Then, since $\lim_{ x \to a }f(x)=L$, there exists somce $\delta$ so that if $0<|x-a|<\delta$, $|f(x)-L|<\epsilon$

ii) So then, since $\{x_{n}\}$ converges to $a$, there is some $K$ so that $\forall \text{ }n>K$, $|x_{n}-a|<\delta$

Then for $n>K$, since $|x_{n}-a|<\delta$, $|f(x_{n})-L|<\epsilon$ by i)

So, indeed $\{f(x_{n})\}$ converges to $L$

## Backward Proof)
Proof by Contrapositive)
- If $\lim_{ x \to a }f(x)\neq L$, then there exists a sequence $\{x_{n}\}$ with $\forall \text{ }n\in\mathbb{N}, x_{n}\neq a$, $\lim_{ n \to \infty }x_{n}=a$, and $\lim_{ n \to \infty }f(x_{n})\neq L$

What does hypothesis mean
- There exists $\epsilon>0$ so that $\forall \text{ }\delta>0$, there exists some $x$ with $0<|x-a|<\delta$ but $|f(x)-L|\geq\epsilon$

If we take $\delta=1$, there is some $x$ call it $x_{1}$ so that $0<|x_{1}-a|<1$, but $|f(x_{1})-L|\geq\epsilon$

Let's try with smaller $\delta$ because we want $x$ gets closer to $a$
- So then, if we take $\delta=\frac{1}{2}$, there exists some $x$, call it $x_{2}$, so that $0<|x_{2}-a|<\frac{1}{2}$, but $|f(x_{2})-L|\geq\epsilon$
- Do this for every $n\in\mathbb{N}$, if we take $\delta=\frac{1}{n}$, there exists some $x$, call it $x_{n}$, so that $0<|x_{n}-a|<\frac{1}{n}$, but $|f(x_{n})-L|\geq \epsilon$

1) Since, for all $a\in\mathbb{N}$, $0<|x_{n}-a|$, we have $x_{n}\neq a$

2) We also need $\lim_{ n \to \infty }x_{n}=a$, but since $\forall \text{ }n\in\mathbb{N}$, $|x_{n}-a|<\frac{1}{n}$
	- $a-\frac{1}{n}<x_{n}<a+\frac{1}{n}$
	- Then, by sequeeze theorem, $\lim_{ n \to \infty }x_{n}=a$

3) And, since we have some $\epsilon>0$ such that $\forall \text{ }n\in \mathbb{N}$, $|f(x_{n})-L|\geq\epsilon$
	- We have $\lim_{ n \to \infty }f(x_{n})$ cannot be $L$

Thus, by 1), 2), and 3), contrapositive statement is true, the original statement is true by proof by contrapositive

# Theorem 40. Arithmetic Theorem for Function Limit

For any $a,L, M\in\mathbb{R}$, functions $f(x)$ and $g(x)$ such that $\lim_{ x \to a }f(x)=L$ and $\lim_{ x \to a }g(x)=M$
## 1. $\lim_{ x \to a }x=a$
Let $\epsilon>0$ and set $\delta=\epsilon$

Let $x$ such that $0<|x-a|<\delta$

Consider $|f(x)-a|$
$=|x-a|<\delta=\epsilon$
	$\therefore |f(x)-a|<\epsilon$

Since $\epsilon>0$ is arbitrary, $\lim_{ x \to a }x=a$ 

## 2. $\lim_{ x \to a }k=k$
Let $\epsilon>0$, set $\delta=\epsilon$
- In fact, $\delta$ can be any real number

Let $s$ such that $0<|x-a|<\delta$

Consier $|f(k)-k|$
$=|k-k|=0<\epsilon$
- $|f(x)-k|<\epsilon$

Since $\epsilon$ is arbitrary, $\lim_{ x \to a }k=k$
## 3. For any $c\in\mathbb{R}$, if $\lim_{ x \to a }f(x)=L$, then $\lim_{ x \to a }cf(x)=cL$

Since $\lim_{ x \to a }f(x)=L$, $\forall \text{ }\epsilon>0$, $\exists \text{ }\delta>0$ such that $\forall \text{ }x$ such that $0<|x-a|<\delta$, $|f(x)-L|<\frac{\epsilon}{|c|}$
Let $\epsilon>0$
Let $x$ such that $0<|x-a|<\delta$

Consider $|cf(x)-cL|$
- $=|c||f(x)-L|<|c|\cdot\frac{\epsilon}{|c|}=\epsilon$

## 4. $\lim_{ x \to a }(f(x)+g(x))=L+M$
Rough Work)
Would need to set $|f(x)+g(x)-(L+M)|\leq|f(x)-L|+|g(x)-M|$
- We can set both are less than or equal to $\frac{\epsilon}{2}$

Let $\epsilon>0$
Since $\lim_{ x \to a }f(x)=L$, there is some $\delta_{1}$ such that if $0<|x-n|<\delta_{1}$ , $|f(x)-L|<\frac{\epsilon}{2}$

Since $\lim_{ x \to a }g(x)=M$, there is some $\delta_{2}$, such that if $0<|x-n|<\delta_{2}$ , $|g(x)-M|<\frac{\epsilon}{2}$

Let $\delta=\min(\delta_{1}, \delta_{2})$

Suppose that $0<|x-n|<\delta$
Consider $|f(x)+g(x)-(L+M)|$
$$|f(x)+g(x)-(L+M)|\leq|f(x)-L|+|g(x)-M|$$
$$<\frac{\epsilon}{2}+\frac{\epsilon}{2}=\epsilon$$

Since $\epsilon>0$ is arbitrary, $\lim_{ x \to a }(f(x)+g(x))=L+M$


## 5. $\lim_{ x \to a }f(x)g(x)=LM$
Suppose $\{x_{n}\}$ is some sequence such that $\forall \text{ }n\in\mathbb{N}, x_{n}\neq a$ and $\lim_{ n \to \infty }x_{n}=a$
- We need to show that $\lim_{ n \to \infty }f(x_{n})g(x_{n})=LM$

By forward direction of Sequence Criterion Theorem,
- $\lim_{ n \to \infty }f(x_{n})=L$
- $\lim_{ n \to \infty }g(x_{n})=M$

Then, by the Arithmetic Theorem of Sequence Convergence, 
- $\lim_{ n \to \infty }f(x_{n})g(x_{n})=LM$

Then, by the backward direction of Sequence Criterion Theorem, 
- $\lim_{ n \to \infty }f(x)g(x)-LM$

## 6. If $M\neq 0$ and $\forall \text{ }x\in\mathbb{R}, g(x)\neq{0}$, then $\lim_{ x \to a }\frac{f(x)}{g(x)}=\frac{L}{M}$
Suppose $\{x_{n}\}$ is some sequence such that $\forall \text{ }n\in\mathbb{N}, x_{n}\neq a$ and $\lim_{ n \to \infty }x_{n}=a$
By forward direction of SCFC,
- $\lim_{ x \to a }g(x_{n})=M$

Then, by Arithmetic Theorem of Sequence Convergence, 
- $\lim_{ x \to a }\frac{1}{g(x_{n})}=\frac{1}{M}$

By, backward direction of SCFC,
- $\lim_{ x \to a }\frac{1}{g(x)}=\frac{1}{M}$

By Rule 5 of Arithmetic Theorem for Function Limit, 
$\lim_{ x \to a }\frac{f(x)}{g(x)}=\lim_{ x \to a }f(x)\cdot\frac{1}{g(x)} =\lim_{ x \to a }f(x)\cdot \lim_{ x \to a }\frac{1}{g(x)} =L\cdot\frac{1}{M}=\frac{L}{M}$

# Special Type of Function Limit
1. $\lim_{ x \to a^{-} } f(x)$
2. $\lim_{ x \to a^{+} } f(x)$
3. $\lim_{ x \to \infty }f(x)$
4. $\lim_{ x \to -\infty }f(x)$
How can we change the definition to define those states?
## $\lim_{ x \to a^{-} } f(x)$
$\lim_{ x \to a }f(x)=L$ if for all $\epsilon>0$, there exists $\delta>0$ so that for all $x$ such that 
- If $0<a-x<\delta$, then $|f(x)-L|<\epsilon$

## $\lim_{ x \to a^{+} }f(x)$
$\lim_{ x \to a }f(x)=L$ if for all $\epsilon>0$, there exists $\delta>0$ so that for all $x$ such that 
- If $0<x-a<\delta$, then $|f(x)-L|<\epsilon$

## $\lim_{ x \to \infty }f(x)$
$\lim_{ x \to a }f(x)=L$ if for all $\epsilon>0$, there exists $\delta>0$ so that for all $x$ such that 
- If $\delta<x$, then $|f(x)-L|<\epsilon$

## $\lim_{ x \to -\infty }f(x)$
$\lim_{ x \to a }f(x)=L$ if for all $\epsilon>0$, there exists $\delta>0$ so that for all $x$ such that 
- If $\delta>x$, then $|f(x)-L|<\epsilon$

## Proposition 41
Suppose $f(x)$ is a function, and $a,L\in\mathbb{R}$. Then, 
$$\lim_{ x \to a }f(x)=L\text{ iff }\lim_{ x \to a^{-} }f(x)=L \text{ and } \lim_{ x \to a^{+} }f(x) =L $$

# Continuous Function(cts)
Continuous at Point
- For function $f(x)$, say that it is continuous at $a$, if $f$ defined at $a$ and $\lim_{ x \to a }f(x)=f(a)$

Continuous at Set
- Say $f(x)$ is continuou on a set $A\subseteq \mathbb{R}$ if it is continuous at all pomints of $A$


**Ex)**
$$f(x) = \{^{x\text{ (x}\in\mathbb{Q})}_{o\text{ (x}\not\in\mathbb{Q})}$$
This function is cts at 0, but not at any other point
- $\lim_{ x \to 0 }f(x)=0=f(0)$

## Prop 42. 
$f$ is cts at $a$ iff $f$ is defined at $a$ and $\lim_{ x \to a^{-} } f(x) = \lim_{ x \to a^{+} } f(x)=f(a)$

## Prop 43. Sequence Criterion for Continuity
$f$ is cts at $a$ iff
1) $f$ is defined at $a$
2) For any sequence $\{x_{n}\}$ such that $\lim_{ x \to \infty }x_{n}=a$, $\lim_{ x \to a }f(x)=f(a)$

# Defining More Function
If $f$ and $g$ are functions and $c\in\mathbb{R}$, define new function as follows
1) $cf$ is defined as $(cf)(x)=c\cdot f(x)$
2) $f+g$ is defined as $(f+g)(x)=f(x)+g(x)$
3) $fg$ is defined as $(fg)(x)=f(x)g(x)$
4) For $x$ such tht $g(x)\neq0$, $\frac{f}{g}$ is defined as $\left( \frac{f}{g} \right)(x) =\frac{f(x)}{g(x)}$
5) $f \circ g$ is defined as $(f\circ g)(x) = f(g(x))$

# Theorem 44. Arithmetic Theorem for Continuous Function
Suppose $f,g$ are cts at $a$ and $c\in\mathbb{R}$
1) $f(x)=k$ is cts for all $\mathbb{R}$
2) Indentity Function: $f(x)=x$ is cts for all $\mathbb{R}$
3) $cf$ is cts at a
4) $f+g$ is cts at a
5) $fg$ is cts at a
6) If $\frac{f}{g}$ defined for all $x\in\mathbb{R}$, then $\frac{f}{g}$ is cts at $a$

## Prove 4)
We know
- $\lim_{ x \to a }f(x)=f(a)$
- $\lim_{ x \to a }g(x)=g(a)$

Then, by Limit Arithmetic Theorem, $\lim_{ x \to a }(f(x)+g(x))=f(a)+g(a)$
- So, $f+g$ is cts at $a$

**Note)** Rest can be proved similarly

## Corollary 45
For all polynomial function
$$f(x)=a_{0}+a_{1}x+a_{2}x^{2}\dots a_{n}x^{n}=\sum^{n}_{i=1}a_{i}x^{i} $$
is cts for all points

# Prop 46. Composite Function Continuity
If $f$ is cts at $a$ and $g$ is cts at $f(a)$, then $g\circ f$ is cts at $a$

**Proof)**
Let's use Sequence Criterion

Suppose $\{x_{n}\}$ conv to $a$
- $\lim_{ n \to \infty }x_{n}=a$

Since $f$ is cts at $a$, $\lim_{ n \to \infty }f(x_{n})=f(a)$

Then, since $g$ is cts at $f(a)$, $\lim_{ n \to \infty }g(f(x_{n}))=g(f(a))$

Since $\{x_{n}\}$ was an arbitrary sequence conv to $a$, we get $g\circ f$ is cts at $a$

# Intermediate Value Theorem
cts functions are guaranteed to take retain value

## Lemma 47. Special Case of the Intermediate Value Theorem
Suppose $a,b\in\mathbb{R}$, $a<b$, $f$ is a function which is cts on $[a,b]$ and $f(a)<0$ and $f(b)>0$
Then, there exists a $c\in[a,b]$ so that $f(c)=0$

**Proof)**
Define $A=\{x\in[a,b]:f(x)<0\}$ and let's find $\text{sup}$ of it
- Non-empty: $f(a)\in A$
- Bounded Above: all $x\in A, x\leq b$

By completeness axiom, $\text{sup}(A)$ exists, let's call it $c$
- $c<b$ is guaranteed that $c$ is $\text{sup}(A)$ and $b$ is an upper bound of $A$
- $a<c$ is guaranteed since $c$ is $\text{sup}(A)$ and $a\in A$

Let's show that $f(c)=0$
- We will show that $f(c)\not<0$ and $f(c)\not>0$, thus by totality, $f(c)=0$

### i) $f(c)\not<0$
Proof by Contradiction) Suppose $f(c)<0$
- We will find a point $d$ "just to the right of $c$" for which $f(d)<0$ also
- Since $c=\text{sup}(A)$, $f(d)<0$ should not happen

Let $\epsilon=\frac{-f(c)}{2}>0$

Since $f$ is cts at $c$, there is some $\delta>0$ so that $\forall \text{ }x$ with $0<|x-c|<\delta$, $f(c)-\epsilon<f(x)<f(c)+\epsilon$
$$f(c)-(\frac{-f(c)}{2})<f(x)<f(c)+\frac{-f(c)}{2}$$
$$\frac{3f(c)}{2}<f(x)<\frac{f(c)}{2}$$
Since $f(c)<0$, $\frac{f(c)}{2}<0$, so for any such $x$, $f(x)<0$

Then, let $d$ be such that $c<d<\min(c+\delta, b)$ and $|d-c|<\delta$
- This $d$ has the property that $d<b$ and $f(d)<0$, thus $d\in A$
- But, we also have $c<d$, but $c=\text{sup}(A)$
- Contradiction as we've found a point in $A$ that is greater than $\text{sup}(A)$

### ii) $f(c)\not>0$
Exercise
- Should get a contradiction with $f(c)$ being the least upper bound


## Theorem 48. Intermediate Value Theorem
Suppose $a,b\in\mathbb{R}$, $a<b$, $f$ is cts on $[a,b]$ and $v$ is some point between $f(a)$ and $f(b)$
- Then, there exists a $c\in[a,b]$ so that $f(c)=v$

**Proof)**
Suppose $f(a)<f(b)$ (The case for $f(b)>f(a)$ is similar)

Define a new function $g(x)=f(x)-v$
- Then, $g$ is also cts since both $f(x)$ and $v$ are continuous, thus by Arithmetic Theorem for Continuous Function, $g$ is continuous
- And also $g(a)=f(a)-v<0$ since $f(a)<v$ and $g(b)=f(b)-v>0$ since $f(b)>v$

Then, by Lemma 47, $\exists \text{ }c\in [a,b]$ so that $g(c)=0$
- Therefore, $f(c)=g(c)+v=v$

### Example)
Consider $f(x)=x^{2}$
- cts everywhere by the Arithmetic Theorem
- Also, $f(1)=1$ and $f(2)=4$
- By IVT, there exists a  $c\in(1,2)$ so that $f(c)=2$
	- I.e. $c^{2}=2$
	- Now, we proved that $c=\sqrt{ 2 }$ is a real number
		- First example of irational real number

### Example)
Show that $x^{3}-8x+4=0$ has at least one solution
- Find some $a,b$ such that $f(a)<0$ and $f(b)>0$
- Then, by IVT, there is some solution


## Proposition 49
There is a real number $x$ such that $1\leq x\leq 2$ and $x^{2}=2$, and $x$ is irrational. We notate this number as $\sqrt{ 2 }$

Proved by Example 1) above

# There are infinitely many irrational number between any two rational number
## Lemma 50
Suppose $q\in\mathbb{R}$ is irrational, then
1) Then, $q^{-1}$ is also irrational
2) If $r\neq 0$ is rational, then $qr$ is also irrational

Prove 1)
Suppose for contradiction, $q^{-1}$ is rational, so $q^{-1}=\frac{m}{n}$ for some $m,n\in\mathbb{Z}$ and $n\neq 0$
- Then $q=\frac{n}{m}$, which is rational, contradicting the assumpsion

Prove 2) 
Exercise

## Theorem 51. Density of Rationals and Irrationals
Suppose $a,b\in\mathbb{R}$, $a<b$. Then there exists a rational number $r$ and irrational number $q$ such that $a<r<b$ and $a<q<b$

Proof by Cases)

i) $a=0$ and $b>0$

Recall [[2. Upper & Lower Bound#Prop 18. Archimedean Property of $ mathbb{R}$|Prop 18.]] 
So for rational number, by Prop 18, $\exists \text{ }n\in \mathbb{N}$ such that $nb>1>0$, so then $0<\frac{1}{n}<b$
- $r=\frac{1}{n}$

For irrational number, we know $1\leq \sqrt{ 2}$, so $0<\frac{1}{\sqrt{ 2 }}\leq 1$
- Thus, by multiplying this and $0<\frac{1}{n}<b$, $0<\frac{1}{n\sqrt{ 2 }}<b$
- By Lemma 50, $\frac{1}{n\sqrt{ 2 }}$ is irrational, $q=\frac{1}{n\sqrt{ 2 }}$

ii) $0<a<b$
In this case, $0<b-a$, So by case 1, there exists a rational numner $r$ and irrational $q$ such that $0<r<b-a$ and $0<q<b-a$

Then, by Prop 18, there is some $n\in\mathbb{N}$ such that $nr>a$
- Let $k$ be the smallest natural number such that $kr>a$
	- Exercise: Why such $k$ exist?
- Then, since $k$ is the smallest, $(k-1)r\leq a$ 
	- By adding this with $r<b-a$, $kr<b$
- Therefore, $a<kr<b$
	- Since $r$ is rational and $k$ is natural number, $kr$ is still a rational number

Similar proof for $q$, setting $k_{2}\in\mathbb{N}$ such that $a<k_{2}q<b$ is irrational

iii) $a<0\leq b$
Since we've already prove that there is some rational $r$ and irrational $q$ such that $0<r<b$ and $0<q<b$ by case 1, it indeed $a<r<b$ and $a<q<b$ since $a<0$

iv) $a<b<0$
Then, $0<-b<-a$. By case 2, $\exists \text{ }$ rational $r$ and irrational $q$ between $-b$ and $-a$
- $-b<r<-a$ and $-b<q<-a$

Then, $a<-r<b$ and $a<-q<b$
- $r$ is still rational
- $q$ is still irrational by Lemma 50

Therefore, the statement is true by proof by cases

## Corollary 52
For any $a,b\in\mathbb{R}$ if $a<b$ then there exist an infinite number of rational and irrational numbers between $a$ and $b$

Proof by Contradiction) Suppose there is only finite number of rationals between $a$ and $b$
- $a<r_{1}<r_{2}<r_{3}\dots r_{n}<b$
- But then by Theorem 51, there is another rational number between $a$ and $r_{1}$, contradicting that the there are only $n$ rationals

Similarly for irrationals

## Cardinality
Cardinality of Rationals is the same with Cardinality of $\mathbb{N}$, but Cardinality of Irrationals is not, the same as Cardinality of $\mathbb{R}$
- Rationals are Countable!

# Extreme Value Theorem
Is about conditions which ensure a function has a largest or smallest value
- In all $\mathbb{R}$
- Or in some closed interval $[a,b]$

Does this always happen?
- If $f$ is cts on $[a,b]$, does it always have a max and min in $[a,b]$?
- Yes!

## Lemma 53
Suppose $a,b\in\mathbb{R}$, $a<b$ and  $f$ is cts on $[a,b]$, then $f$ is bounded on $[a,b]$
- $\exists \text{ }M,N\in\mathbb{R}$ such that $\forall \text{ }x\in[a,b]$, $N\leq f(x)\leq M$

**Proof)**
Suppose for contradiction, such an $M$ does not exist

So, $M=1$ does not work, so there exists some $x_{1}\in[a,b]$, call it $x_{1}$, so that $f(x_{1})>1$
So, $M=2$ does not work, so there exists some $x_{2}\in[a,b]$, call it $x_{2}$, so that $f(x_{2})>2$
  $\vdots$

i.e. for every $n\in\mathbb{N}$, there is some $x_{n}\in[a,b]$ so that $f(x_{n})>n$
- So, we have a sequence $\{x_{n}\}$ such that $\forall \text{ }x_{n}\in[a,b], f(x_{n})>n$

Since $\{x_{n}\}$ is bounded, by Bolzano-Weierstraus Theorem, it has a convergent subseqeuence $\{x_{n_{k}}\}$, that converges to some $L$
- Since $f$ is cts, by Sequence Criterion, $\{f(x_{n_{k}})\}$ conv to $f(L)$
- The sequence $\{f(x_{n_{k}})\}$ is bounded since it is convergent

This contradicts how defined $f(x_{n})$ since $n\in\mathbb{N}$, $f(x_{n})>n$
- Therefore, $M$ must exist by proof by contradiction

Similar for $N$

## Theorem 54. Extreme Value Theorem
Suppose $a,b\in\mathbb{R}$, $a<b$ and  $f$ is cts on $[a,b]$. Then $f$ acieves a maximum and minimum on $[a,b]$
- $\exists \text{ }c,d\in[a,b]$ so that $\forall \text{ }x\in[a,b]$, $f(c)\leq f(x) \leq f(d)$
- Note) $c,d$ are not necessarily unique

Let $\mathrm{Im}(f)=\{f(x):x\in[a,b]\}$
- By Lemma 53, it is bounded above
- It is non-empty, $f(a)\in \mathrm{Im}(f)$
- By completeness axiom, $\text{sup}(\mathrm{Im}(f))$ exists, call it $L$
- We want to find a $d\in[a,b]$ so that $f(d)=L$

For any $n\in\mathbb{N}$, $L-\frac{1}{n}$ is not an upper bound, thus there must be an $x_{n}\in[a,b]$, $L-\frac{1}{n} <f(x_{n})$
- And we know that $f(x_{n})\leq L$

So $\{x_{n}\}$ is a sequence of points, each in $[a,b]$ and $\forall \text{ }n\in\mathbb{N}$, $L-\frac{1}{n}<f(x_{n})\leq L$
- By Sequeeze Theorem, $f(x_{n})$ converges to $L$
- Do we know that $\{x_{n}\}$ converges?

Since $\{x_{n}\}$ is bounded, then by Bolzano-Weierstrause Theorem, there is some subsequence $\{x_{n_{k}}\}$ that converges
- Let $d=\lim_{ k \to \infty }x_{n_{k}}$
- So by continuity of $f$ and Sequence Criterion, $\{f(x_{n_{k}})\}$ converges to $f(d)$

Since the whole sequence converges to $L$, so the subsequence must converge to $L$, so $f(d)=L$
- Since $L=\text{sup}(\mathrm{Im}(f))$, $\forall \text{ }x\in[a,b]$, $f(x)\leq L=f(d)$

Similar for $c$
- Use $\text{inf}(\mathrm{Im}(f))$ to set existence of $c$

# Definition of Derivatives
If $f$ is a function defined at some $a\in\mathbb{R}$, then if $$\lim_{ x \to a } \frac{f(x)-f(a)}{x-a}$$exists, we say that $f$ is differentiable at $a$ (i.e. derivative exists at $a$), call it $f'(a)$
- Note that this function is not defined at $a$

## Example)
Let $f(x)=x^{2}$ what is $f'(3)$?
$$\lim_{ x \to 3 }\frac{f(x)-f(3)}{x-3}=\lim_{ x \to 3 }\frac{x^{2}-9}{x-3}=\lim_{ x \to 3 }\frac{(x+3)(x-3)}{x-3}=\lim_{ x \to 3 } (x+3)=6$$

## Example)
Let $f(x)=\large\{^{x^{2}\text{ (if }x\geq0)}_{0 \text{ (if }x<0)}$. Does $f'(0)$ exists?
$$\lim_{ x \to 0 } \frac{f(x)-f(0)}{x-0}=\lim_{ x \to 0 } \frac{f(x)-0}{x-0}=\lim_{ x \to 0 } \frac{f(x)}{x}$$

To find this let's consider RH limit and LH limit separately.

i) LH
$$\lim_{ x \to 0^{-} } \frac{f(x)}{x}=\lim_{ x \to 0 } \frac{0}{x}=0$$
ii) RH
$$\lim_{ x \to 0^{+} }\frac{f(x)}{x}=\lim_{ x \to 0^{+} }\frac{x^{2}}{x}=\lim_{ x \to 0^{+} } x=0  $$

Since RH and LH leads to the same limit value, $\lim_{ x \to 0 }\frac{f(x)}{x}=0$, $f'(0)$ exists and equals to 0

## Example)
Let $f(x)=|x|$. Does $f'(0)$ exists?

$$\lim_{ x \to 0 } \frac{f(x)-f(0)}{x-0}=\lim_{ x \to 0 } \frac{f(x)-0}{x-0}=\lim_{ x \to 0 } \frac{f(x)}{x}$$

To find this let's consider RH limit and LH limit separately.

i) LH
$$\lim_{ x \to 0^{-} } \frac{f(x)}{x}=\lim_{ x \to 0 } \frac{-x}{x}=-1$$
ii) RH
$$\lim_{ x \to 0^{+} }\frac{f(x)}{x}=\lim_{ x \to 0^{+} }\frac{x}{x}=1  $$

Since RH and LH does not lead to the same limit value, $\lim_{ x \to 0 }\frac{f(x)}{x}$ does not exists, thus $f'(0)$ does not exist

# Prop 51. If $f$ is differentiable at $a$, then $f$ is continuous at $a$
(Note that this is one-way implication)

We know $\lim_{ x \to a }\frac{f(x)-f(a)}{x-a}$ exists, we want $\lim_{ x \to a }f(x)=f(a)$

Consider $\lim_{ x \to a }f(x)-f(a)$
- We want to prove this exsits and equals to 0
- $=\lim_{ x \to a }\frac{f(x)-f(a)}{x-a}\cdot(x-a)$

Since $\lim_{ x \to a }\frac{f(x)-f(a)}{x-a}$ and $\lim_{ x \to a }(x-a)$ both exist, by Arithmetic Theorem of Function Limit, their product exists
- $\lim_{ x \to a }(f(x)-f(a))$ exists

Furthermore,  $\lim_{ x \to a }\frac{f(x)-f(a)}{x-a}\cdot(x-a)=\lim_{ x \to a }\frac{f(x)-f(a)}{x-a}\cdot\lim_{ x \to a }(x-a)=f'(a)\cdot(a-a)=f'(a)\cdot 0=0$
- Since $\lim_{ x \to a }(f(x)-f(a))=0$, $\lim_{ x \to a }f(x)=f(a)$

# Chain Rule
$$(g\circ f)'(a)=g'(f(a))f'(a)$$

$(g\circ f)'(a)=\lim_{ x \to a }\frac{g(f(x))-g(f(a))}{x-a}$

$g'(f(a))f'(a)=\left( \lim_{ x \to f(a) }\frac{g(x)-g(f(a))}{x-f(a)} \right)\left( \lim_{ x \to a }\frac{f(x)-f(a)}{x-a} \right)$

Unfortunately, we can't directly prove from definition immediately. Let's consider following theorem

## Thm 56. Derivative Existence Theorem (Caratheodory's Theorem)
Suppose $f$ is defined at some $a\in\mathbb{R}$. Then $f$ is differentiable at $a$ iff there exists some function $S$ which has two properties
1. $\forall \text{ }x\neq a$, $S(x)(x-a)=f(x)-f(a)$
2. $S$ is cts at $a$
In this case, $f'(a)=S(a)$

### Example)
Suppose we want to find $f'(3)$ when $f(x)=x^{2}$
Consider $f(x)-f(a)=x^{2}-9=(x-3)(x+3)$
- $x+3$ could be $S(x)$, is this function cts at 3?
	- Yes

Then, by Derivative Existence Theorem, $f'(3)$ exists and equals to $3+3=6$

### Forward Direction)
Suppose $f$ is differentiable at $a$
Define $S(x)$ to be
$$S(x)=\large\{^{\frac{f(x)-f(a)}{x-a}\text{ if }x\neq a}_{f'(a)\text{ if }x=a} $$
By definition, if $x \neq a$ $S(x)(x-a)=f(x)-f(a)$
- So, $S$ satisfies 1.

Consider $\lim_{ x \to a }S(x) = \lim_{ x \to a }\frac{f(x)-f(a)}{x-a}=f'(a)=S(a)$
- Thus, indeed $S$ is continuous at $a$

### Backward Direction)
Assume such an $S$ exists
By 1. for $x\neq a$, since $S(x)(x-a)=f(x)-f(a)$
- $S(x)=\frac{f(x)-f(a)}{x-a}$

Then, $\lim_{ x \to a }\frac{f(x)-f(a)}{x-a}=\lim_{ x \to a }S(x)$

Since $S$ is continuous by 2. 
- $\lim_{ x \to a }S(x)=S(a)$

So, $\lim_{ x \to a }\frac{f(x)-f(a)}{x-a}$ does exists and equals $S(a)$

## Prove using DET
Suppose $f,g$ are differentiable at $a$, and we want to show that $f+g$ is differentiable at $a$

By forward direction of DET, there are functions $S,T$ so that 
- $\forall \text{ }x\neq a$, $S(x)(x-a)=f(x)-f(a)$ and $T(x)(x-a)=g(x)-g(a)$
- $S,T$ are cts at $a$, thus $S(a)=f'(a)$ and $T(a)=g'(a)$

Consider $(f+g)(x)-(f+g)(a)$
$$=f(x)+g(x)-f(a)-g(a)$$
$$=S(x)(x-a)+T(x)(x-a)=(x-a)(S(x)+T(x))$$
- $S(x)+T(x)$ is cts by Continuity Arithmetic Theorem

Then, $S(x)+T(x)$ satisfies 1. and 2. for the DET for $f+g$ at $a$
- So, $(f+g)(a)$ exists and equals to $S(a)+T(a)=  f'(a)+g'(a)$ by DET

## Prop 57. Chain Rule
If $f$ is differentiable at $a$ and $g$ is differentiable at $f(a)$, then $g\circ f$ is differentiable at $a$ and
$$(g\circ f)'(a)=g'(f(a))f'(a)$$

**Proof)**
By DET forward direction, there exist functions $S,T$ so that
1. $\forall \text{ }x\neq a$, $S(x)(x-a)=f(x)-f(a)$, $S$ is cts at $a$  and $S(a)=f'(a)$
2.  $\forall \text{ }y\neq f(a)$, $T(y)(y-f(a))=g(y)-g(f(a))$, $T$ is cts at $f(a)$, $T(f(a))=g'(f(a))$

Consider $g(f(x))-g(f(a))$
$$=T(f(x))(f(x)-f(a))$$
by substitute $y=f(x)$ to 2.
$$T(f(x))S(x)(x-a)$$
by 1.

Then, is $T(f(x))S(x)$ cts at $a$?
- $S(x)$ is cts at $a$ by 1
- $f$ is differentiable at $a$ and $T$ is cts at $f(a)$, by [[6. Continuous Function#Prop 46. Composite Function Continuity|Prop 46(Composite Function Continuity)]], $T(f(x))$ is cts at $a$

So by the Continuity Arithmetic Theorem, $T(f(x))S(x)$ is cts at $a$

So by DET, $g\circ f$ is differentiable at $a$, and also
$$g\circ f'(a)=[T(f(x))S(x)](a)=T(f(a))S(a)=g'(f(a))f'(a)$$

# Basic Derivative Rules

## 1. For any $k\in\mathbb{R}$, $f(x)=k$, then $\forall \text{ }a\in\mathbb{R}, f'(a)=0$
## 2. If $f(x)=x$, then $\forall \text{ }a\in\mathbb{R}, f'(a)=1$

$f,g$ are differentiable at $a$,
## 3. $\forall \text{ }c\in\mathbb{R}$, $(cf)'(a)=cf'(a)$
## 4. $(f+g)'(a) = f'(a)+g'(a)$
## 5. $(fg)'(a) = f'(a)g(a)+f(a)g'(a)$
## 6. $\left( \frac{f}g{} \right)'(a)=\frac{f'(a)g(a)-g'(a)f(a)}{g(a)^{2}}$

# Prop 59. Power Rule
If $n\in\mathbb{N}$ and $f(x)=x^{n}$, then $f'(x)=nx^{n-1}$

**Proof by Induction)**
For $n=1$, then $f(x)=x$ and $f'(x)=1$ by Basic Derivative Rule
- $1x^{1-1} = 1$
- Base Case hold

Assume the result holds for $n=k$, i.e. if $f(x)=x^{k}$, then $f'(x)=kx^{k-1}$
- Need to show that if $g(x)=x^{k+1}$, then $g'(x)=(k+1){x^{k}}$

$g(x)=x(x^{k})$, then by product rule, $g'(x)=x^{k}+x\cdot(kx^{k-1})=x^{k}+kx^{k}=(k+1)x^{k}$
- Thus Inductive step holds

Therefore, if $n\in\mathbb{N}$ and $f(x)=x^{n}$, then $f'(x)=nx^{n-1}$, by proof by induction

# Power Rule with non natural number power?

## Negative Power
Assignment Q

## Fractional Power
Consider $x^{\frac{1}{3}}$
- Since this is an inverse of $x^{3}$, it will be useful if we have a derivative rule for this

## Inverse
For a function $f$, and inverse for $f$ is a function $g$ so that
- $\forall \text{ }x$ in the domain of $f$, $g(f(x))=x$ and $\forall \text{ }y$ in domain of $g$, $f(g(y))=y$

# Theorem 60. Inverse Function Theorem
Suppose $f$ has an inverse funciton $g$, $f$ is differentiable at $a$, and $f'(a)\neq 0$
- Then $g'(f(a))$ exists and equals $\frac{1}{f'(a)}$
Also, if you let $b=f(a)$, then $g(b)=g(f(a))=a$
- $g'(b)=g'(f(a))=\frac{1}{f'(g(b))}$

**Ex)**
For $n\in\mathbb{N}$, the inverse of $f(x)=x^{n}$ is $g(x)=x^{\frac{1}{n}}$
Then, by inverse function theorem, 
$$g'(b)=\frac{1}{f'(g(b))}=\frac{1}{n\left( b^{\frac{1}{n}} \right)^{n-1}}=\frac{1}{n}\cdot\frac{1}{b^{1-\frac{1}{n}}}=\frac{1}{n}\cdot b^{\frac{1}{n}-1}$$
Thus, the derivative of $x^{\frac{1}{n}}$ is $\frac{1}{n}\cdot x^{\frac{1}{n}-1}$

**Ex)**
Suppose we had defined 
$$f(x)=e^{x}=\lim_{ n \to \infty } \left( 1+\frac{x}{n} \right)^{n}$$
and showed $f'(x)=e^{x}$
Its inverse function is $g(x)=\ln(x)$

Then, by inverse function theorem, 
$$g'(x)=\frac{1}{f'(g(x))}=\frac{1}{f'(\ln x)}=\frac{1}{e^{\ln x}}=\frac{1}{x}$$
Therefore, $g'(x)=\frac{1}{x}$

## Proof)
By DET forward direction, there exists function $S$ so that 
- $\forall \text{ }x\neq a$, $f(x)-f(a)=(x-a)S(x)$
- $S$ is cts at $a$
- and $S(a)=f'(a)$

Now, want to look at differentiability of $g$ at $f(a)$, so consider for some $y\neq f(a)$, $g(y)-g(f(a))$
- Since $f$ and $g$ are inverse, $=g(y)-a$

Let $x=g(y)$ so that $f(x)=f(g(y))=y$
- $g(y)-a=x-a$

Suppose $S(x)\neq 0$
- $=\frac{f(x)-f(a)}{S(x)}=\frac{y-f(a)}{S(g(y))}=\frac{1}{S(g(y))}\cdot(y-f(a))$

Then, $\frac{1}{S(g(y))}$ satisfies 2. condition for DET
- Need to show it is cts at $f(a)$

If $f$ is cts at $a$ and $S(g(f(a)))=S(a)$ and $S$ is cts at $a$ by assumption
- by the DET, $g'(f(a))$ exists and equals to $\frac{1}{S(g(f(a)))}=\frac{1}{S(a)}=\frac{1}{f'(a)}$

# How the Derivative of $f$ related to shape of graph
## Open Interval
An Open Interval in $\mathbb{R}$ is a subset of the form
$$\{ x\in\mathbb{R}: a<x<b \}$$
for some $a,b\in\mathbb{R}$ and $a<B$
- Denoted as $(a,b)$

## Proposition 61
Suppose $f$ is a function, $a\in\mathbb{R}$, $I$ is some open interval containing $a$ and $\forall \text{ }x\in I, f(x)\geq M$ for some $M\in\mathbb{R}$
- Then if $\lim_{ x \to a }f(x)=L$ exists, then $L\geq M$ also

**Exercise)**
Suppose for contradiction, $L<M$. 
Take $\epsilon =|M-L|$.
Then, there is some $\delta>0$ such that $|x-a|<\delta$

## Local Minimum and Maximum
Suppose $f$ is a function. 
- Say that $f$ has a local minimum at $a\in\mathbb{R}$ if there is some open interval $I$ containing $a$ so that $\forall \text{ }x\in I$, $f(x)\geq f(a)$
- Similarly, $f$ has a local maximum at $a\in\mathbb{R}$ if there is some open interval $I$ containing $a$ so that  $\forall \text{ }x\in I, f(a)\geq f(x)$

# Theorem 62 (Fermat's Theorem)
Suppose $f$ has a local minimum or maximum at $a$
- Then either $f'(a)$ does not exist or $f'(a)=0$

**Proof)** Suppose $a$ is a local minimum
- If $f'(a)$ does not exist, we are done

Suppose $f'(a)$ exists
- Show $f'(a)\geq0$ and $f'(a)\leq 0$

Consider $x>a$, then
$f'(a)=\lim_{ x \to a }\frac{f(x)-f(a)}{x-a}=\lim_{ x \to a^{+} }\frac{f(x)-f(a)}{x-a}$
- Since $a$ is a local minimum says $f(x)\geq f(a)$ and $x-a>0$ since $x>a$, $\frac{f(x)-f(a)}{x-a}\geq0$
- By Prop 61, $\lim_{ x \to a^{+} }\frac{f(x)-f(a)}{x-a}\geq 0$ also

Similarly, consider $x< a$
$f'(a)=\lim_{ x \to a }\frac{f(x)-f(a)}{x-a}=\lim_{ x \to a^{-} }\frac{f(x)-f(a)}{x-a}$
- Since $f(x)\geq f(a)$ and $x<a$, $\frac{f(x)-f(a)}{x-a} \leq 0$
- By Prop 61, $\lim_{ x \to a^{-} }\frac{f(x)-f(a)}{x-a} \leq 0$ as well

Thus, $f'(a)\geq0$ and $f'(a) \leq 0$, $f'(a) = 0$

Similar for $a$ being local maximum

# Increasing Function
$f$ is said to be increasing on an interval $I$, if $\forall \text{ }x_{1}<x_{2}$ in $I$, $f(x_{1})\leq f(x_{2})$
- Decreasing on an interval $I$, if $\forall \text{ }x_{1}<x_{2}$ in $I$, $f(x_{1})\geq f(x_{2})$

# Proposition 63
If $f$ is increasing on an open interval $I$, and differentiable on all of $I$, then $\forall \text{ }a\in I$, $f'(a)\geq 0$
- Decreasing on an open interval $I$, and differentiable on all of $I$, then $\forall \text{ }a\in I, f'(a)\leq 0$

**Proof)**
Assignment

# Lemma 64. Rolle's Theorem
Suppose $a,b\in\mathbb{R}$, $f$ is cts on $[a,b]$ and differentiable on $(a,b)$ and $f(a)=f(b)$
- Then there exists $c\in(a,b)$ so that $f'(c)=0$

**Proof)**
By Extreme Value Theorem, $f$ has a maximum and minimum in $[a,b]$
- If either of these is in $(a,b)$, then say at $c$, then it will be a local min or max, and by Fermat's Theorem, $f'(c)=0$
- Otherwise, local minimum and maximum are at $a$ and $b$, but $f(a)=f(b)$, thus $\max = \min$, thus this is constant function. Thus, for any $c\in(a,b)$, $f'(c)=0$

# Theorem 65. Mean Value Theorem
Suppose $a,b\in\mathbb{R}$, $a<b$, $f$ is cts on $[a,b]$ and differentiable on $(a,b)$
- Then there exists a point $c\in(a,b)$ so that $f'(c)=\frac{f(b)-f(a)}{b-a}$

**Note)** MVT says you can "Find a place where the derivative is the slope of the line connecting $a$ and $b$"

## Proof)
Define
$L(x)=\left( \frac{f(b)-f(a)}{b-a} \right)(x-a)+f(a)$
Then, define
$h(x)=L(x)-f(x)$

We'll show we can use Rolle's Theorem on the function $h$

Since $(x-a)$ is differentiable, $L(x)$ is differentiable by Basic Derivative Rule
- Then, $h(x)$ is also differentiable by Basic Derivative Rule, as both $L(x)$ and $f(x)$ are differentiable
- Now, we need $h(a)=h(b)$

$h(a)=L(a)-f(a)=\left( \frac{f(b)-f(a)}{b-a} \right)(a-a)+f(a)-f(a)=0$
$h(b)=L(b)-f(b)=\left( \frac{f(b)-f(a)}{b-a} \right)(b-a)+f(a)-f(b)=f(b)-f(a)+f(a)-f(b)=0$
- $h(a)=h(b)$

By Rolle's Theorem, there is a $c\in(a,b)$ so that $h'(c)=0$
- $h'(c)=L'(c)-f'(c)=\frac{f(b)-f(a)}{b-a}-f'(c)$
- $0=\frac{f(b)-f(a)}{b-a}-f'(c)$

Therefore, $f'(c)=\frac{f(b)-f(a)}{b-a}$

# Proposition 66
If $f$ is differentiable on an open interval $I$, and $\forall \text{ }a\in I, f'(a)\geq 0$, then $f$ is increasing on $I$
- We want if $x_{1}<x_{2}$, then $f(x_{1})\leq f(x_{2})$
- Unfortunately, we can't directly prove this from the definition since it only tells information about $f(x)$ for $x$ near $x_{1}$, not between $x_{1}$ and $x_{2}$
- Thus, we need MVT

Suppose $x_{1}<x_{2}$ for some $x_{1}, x_{2}\in I$.
- By MVT, $\exists \text{ }c\in(x_{1}, x_{2})$ so that $f'(c)=\frac{f(x_{2})-f(x_{1})}{x_{2}-x_{1}}$
- Then, $f(x_{2})-f(x_{1})=f'(c)(x_{2}-x_{1})$

We know that $f'(c)\geq0$ by assumption and $x_{2}-x_{1}>0$
- Therefore, $f(x_{2})-f(x_{1})\geq 0$
- $f(x_{2})\geq f(x_{1})$

Since $x_{1}$ and $x_{2}$ are arbitrary, $f$ is increasing on $I$

---
# Example
Show that $f(x)=\displaystyle\Big\{^{5x \text{ if x is rational}}_{0\text{ if x is irrational}}$
is not cts at $a$ if $a\neq 0$

We can prove this directly, or using previous results
## Directly
Want to show that if $a\neq 0$, $\lim_{ x \to a }f(x)\neq f(a)$
- Actually, we will show that $\lim_{ x \to a }f(x)$ doesn't even exist
- From the definition, need to find an $\epsilon>0$ which makes the definition not work

Take $\epsilon=|5a|$. If $\lim_{ x \to a }f(x)=f(a)$, then we'd have $\delta>0$ so that for any $x$ such that $0<|x-a|<\delta$, $|f(x)-f(a)|<\epsilon$

If $a$ is irrational, $f(a)=0$, and suppose also $a>0$
- Then, we can find a rational $x$ so that $a<x<a+\delta$ by density of rational
- Thus, $0<|x-a|<\delta$, but $|f(x)|=5x>5a$, thus $|f(x)|\not<\epsilon$

Similar proof for $a$ being rational

## Using Sequence Criterion
Use a sequence of rationals $\{ x_{n} \}$ converging to $a$ and sequence of irrationals $\{ y_{n} \}$ converging to $a$, then 
- $\{ f(x_{n}) \}=\{ 5x_{n} \}$ conv to $5a$ since $\{ x_{n} \}$ converges to $a$
- $\{ f(y_{n}) \}=\{ 0 \}$ conv to 0

So, the limit would only exist if $5a=0$, which is only $a=0$

Note) How do we even know such sequence $\{ x_{n} \}$ and $\{ y_{n} \}$ exist?
We should be able to set such sequences using density of rationals and irrationals, but how?
- For each $n$, find a rational $q_{n}$ such that $a<q_{n}<a+\frac{1}{n}$
- Then $\lim_{ n \to \infty }q_{n}=a$ by Sequeeze Theorem

