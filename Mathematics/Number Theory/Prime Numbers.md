# Lemma 3.1: Every integer greater than 1 has a prime diviser
For proof by contradiction, suppose *there is positive integer greater than 1 that has no prime divisers*
- Let $n$ be the smallest positive integer greater than 1 that has no prime divisers

If $n$ is prime, we have a contradiction that it has $n$ itself as prime diviser

Otherwise, $n$ is composite 
- $\exists \text{ }a,b\in\mathbb{Z}$ with $1<a, b<n$ and $ab=n$
- Since $n$ is the smallest positive integer greater than 1 that has no prime diviser and $a<n$, $a$ must have prime diviser. Let it $x$
- BY theorem 1.8, since $x$ divides $a$ and $a$ divides $n$, we can get $x$ can divide $n$
- Again there is contradiction that $n$ has prime diviser $x$

Therefore, every integer greater than 1 has a prime diviser by proof by contradiction

# Theorem 3.1: There are infinitely many primes
For proof by contradiction, suppose there is finite amount, $n$ prime numbers
- $p_{1}, p_{2}, p_{3}, \dots p_{n}$ are all the primes

Let $A=p_{1}\cdot p_{2}\cdot\dots p_{n}+1$
by Lemma 3.1, $A$ has a prime diviser, $p_{k}\text{ }\{1<k<n\}$ 
- So $\exists \text{ }x\in\mathbb{Z}$ such that $p_{k}\cdot x=A$

Then, $1=A-p_{1}\cdot p_{2} \dots p_{n}$
$1=p_{k}\cdot x-p_{1}\cdot p_{2} \dots p_{n}$
$1=p_{k}(x-p_{1}\cdot p_{2} \dots p_{k-1}\cdot p_{k+1}\dots p_{n})$
- This indicates $p_{k} \text{ | } 1$, which is impossible.
- I.e. there is no such prime number that divides 1 and get another integer, "$x-p_{1}\cdot p_{2} \dots p_{k-1}\cdot p_{k+1}\dots p_{n}$"

Therefore, there is a contradiction, thus there are infinitely many prime numbers

# Theorem 3.2: If $n$ is a composite integer, then $n$ has a prime factor not exceeding $\sqrt{ n }$
Let $n=ab$ where $a,b\in\mathbb{Z}:1<a\leq b<n$

Certainly $a\leq\sqrt{ n }$ because otherwise $\sqrt{ n }\leq a\leq b$
- Then, $ab\geq\sqrt{ n }\sqrt{ n }=n$

Since $a>1$, it has a prime diviser, $x$, thus $x\leq a$
- $x\leq a\leq\sqrt{ n }$, $x\text{ | }a, a\text{ | }n$
- So $x \text{ | }n$

Therefore, $x$ is a prime diviser of $n$ that not exceeding $\sqrt{ n }$

# The Sieve of Eratosthenes
The function $\pi(n)$ where $n$ is positive real number, denotes the number of primes not exceeding $n$

## The Prime Number Theorem
$$\lim_{x\to \infty}{\frac{\pi(x)}{x/\ln(x)}}=1$$
We often write $a(x)$~$b(x)$ to denote $\lim_{x\to \infty}{\frac{a(x)}{b(x)}}=1$ and say "$a(x)$ is asymptotic to $b(x)$"
- $\pi(x)$ ~ $x/\ln(x)$

#