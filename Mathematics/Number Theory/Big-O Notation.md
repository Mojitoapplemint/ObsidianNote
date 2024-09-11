# Big-O Notation Definition
Let $f,g$ be functions $\mathbb{Z}^{+}\rightarrow \mathbb{R}$. Then $f=O(g)$ if there is an integer $n_{0}$ and positive real number $c$ such that $|f(n)|\leq c|g(n)|$ for all $n\geq n_{0}$
- $f$ is called Complexity Function
- For some measure $n$ of the size of the input, $f(n)$ is an upper bound for the number of operations required to carry out the algorithm

**Ex)**
Prove that $\frac{n(n-1)}{2}=O(n^{2})$

$$|\frac{1}{2}n^{2}-\frac{1}{2}n|=\frac{1}{2}|n| |n-1|$$
$$\leq\frac{1}{2}n(n-1)\text{ since }n\geq 1$$
$$=\frac{1}{2}n^{2}-\frac{1}{2}n$$
$$\leq\frac{1}{2}n^{2}$$
$$\leq n^{2}$$
Thus, $|\frac{1}{2}n^{2}-\frac{1}{2}n|\leq c|n^{2}|$ for all $n\geq 1$

# Smaller Order