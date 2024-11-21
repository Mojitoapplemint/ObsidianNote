# Proposition
If $ab\equiv x\text{ (mod }m)$ and $cd\equiv y\text{ (mod }m)$, then $abcd\equiv xy\text{ (mod }m)$

# Wilson's Theorem
If $p$ is prime, then $(p-1)!\equiv -1\text{ (mod }p)$

**Proof)**
Suppose $p$ is prime

i) If $p=2$, then $(p-1)\neq 1\equiv -1 \text{ (mod }2)$

ii) When $p>2$ ($p$ is odd)
Consider $a\in\{1,2,3\dots p-1\}$. Since $p$ is prime, $gcd(a,p)=1$

$\therefore$ a has inverse $\bar{a}$ modulo $p$

[[7. Conguents#Theorem 4.12|Theorem 4.12]]  told us $a^{2}\equiv 1 \text{ (mod }p)$ iff $a\equiv 1$ or $a\equiv -1 \text{ (mod }p)$
- So, the only integer in $\{1,2,\dots p-1\}$ that one their own inverses are 1 and $p-1$
- Thus, let's consier $\{2,3\dots p-1\}$

We group $2,3,\dots p-2$ into $\frac{p-3}{2}$ pairs that are congruent to $1\text{ (mod }p)$

**Claim)** No two integers in my list have the same inverse mod $p$

Proof by contradiction: Suppose $ax\equiv 1\text{ (mod }p)$ and $(a+j)x\equiv 1\text{ (mod }p)$
- $2\leq a,a+j, x\leq p-2$
- $1\leq j\leq p-3$
- $a,a+j\neq x$

Then,
- $p\text{ | }ax-1$
- $p\text{ | }(a+j)x-1$

$pq=ax-1$ for some $q\in \mathbb{Z}$
- Then $ax+jx-1=pq+jx \implies p\text{ | }(pq+jx) \implies py=pq+jx$ for some $y\in\mathbb{Z}$
- $p(y-q)=jx$, thus $p\text{ | }jx$. Since $p$ is prime, $p\text{ | }j$ or $p\text{ | }x$
- This contradicts that $x\leq p-2<p$ and $j\leq p-3<p$, thus $p$ can't divide $j$ and $x$
(End of proving Claim)

Then, by the claim, every integer in $\{2,3\dots p-2\}$ has distinct inverse mod $p$ from the set
- $2\cdot 3\dots(p-2)\equiv 1\text{ (mod }p)$

Therefore, $1\cdot 2\cdot 3\dots(p-1)\equiv p-1\equiv -1\text{ (mod }p)$

# Theorem 6.2
Let $n\geq 2$ be an integer, If $(n-1)!\equiv -1\text{ (mod }n)$, then $n$ is prime

**Proof)**
Let $n\geq{2}$ be an integer for which $(n-1)!\equiv -1\text{ (mod }n)$

Proof by Contradiction: Suppose $n$ is composite, $n=ab\text{ }(a,b\in\mathbb{Z}\text{, }1<a\leq b<n)$

As $1<a<n$, we know $a$ is one of the integers in the products $(n-1)!$
- $a\text{ | }(n-1)!$ 

Since $(n-1)!\equiv -1 \text{ (mod }n)$ by given condition, $n\text{ | }[(n-1)!+1]$
- Since $a\text{ | }n$ and $n\text{ | }[(n-1)!+1]$, $a\text{ | }[(n-1)!+1]$

Since $a$ divides both $(n-1)!$ and $(n-1)!+1$, $a$ would divide their difference
- $a\text{ | }1$

This contradicts since $1<a$. Thus, $n$ is prime by proof by contradiction

# Theorem 6.3: Fermat's Little Theorem
If $p$ is prime and $a$ is an integer with $p\text{ }|\not\text{ }a$, then $a^{p-1}\equiv 1 \text{ (mod }p)$

## Idea
| x (mod 7)  | 1   | 2   | 3   | 4   | 5   | 6   |
| ---------- | --- | --- | --- | --- | --- | --- |
| 3x (mod 7) | 3   | 6   | 2   | 5   | 1   | 4   |
Therefore,
$$(3\cdot 1)\cdot(3\cdot 2)\cdot(3\cdot 3)\cdot(3\cdot 4)\cdot(3\cdot 5)\cdot(3\cdot 6)\equiv 1\cdot2 \cdot 3\cdot 4 \cdot5\cdot 6\text{ (mod }7)$$
$$3^{6}\cdot 6!\equiv 6! \text{ (mod }7)$$
Since $6!$ and 7 are relatively prime, we can cancel $6!$ for both sides
$\therefore 3^{6}\equiv 1\text{ (mod }7)$

## Lemma 4.1 Complete System of Residue
A set of $p$ incongruent integers modulo $p$ forms a complete system of residue mod $p$

Ex) $p=5$ $\implies \{0,1,2,3,4\}$ is complete set of residue
- Each number is just a representative of each equivalent class

## Theorem 4.7
If $r_{1}, r_{2}\dots r_{n}$ is a complete system of residue mod $n$, and $gcd(m,n)=1$ for some $a\in\mathbb{Z}^{+}$, then $mr_{1}+i, mr_{2}+i, mr_{n}+i$ is also complete system of residue mod $n$

## Very Useful Claim
Claim: Let $p$ be prime such that $p\text{ }|\not\text{ }a$. The integers $a, 2a, 3a\dots(p-1)a \text{ (mod }p)$ are the same as the integers $1,2,3\dots(p-1)$ though they may appear in a different order

Let $p$ be prime, $a\in\mathbb{Z}$, $p\text{ }|\not\text{ }a$

i)
Observe that none of $a, 2a, 3a\dots(p-1)a \text{ (mod }p)$ are divisible by $p$
- $p$ be prime, thus $p\text{ }|\not\text{ }i$ if $1\leq i\leq p-1$ 
- $p\text{ }|\not\text{ }a$

ii)
Observe that no two of $a, 2a, 3a\dots(p-1)a$ are congruent modulo p
**Proof by Contradiction)**
Suppose $ja\equiv ka(\text{mod }p)$ for $1\leq k<j\leq p-1$ 
Then $p\text{ | }(j-k)a$
- Since $p\text{ }|\not\text{ }a$, $p\text{ | }(j-k)$

Since $1\leq k<j\leq p-1$, $j-k$ must be smaller than $p$.
- This contradicts that $p$ can't divide $j-k$

Therefore, $a, 2a, 3a\dots(p-1)a$ are a set of $p-1$ integers, none congruent to $0\text{ (mod }p)$ and no two are congruent modulo $p$
- If we include 0, then we have $p$ incongruent integers $\text{mod }p$, which is a complete system of residue by lemma 4.1

From that complete system of residue, excluding 0, then we have the integers $1,2,\dots(p-1)$

## Proving Fermat's Little Theorem
Let $p$ be prime, $a\in\mathbb{Z}$, $p\text{ }|\not\text{ }a$

By the very useful claim, 
$$a\cdot 2a\cdot 3a \dots(p-1)a\equiv 1\cdot 2\cdot 3 \dots(p-1)\text{ (mod }p)$$
$$a^{p-1}(p-1)!\equiv (p-1)!\text{ (mod }p)$$
Since $(p-1)!$ and $p$ are relatively prime, we can cancel $(p-1)!$ to both side
$$\therefore a^{p-1}\equiv 1\text{ (mod p})$$

**Note)**
Why we can cancel $(p-1)!$ out?

From $a^{p-1}(p-1)!\equiv (p-1)!\text{ (mod }p)$, 
- $p\text{ | }[(a^{p-1}-1)(p-1)!]$
- $p\text{ } |\not\text{ }(p-1)!$, so $p|(a^{p-1}-1)$

# Theorem 6.4
If $p$ prime and $a\in\mathbb{Z}^{+}$, then $a^{p}\equiv a\text{ (mod }p)$

**Proof)**
Let $p$ be prime and $a\in\mathbb{Z}^{+}$

Proof by Cases

i) $p\text{ }|\not\text{ }a$
Then, by Fermat's Little Theorem,
- $a^{p-1}\equiv 1\text{ (mod p})$

And we can multiply $a$ to the bothsides and get the result we want

ii) $p\text{ | }a$
If $p \text{ | } a$, then $p\text{ | }a^p$
Thus $p\text{ | }(a^{p}-a)$, $a^{p}\equiv a\text{ (mod }p)$

# Witness
Suppose $n$ is a very large number
- How can we determine that $n$ is prime? Let's utlize FLT

Suppose $a=2$, if $n$ is prime, by FLT, $2^{n-1}\equiv 1\text{ (mod }n)$
- If $n$ is prime, then $2^{n}\equiv 2\text{ (mod }n)$

Consider its contrapositive: If $2^{n}\not\equiv 2\text{ (mod }n)$, then $n$ is not prime
- What if $2^{n}\equiv 2$?
- Then $n$ may/may not be prime

Suppose we pick other values for $a$.
- $3^{n}\equiv 3\text{ (mod }n)$
- $4^{n}\equiv 4\text{ (mod }n)$
- $\vdots$
- $100^{n}\equiv 100\text{ (mod }n)$
Even if all of the above holds, we still can't say that $n$ is prime, but it seems probable.

We say $a$ is a **witness** for $n$ if $a^{n}\not\equiv a\text{ (mod }n)$
- If $n$ is prime, it has no witnesses

## Example) $n=561$
Consider $n=561=3\cdot 11\cdot 17$
- It is not prime
- It has no witnesses

To prove $a^{561}\equiv a\text{ (mod }561)$

We could show
1. $a^{561}\equiv a\text{ (mod }3)$
2. $a^{561}\equiv a\text{ (mod }11)$
3. $a^{561}\equiv a\text{ (mod }17)$

Prove 1) 
i) If $3|a$
Then, $a\equiv 0\text{ (mod }3)$ and $a^{561}\equiv 0\text{ (mod }3)$

ii) If $3\text{ }|\not\text{ }a$
Then FLT says $a^{560}\equiv 1\text{ (mod }3)$
- Thus, $a^{561}\equiv a\text{ (mod }3)$

# Fermat Pseudoprime
Let $b\in\mathbb{Z}^{+}$

If $n$ is a composite positive integer and $b^{n}\equiv b\text{ (mod }n)$ then $n$ is a **(Fermat) Pseudoprime** to the base $b$

**Ex)** 15 is a Fermat Pseudoprime to the base 4, so $4^{15}\equiv 4\text{ (mod }15)$

## Drive more pseudoprimes from one pseudoprime
We've got some big integer $n$ and we found $2^{n}\equiv{2}\text{ (mod }n)$
- Either $n$ is *prime or a pseudoprime to the base 2*

Suppose $n$ is not prime.

$2^{n-1}\equiv 1\text{ (mod }n)$

Let $m=2^{n}-1$ and we want to prove that this is also pseudoprime
1) Show $m$ is composite
2) Show $m$ is pseudoprime to the base 2

i) Show $m=2^{n}-1$ is composite

Since $n$ is composite, $n=k\cdot l$ for some integer $1<k,l<n$
- Let's show $(2^{k}-1)\text{ | }m$

Consider $x^{l}-1=(x-1)(x^{l-1}+x^{l-2}\dots+1)$ (binomial identity)

Let $x=2^{k}$, Then by binomial identity
$$m=2^{n}-1=2^{kl}-1=(2^{k}-1)(2^{k(l-1)}+2^{k(l-2)}\dots 2^{k}+1)$$
$$\therefore (2^{k}-1)\text{ | }m$$

ii) Show $m$ is pseudoprime to the base 2

$2^{n}\equiv 2\text{ (mod }n)\implies ny=2^{n}-2\text{ }(y\in\mathbb{Z})$

Since $m=2^{n}-1$,
$2^{m-1}-1=2^{2^{n}-2}-1=2^{ny}-1$

Then, by binomial identity,
$$2^{ny}-1=(2^{n}-1)(2^{n(y-1)}+2^{n(y-2)}\dots 2^{n}+1)$$
$$2^{m-1}=m(2^{n(y-1)}+2^{n(y-2)}\dots 2^{n}+1)$$
$$\therefore  m\text{ | }(2^{m-1}-1)\implies 2^{m-1}\equiv 1\text{ (mod }m)\implies 2^{m}\equiv 2 \text{ (mod }m)$$

Therefore, $m$ is a pseusdoprime to the base 2

**Note)**
$q=2^{m}-1$ will also be a pseudoprime. Therefore, there are **infinite amount of pesudoprime to the baes 2** by repeating this process

# Absolute Fermat Pseudoprime (Carmichael Number)
A Carmichael Number is a composite number $n$ where $a^{n-1}\equiv 1\text{ (mod }n)$ for every positive integer $a$ where $gcd(a,n)=1$
- Also called **Absolute (Fermat) Pseudoprime**
- Pseudoprime for all base

**Ex)** 561, 1105, 1729, 2465, 2821, 6601, 8911
$561=3\cdot 11\cdot 17$
$1105=5\cdot 13\cdot 17$
$1729=7\cdot 13\cdot 19$
$2465=5\cdot 17\cdot 29$
$2821=7\cdot 13\cdot 31$
$6601=7\cdot 23\cdot 41$
$8911=7\cdot 19\cdot 67$

## Properties
1. Odd
2. All prime factors are distinct (No squares)
3. If $p$ is a prime number of $n$, $(p-1)|(n-1)$

### Prove 1): Odd
Let $n$ be a Carmichael number. Suppose $a=n-1$

Then, $(n-1)^{n}\equiv (n-1)\text{ (mod }n)$
- But $n-1\equiv -1\text{ (mod }n)$

Then, $(-1)^{n}\equiv -1\text{ (mod }n)$

If $n=2$, then $(-1)^{2} =1\equiv -1\text{ (mod }2)$
- Since Carmichael number is composite, $n$ can't be Carmichael Number

If $n>2$ and even, $(-1)^{n}=1\equiv -1 \text{ (mod }n)$
- This contradicts that since $n>2$, $1\equiv -1 \text{ (mod }n)$ is impossible

Therefore, If $n>2$ and odd, then $(-1)^{n}=-1\text{ (mod }n)$


### Prove 2) All prime factors are distinct (No squares)
Next, we show that if $p$ is prime divisor of Carmichael number $n$, then 
$$p^{2}\text{ }|\not \text{ }n$$
Proof by Contradiction)
Let $p^{k}$ be the highest prime power dividing $n$. 
- $n=p^{k}y$ $(y\in\mathbb{Z}\text{ and }gcd(p,y)=1)$ 
- And we assume $k\geq 2$

Let $a=1+py$
- Magical Number
- We will show $a^{n-1}\not\equiv 1 \text{ (mod }n)$ 

Assume that $gcd(a,n)=1$
- Assignment Question

Note $gcd(a,y)=1$
- Suppose for contradiction, suppose $gcd(a,y)=d>1$, then $dl=y$ and $dk=a$
- $a=1+py\implies dk=1+pdl\implies d(k-pl)=1$
- $d\text{ | }1$, thus contradiction

Consider $a^{n-1}=(1+py)^{n-1}$
By Binomial Theorem, 
$$(1+py)^{n-1}=1+(n-1)(py)^{1}+{}_{n-1}C_{2}\cdot (py)^{2}\dots (n-1)(py)^{n-2}+(py)^{n-1}$$
$$=1+(n-1)py+p^{2}(\text{mumbo jumbo})$$
Let's think about this in $\text{mod } p^{2}$
$$\equiv 1+(n-1)py\text{ (mod }p^{2})$$
$$=1+npy-py\text{ (mod }p^{2})$$
$$=1+(p^{k}y)py-py\text{ (mod }p^{2})$$
Since $k\geq 2$, $(p^{k}y)py\equiv 0\text{ (mod }p^{2})$
$$\equiv 1-py \text{ (mod }p^{2})$$

Observe $1-yp\not\equiv 1\text{ (mod }p^{2})$
- Suppose for Contradiction, $1-yp \equiv 1\text{ (mod }p^{2})$
- Then, $p^{2}\text{ | }(-yp)$
- Contradicts $gcd(p,y)=1$

Therefore, $a^{n-1}\not\equiv 1\text{ (mod }p^{2})$

This yields a contradiction, since $n$ is Carmichael number and $gcd(a,n)=1$, we know 
- $a^{n-1}\equiv 1 \text{ (mod }n)$
- $a^{n-1}\equiv 1 \text{ (mod }p^{k}y)$
	- $a^{n-1}\equiv 1 \text{ (mod }p^{2}p^{k-2}y)$
	- $a^{n-1}\equiv 1\text{ (mod }p^{2})$
- So our assumption that $k\geq2$ was incorrect

# Korselt's Criterion
Let $n$ be composite, then $n$ is Carmichael number iff
- $n$ is odd
- Every prime dividing $n$ satisfies two conditions
	1) $p^{2}\text{ }|\not\text{ }n$
	2) $(p-1)\text{ | }(n-1)$

# Miller's Test
Let $n$ is some be a big odd integer. We want to determine if $n$ is prime.

For some $b\in \mathbb{Z}^{+}$, $gcd(n,b)=1$ and $b^{n-1}\equiv 1\text{ (mod }n)$
Then, either $n$ is prime, or is a (Fermat) Pseudoprime to the base $b$

Let $x=b^{\frac{n-1}{2}}$, then $x^{2}=b^{n-1}\equiv 1\text{ (mod }n)$
- Recall [[7. Conguents#Theorem 4.12|Theorem 4.12]].
- So if $n$ is prime, $x=b^{\frac{n-1}{2}}\equiv \pm{1}\text{ (mod }n)$
	- Another primality test
	- If $b^{\frac{n-1}{2}}\equiv 1\text{ (mod }n)$, then consider $b^{\frac{n-1}{2\cdot 2}}$
	- Repeat until $x\equiv -1 \text{ (mod }n)$

## Miller's Test
Let $n\in\mathbb{Z}$ with $n>2$ and $n-1=2^{s}t$ ($s$ is some non-neg and $t$ is odd positive)

$n$ passes Miller's Test for the base $b$ if
1) $b^{t}\equiv 1\text{ (mod }n)$
Or
2) $b^{2^{j}t}\equiv -1\text{ (mod }n)$ for some $j:0\leq j\leq s-1$

## Theorem 6.8
If $n$ is prime and $b\in\mathbb{Z}^{+}$ with $n \text{ }|\not\text{ }b$, then $n$ passes Miller's Test for base $b$
- Contrapositive: If $n$ does not passes, then $n$ is not prime

## Example) Our Carmichael Number 561
$n=561$, then $n-1=560=2^{4}\cdot35$
- $s=4$ and $t=35$

Let's try with $b=2$
1) $b^{t}=2^{35}\equiv 263 \text{ (mod }561)$
2) There is no $j$ that $b^{2^{j}t}\equiv -1\text{ (mod }n)$
	$2^{2\cdot 35}\equiv 166 \text{ (mod }561)$
	$2^{2^{2}\cdot 35}\equiv 67 \text{ (mod }561)$
	$2^{2^{3}\cdot 35}\equiv 1 \text{ (mod }561)$

561 does not pass the Miller's Theorem, thus it is not prime

# Theorem 6.10
If $n$ is an odd positive composite integer, then $n$ passes Miller's Test for at most $\frac{n-1}{4}$ bases $b$ with $b\in\{1,2,\dots n-1\}$
- Take $k$ random integers from $\{1,2,\dots n-1\}$. If $n$ is composite, the probability that $n$ passes all $k$ test is $<\left( \frac{1}{4} \right)^{k}$

## Can we restrict $b$ more?
Suppose $n$ is some composite and we consider $b:1\leq b\leq n-1$
- What happen if $gcd(b,n)=d>1$?
- $dk=n$ and $dl=b$ 

Suppose for contrapositive, assume passes Miller's Test, $b^{y}=\pm 1\text{ (mod }n)$
- $nq= b^{y}\pm 1$

Then, 
- $dkq = d^{y}\cdot l^{y}\pm 1$
- $d(kq- d^{y-1}\cdot l^{y})=\pm 1$

Implies $d\text{ | }1$ or $d\text{ | }-1$
- This contradicts that $d>1$, thus $n$ does not pass Miller's Test if $gcd(b,n)>1$

Therefore, we can restrict $b$ value that $1\leq b\leq n-1$ and $gcd(n,b)=1$
- Defined as $\phi(n)$


---
# Binomial Theorem
$$(s+t)^{k}=\sum^{k}_{i=0} {}_{k}C_{i} \cdot s^{k-i}\cdot t^{i}$$


Suppose we wish to know if there is some power (depending on $m$) such that $a^{?}\equiv 1\text{ (mod }m)$

Impossible if $a$ and $m$ are not relatively prime
- If $a^{k}\equiv 1\text{ (mod }m)$
	 $my=a^{k}-1$
	 $a^{k}-my=1$
	 $a(a^{k-1})+m(-y)=1$
	 $\therefore gcd(a,m)=1$

Consider a set $A=\{a\text{ | } 1\leq a\leq m \text{ \& }gcd(a,m)=1\}$
- $\phi(m)$

# Euler Phi Function $\phi(m)$
Let $m\in\mathbb{Z}^{+}$. Then Euler Phi Function $\phi(m)$ is defined to be the number of positive integers not exceeding $m$ that are relatively prime to $m$

Ex)
If $m$ is prime, then $\phi(m)=m-1$

Ex)
Suppose we want a power of 7 that is congruent to 1 modulo 10
- $7^{k}\equiv 1\text{ (mod }10)$

Consider $\phi(10)=4 \implies \{1,3,7,9\}$

Multiply each number by 7 $\implies \{7,21,49,63\}$

By taking mod 10 $\implies\{7,1,9,3\}$
- We got the same set again
- Looks like Fermat's Little Theorem

Then, 
$$(7\cdot(1))(7\cdot(3))(7\cdot(7))(7\cdot(9))\equiv 1\cdot 3\cdot 7 \cdot 9\text{ (mod }10)$$
$$7^{4}(1\cdot 3\cdot 5\cdot 7) \equiv 1\cdot 3\cdot 5\cdot 7\text{ (mod }10)$$
$$7^{4}\equiv 1\text{ (mod }10)$$
It seems liek $7^{\phi(10)}\equiv 1\text{ (mod }10)$

# Theorem 6.14: Euler's Theorem
If $m\in\mathbb{Z}^{+}$ and $a$ is an integer such that $gcd(a,m)=1$, then
$$a^{\phi(m)}\equiv 1\text{ (mod }m)$$

**Note)**
Since Euler's Theorem consider numbers that are relatively prime with $m$, we can't use complete system of residue, like we did to prove Fermat's Little Theorem. Instead, let's define another system

## Reduced Residue System Modulo $m$
Integers such that each element of the set if relatively prime to $m$ and no two distinct elements in the set are congruent modulo $m$
- Simply is a set of $\phi(m)$
- Start from Complete Residue System and remove element that is not relatively prime with $m$

Ex) 
Consider 6
- Complete Residue System mod 6 : $\{0,1,2,3,4, 5\}$
- Reduced Residue System mod 6 : $\{1,5\}$

## Proof)
Let $r_{1}, r_{2}\dots r_{\phi(m)}$ be reduced residue system mod $m$ were $r_{i}$ is the least positive residue mod $m$

Let $a$ be an integer such that $gcd(a,m)=1$
- Then, let's show $ar_{1}, ar_{2}, \dots ar_{\phi(m)}$ is a reduced residue system mod $m$

First $gcd(a,m)=1$ by assertion, and $gcd(r_{i}, m)=1$
- Then $gcd(ar_{i}, m)=1$

Suppose $ar_{i}\equiv ar_{j}\text{ (mod }m)$ for some $i\neq j$ and $1\leq i,j\leq\phi(m)$
- So, $m|a(r_{i}-r_{j})$

Since $gcd(a,m)=1$ this means $m|(r_{i}-r_{j})$
- Thus, $r_{i}\equiv r_{j}\text{ (mod }m)$
- But this is a contradiction since $r_{1}, r_{2}\dots r_{\phi(m)}$ is a reduced residue system mod $m$, thus $r_{i}\not\equiv r_{j}\text{ (mod }m)$ where $i\neq j$

So, $ar_{1}, ar_{2}\dots ar_{\phi(m)}$ is a reduced residue system mod $m$

So the least positive integers (mod $m$) of $ar_{1}, ar_{2}, \dots ar_{\phi(m)}$ are $r_{1}, r_{2}\dots r_{\phi(m)}$
- Not necessarily in the same order

Therefore, 
$$(ar_{1})(ar_{2})\dots(ar_{\phi(m)})\equiv r_{1}\cdot r_{2}\dots r_{\phi(m)}\text{ (mod }m)$$
$$a^{\phi(m)}\cdot r_{1}\cdot r_{2}\dots r_{\phi(m)}\equiv r_{1}\cdot r_{2}\dots r_{\phi(m)}\text{ (mod }m)$$
We can cancel $r_{i}$'s since each is relativelt prime to $m$,
$$\therefore  a^{\phi(m)}\equiv 1 \text{ (mod }m)$$
## Example)
Find the least non negative residue of $2^{121}$ mod $9$

So, $a=2$ and $m=9$, then $gcd(a,m)=1$

Then by Euler's Theorem, $2^{\phi(9)}\equiv 1\text{ (mod }9)$

Consider $\phi(9) \to\{1,2,4,5,7,8\}$
- $\phi(9)=6$

Since $121 = 20\cdot{6}+1$, 
- $2^{121} = (2^{6})^{20}\cdot 2\equiv 2\text{ (mod }9)$

## Example 2)
Find least positive residue $x\text{ (mod }10)$ of $3x\equiv 7\text{ (mod }10)$

Let $m=10$ and $a=3$.

Since $gcd(3,10)=1$, then by Euler's Theorem, 
$$3^{\phi(10)}\equiv 1\text{ (mod }10)$$
$\phi(10)=4$ $(\{1,3,7,9\})$
- Thus, $3^{4}\equiv 1\text{ (mod }10)$

This tells use that $3$ and $3^{3}$ are inverses mod $10$
- And $3^{2}$ is its own inverse

Multiply $3^{3}$ to both sides to the equation above
$3^{3}\cdot 3x\equiv 3^{3}\cdot7\text{ (mod }10)$
$3^{4}x\equiv x\equiv 3^{3}\cdot 7=27\cdot7\equiv9 \text{ (mod }m)$

---
# Chapter 7: Euler-Phi Function
How can we find $\phi(m)$?

If $m$ is prime, then $\phi(m)=m-1$
- How about its converse?

Suppose $m$ is an positive integer with $\phi(m)=m-1$

i) If $m$ is prime

ii) If $m=1$
- $\phi(1)=1\neq m-1=0$
- $m$ can't be $1$

iii) If $m$ is composite
- Then, $m$ would have some $d$ such that $d|m$ where $1<d<m$
- But $gcd(d,m)=d>1$
- Then, $\phi(m)\leq m-2$
- Which contradicts $\phi(m)=m-1$
- Thus, $m$ can't be conposite

# Multiplicative
An arithmetic function $f$ is called **multiplicative** if $f(mn)=f(m)f(n)$ whenever $m$ and $n$ are relatively prime positive integers
- Arithmetic Funtion means functions defined for all positive integer

And $f$ is **completely multiplicative** if $f(mn)=f(m)f(n)$ for all positive integers $m,n$

# Theorem 7.1
If $f$ is multiplicative function and if $n=p_{1}^{a_{1}}p_{2}^{a_{2}}\dots p_{s}^{a_{s}}$ is the prime factorization of positive integer $n$, then
$$f(n)=f(p_{1}^{a_{1}})\cdot f(p_{2}^{a_{2}})\dots f(p_{s}^{a_{s}})$$

# Theorem 7.2
Let $m\in \mathbb{Z}^{+}$, then $\phi(m)=m-1$ iff $m$ is prime

# Theorem 7.3
Let $p$ be prime, $k\in\mathbb{Z}^{+}$, then $\phi(p^{k})=p^{k}-p^{k-1}$

Let $m=p^{k}$ where $p$ is prime, $k$ is an integer $\geq 2$
- Let's count the integers $a:1\leq a\leq p^{k}$ that are not relatively prime to $m$
	- $p, 2p, 3p, \dots p^{k-1}p$
- $\phi(p^{k})=p^{k}-p^{k-1}$

# Theorem 7.4
Let $m,n$ be relatively prime positive integers, then $\phi(mn)=\phi(m)\cdot \phi(n)$

## Rough Work
Consider $\phi(42)$ and $\phi(6)\cdot\phi(7)$
Since $\phi(6)=2$, (1 and 5), Let's consider row 1 and 5 only at the below
- Then, crossout integers that is not relatively prime with 7

**1**   7  **13  19  25  31  37**
2  8  14  20  26  32  38
3  9  15  21  27  33  39
4 10 16  22  28  34  40
**5  11  17  23  29**  35  **41**
6 12 18  24  30  36  42

Consider row $i$
$$i\text{ / } 6+i\text{ / } 2(6)+i\text{ / } 3(6)+i\text{ / } 4(6)+i\text{ / } 5(6)+i\text{ / } 6(6)+i$$
$$=i\text{ / } 6+i \text{ / }12+i\text{ / } 18+i\text{ / } 24+i\text{ / } 30+i\text{ / } 36+i$$
$$\equiv i\text{ / }6+i\text{ / }5+i\text{ / }4+i\text{ / }3+i \text{ / } 2+i\text{ / }1+i\text{ (mod }7)$$

And this is a complete system of residue mod $7$ by [[9. Some Special Congruences#Lemma 4.1|Lemma 4.1]]
- Then, there is a reduced residue system mod $7$ of $\phi(7)$ integers, each relatively prime to $7$

As a result, there are $\phi(6)$ rows that contains some integers that are relatively prime with 42, and in each row, there are $\phi(7)$ integers that are relatively prime with 42

## Formal Proof
Consider following table,

1   $m+1$   $2m+1$   $\dots$   $(n-1)m+1$
2   $m+2$   $2m+2$   $\dots$   $(n-1)m+2$
3   $m+3$   $2m+3$   $\dots$   $(n-1)m+3$
$\vdots$        $\vdots$             $\vdots$                         $\vdots$
$m$     $2m$        $3m$     $\dots$           $nm$

Look at $\phi(m)$ rows where $m$ and $i$ are relatively prime

Consider row $i$, where $gcd(m,i)=1$
 
$$i\text{ / } m+i\text{ / }2m+i\text{ / }\dots\text{ / }(n-1)m+i$$
are all relatively prime to $m$
- Suppose for contradiction, $\exists \text{ }0\leq k\leq n-1$ such that $gcd(km+i, m)=d>1$
- $dx=m$, $dy=km+i$ for some $x,y\in\mathbb{Z}$
- Then, $i=d(y-kx)$, thus $d\text{ | }i$
- This contradicts $d\text{ | m}$ and $gcd(m,i)=1$

[[9. Some Special Congruences#Theorem 4.7|Theorem 4.7]] tells us that any row $i$ where $gcd(i,m)=1$, that row is a complete system of residue mod $n$
- Then, there are $\phi(n)$ integers in a reduced system of residue mod $n$ in that row
- And there are $\phi(m)$ possible rows

Therefore, there are $\phi(m)\cdot\phi(n)$ number of integers that is relatively prime to both $m$ and $n$, thus with $mn$

# Theorem 7.5
Let $n=p_{1}^{a_{1}}p_{2}^{a_{2}}\dots p_{k}^{a_{k}}$ be the prime power factoriation of $n$
$$\phi(n) = n \prod^{k}_{i=1}\left( 1-\frac{1}{p_{i}} \right)$$

**Proof)**
For each $\phi(p_{i}^{a_{i}})$, 
$=p_{i}^{a_{i}}-p_{i}^{a_{i-1}}$ by Theorem 7.3
$=p_{i}^{a_{i}}\left( 1-\frac{1}{p_{i}} \right)$

Therefore,
$$\phi(n)=\phi(p_{1}^{a_{1}})\phi(p_{2}^{a_{2}})\dots \phi(p_{k}^{a_{k}})$$
$$=p_{1}^{a_{1}}\left( 1-\frac{1}{p_{1}} \right)p_{2}^{a_{2}}\left( 1-\frac{1}{p_{2}} \right)\dots p_{k}^{a_{k}}\left( 1-\frac{1}{p_{k}} \right)$$
$$=p_{1}^{a_{1}}p_{2}^{a_{2}}\dots p_{k}^{a_{k}}\left( 1-\frac{1}{p_{1}} \right)\left( 1-\frac{1}{p_{2}} \right)\dots\left( 1-\frac{1}{p_{k}} \right)$$
$$=n\cdot \prod^{k}_{i=1}\left( 1-\frac{1}{p_{i}} \right)$$


# $\sigma$ Function
$\sigma$ is defined by setting $\sigma(n)$ equal to the sum of all positive divisor of $n$

**Ex)**
$\sigma(4) = 1+2+4=7$
$\sigma(9) = 1+3+9=13$

## Perfect Number
If $n\in\mathbb{Z}^{+}$ and $\sigma(n)=2n$ then $n$ is called a perfect number

## $\sigma(mn)$ is multiplicative
If $gcd(m,n)=1$, then $\sigma(mn)=\sigma(m)\sigma(n)$

## Lemma 7.1 
For $n=p^{a}$ where $p$ is prime and $a\in\mathbb{Z}^{+}$, 
$$\sigma(n)=\frac{p^{a+1}-1}{p-1}$$

Let $n=p^{a}$ where $p$ is prime, $a\in\mathbb{Z}^{+}$
- Then, $\sigma(n)=1+p+p^{2}\dots p^{a}$
- Since this is a geometric series, $\sigma(n)=\frac{p^{a+1}-1}{p-1}$

# Theorem 7.9
Let $n=p_{1}^{a_{1}}p_{2}^{a_{2}}\dots p_{k}^{a_{k}}$ be the prime power factorization of $n$, then
$$\sigma(n)=\prod^{k}_{i=1}\sigma(p_{i}^{a_{i}})$$
$$=\prod^{k}_{i=1}\left( \frac{p^{a_{i}+1}-1}{p_{i}-1} \right)$$

# Mersenne Prime
Consider Geometric Series
$$1+x+x^{2}+\dots x^{n-1}=\frac{x^{n}-1}{x-1}$$
$$(x-1)(1+x+x^{2}\dots x^{n-1})=x^{n}-1$$
So, $(x-1)\text{ | }(x^{n}-1)$

Assuming $x\in\mathbb{Z}, n\in \mathbb{Z}^{+}$, if $x>2$, then $x^{n}$ is composite
- Since $x-1$ which is neither $1$ nor $x^{n}-1$ can divide $x^{n}-1$

Then, consider when $x=2$
- Is $2^{n}-1$ prime or composite?
	- $n=2\implies 3$
	- $n= 4 \implies 15$
- It can be both

## $n$ is composite
Suppose $n$ is composite. Then $n=st$ for some $s,t\in\mathbb{Z}$, where $1<s\leq t<n$

Consider $2^{n}-1$
$$=(2^{s})^{t}-1$$
$$=(2^{s}-1)(1+2^{s}+(2^{s})^{2}\dots +(2^{s})^{t-2}+(2^{s})^{t-1})$$

Thus, 
$$(2^{s}-1)\text{ | }(2^{n}-1)$$
Since $s>1$, $2^{s}-1\neq 1$.
- Therefore, if $n$ is composite, then $2^{n}-1$ is also composite

## $n$ is prime
$2^{n}-1$ still can be prime or composite
- $2^{3}-1=7$
- $2^{11}-1 = 23\cdot 89$

## Mersenne Number / Mersenne Prime
Let $n\in\mathbb{Z}^{+}$. Then $M_{n}=2^{n}-1$  is the $n^{th}$ Mersenne number

Let $p$ is prime, if $M_{p} = 2^{p}-1$ is prime, then $M_{p}$ is a Mersenne Prime

## Theorem 7.10
Let $n$ be even positive integer. Then, $n$ is a perfect number iff $n=2^{m-1}(2^{m}-1)$ where $m\in\mathbb{Z}^{+},m\geq2$ and $2^{m}-1$ is prime

**Forward Direction)**
Suppose $n$ is even positive integer, $\sigma(n)=2n$
Let $n=2^{s}t$ where $s,t\in\mathbb{Z}^{+}$ and $t$ is odd
$$\sigma(n)=2n=2^{s+1}t$$
Since $2$ and $t$ are relatively prime, 
$$\sigma(n)=\sigma(2^{s}t)=\sigma(2^{s})\sigma(t)=(2^{s+1}-1)\sigma(t)$$

Therefore, 
$$2^{s+1}t=(2^{s+1}-1)\sigma(t)$$
- Since $2^{s+1}-1$ is odd, $\sigma(t)$ must be even
- $\therefore{2}^{s+1}\text{ | }\sigma(t)$
- $\sigma(t)=2^{s+1}k$ $(k\in\mathbb{Z}^{+})$

So, 
$$2^{s+1}t=(2^{s+1}-1)2^{s+1}k$$
$$t=(2^{s+1}-1)k$$
- $k\neq t$ but $k\text{ | }t$
$$t=2^{s+1}k-k=\sigma(t)-k$$
$$\sigma(t)=k+t$$
1. If $k=1$, then $\sigma(t)=t+1\implies$ tells us that $t$ must be prime
2. If $k\neq 1$, then $t\neq 2^{s+1}-1$
	- Thus, $t$ has at least three divisor $(2^{s+1}-1)\text{ | }t$, $k\text{ | }t$ and $t\text{ | }t$ 
	- $\sigma(t)\geq (2^{s+1}-1)+k+t>\sigma(t)=k+t$
	- This is an contradiction, so $k\neq 1$

**Backward Direction)**
Suppose $2^{m}-1$ is prime for some $m\in\mathbb{Z}^{+}, m\geq 2$
- Then, $\sigma(2^{m}-1)=1+2^{m}-1=2^{m}$

Consider $\sigma(2^{m-1})$. Since this is sum of geometric series, 
- $=\frac{2^{m}-1}{2-1}=2^{m}-1$

Consider $\sigma(2^{m-1}(2^{m}-1))=\sigma(2^{m-1})\sigma(2^{m}-1)=2^{m}\cdot(2^{m}-1)=2(2^{m-1})(2^{m}-1)$
- Thus $2^{m-1}(2^{m}-1)$ is a perfect number
- Let's call this $n$
	- Then $n$ is even



