We've learned that if $gcd(a,n)=1$, then $a^{\phi(n)}\equiv 1\text{ (mod }n)$ by Euler's Theorem

Since there is at least one possible $x$ that satisfies $a^{x}\equiv 1\text{ (mod }n)$, smallest $x$ would exist by Well-Ordering Principle.

# Order
Let $gcd(a,n)=1$ and $a\neq 0, n\in\mathbb{Z}^{+}$. The least positive integer $x$ such that
$$a^{x}\equiv 1\text{ (mod }n)$$
is the order of $a$ modulo $n$ denoted as $ord_{n}(a)$

**Ex)**
Consider $2^{x}\equiv 1\text{ (mod }9)$
- By Euler's Theorem, $2^{\phi(9)}=2^{6}\equiv 1\text{ (mod }9)$
- We can manually subsitute $x=1,2,3,4,5$ to verify that $6$ is the smallest entry
- $ord_{9}(2)=6$

**Ex)**
Consider $ord_{13}(10)$
- By Euler's Theorem, $10^{\phi(13)}=10^{12}\equiv 1\text{ (mod }13)$
- So, $ord_{13}(10)\leq12$

