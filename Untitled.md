Suppose for Contradiction, let $n$ satisfies $\phi(n)=2p$. Let $n=p_1^{a_{1}}p_{2}^{a_{2}}\dots p_{k}^{a_{k}}$ be prime factorization. Then, by Theorem 7.1 and Theorem 7.3, 
$$\phi(n)=p_{1}^{a_{1}-1}(p_{1}-1)\cdot p_{2}^{a_{2}-1}(p_{2}-1)\cdots p_{k}^{a_{k}-1}(p_{k}-1)$$

i) If $p\text{ }|\not\text{ }n$ (i.e. $p\not\in \{ p_{1},p_{2}..p_{k} \}$)

Observe that $p\neq 1$ since $p$ is prime

Observe that $p\neq 2$ since $p \equiv 1\text{ (mod }3)$, then $p$ is odd. 

Therefore, since $\forall \text{ }i\text{ }(1\leq i\leq k)$, $p_{i}-1$ is either even or 1, $p\not\in \{ p_{1}-1,p_{2}-1\dots p_{k}-1 \}$

This implies that $\forall \text{ }i\text{ }(1\leq i\leq k)$, $p\neq p_{i}^{a_{i}-1}$ and $p\neq p_{i}-1$

Thus, $p\text{ }|\not\text{ }\phi(n)$ which contradicts that $\phi(n)=2p$

ii) If $p\text{ | }\phi(n)$, then let $n=p_1^{a_{1}}p_{2}^{a_{2}}\dots p^{a}\dots p_{k}^{a_{k}}$ Then, 
$$\phi(n)=p_{1}^{a_{1}-1}(p_{1}-1)\cdot p_{2}^{a_{2}-1}(p_{2}-1)\cdots p^{a-1}(p-1)\dots p_{k}^{a_{k}-1}(p_{k}-1)$$

Thus, $(p-1)\text{ | }\phi(n) \cdots (1)$ 

Since $\phi(n)=2p$, $\phi(n)\equiv 2\text{ (mod }3)$

Then, since $p\equiv 1\text{ (mod }3)$, $3\text{ | }(p-1)\cdots (2)$

By (1) and (2), $3\text{ | }\phi(n)$, which contradicts $\phi(n)\equiv 2\text{ (mod }3)$

Therefore since there are contradictions in both cases, $\phi(n)=2p$ does not have any solutions.