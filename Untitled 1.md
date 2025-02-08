No.2

a)

Let $B=\{ E_{11}, E_{12}, E_{21}, E_{22} \}$ be a standard matrix of $\mathcal{M}_{2}(\mathbb{C})$.

Consider $T\left( \begin{bmatrix}1&0\\0&0\end{bmatrix} \right)$, $T\left( \begin{bmatrix}0&1\\0&0\end{bmatrix} \right)$, $T\left( \begin{bmatrix}0&0\\1&0\end{bmatrix} \right)$, $T\left( \begin{bmatrix}0&0\\0&1\end{bmatrix} \right)$

$T\left( \begin{bmatrix}1&0\\0&0\end{bmatrix} \right)=\begin{bmatrix}1&2\\0&3\end{bmatrix}\begin{bmatrix}1&0\\0&0\end{bmatrix}-\begin{bmatrix}1&0\\0&0\end{bmatrix}\begin{bmatrix}1&2\\0&3\end{bmatrix}$ 

$=\begin{bmatrix}1&0\\0&0\end{bmatrix}-\begin{bmatrix}1&2\\0&0\end{bmatrix}=\begin{bmatrix}0&-2\\0&0\end{bmatrix}$


$T\left( \begin{bmatrix}0&1\\0&0\end{bmatrix} \right)=\begin{bmatrix}1&2\\0&3\end{bmatrix}\begin{bmatrix}0&1\\0&0\end{bmatrix}-\begin{bmatrix}0&1\\0&0\end{bmatrix}\begin{bmatrix}1&2\\0&3\end{bmatrix}$ 

$=\begin{bmatrix}0&1\\0&0\end{bmatrix}-\begin{bmatrix}0&3\\0&0\end{bmatrix}=\begin{bmatrix}0&-2\\0&0\end{bmatrix}$


$T\left( \begin{bmatrix}0&0\\1&0\end{bmatrix} \right)=\begin{bmatrix}1&2\\0&3\end{bmatrix}\begin{bmatrix}0&0\\1&0\end{bmatrix}-\begin{bmatrix}0&0\\1&0\end{bmatrix}\begin{bmatrix}1&2\\0&3\end{bmatrix}$ 

$=\begin{bmatrix}2&0\\3&0\end{bmatrix}-\begin{bmatrix}0&0\\1&2\end{bmatrix}=\begin{bmatrix}2&0\\2&-2\end{bmatrix}$


$T\left( \begin{bmatrix}0&0\\0&1\end{bmatrix} \right)=\begin{bmatrix}1&2\\0&3\end{bmatrix}\begin{bmatrix}0&0\\0&1\end{bmatrix}-\begin{bmatrix}0&0\\0&1\end{bmatrix}\begin{bmatrix}1&2\\0&3\end{bmatrix}$ 

$=\begin{bmatrix}0&2\\0&3\end{bmatrix}-\begin{bmatrix}0&0\\0&3\end{bmatrix}=\begin{bmatrix}0&2\\0&0\end{bmatrix}$

$\therefore[T]_{B}=\begin{bmatrix}0&0&2&0\\-2&-2&0&2\\0&0&2&0\\0&0&-2&0\end{bmatrix}$

b)
$\begin{bmatrix}0&0&2&0\\-2&-2&0&2\\0&0&2&0\\0&0&-2&0\end{bmatrix}\xrightarrow{R_{1}\leftrightarrow R_{2}}\begin{bmatrix}-2&-2&0&2\\0&0&2&0\\0&0&2&0\\0&0&-2&0\end{bmatrix}\xrightarrow{R_{3}- R_{2}}\begin{bmatrix}-2&-2&0&2\\0&0&2&0\\0&0&0&0\\0&0&-2&0\end{bmatrix}\xrightarrow{R_{4}+ R_{2}}\begin{bmatrix}-2&-2&0&2\\0&0&2&0\\0&0&0&0\\0&0&0&0\end{bmatrix}$
In REF, there are 2 leading variables, thus $\text{rank}(T)=2$

There are 2 free variables, thus $\text{nullity}(T)=2$

c)

i) Basis of $\text{range}(T)=\{T(\vec{v}) \text{ | }\vec{v}\in \mathcal{M}_{2}(\mathbb{C}) \}$

Consider $\text{range}([T]_{B})=\text{span}\Big(\begin{bmatrix}0\\-2\\0\\0\end{bmatrix},\begin{bmatrix}0\\-2\\0\\0\end{bmatrix}, \begin{bmatrix}2\\0\\2\\-2\end{bmatrix}, \begin{bmatrix}0\\2\\0\\0\end{bmatrix}\Big)$. Since $\begin{bmatrix}0\\2\\0\\0\end{bmatrix}$ and $\begin{bmatrix}0\\-2\\0\\0\end{bmatrix}$ are scalar multiplication of each other, there is redundancy.

$\text{span}\Big(\begin{bmatrix}0\\-2\\0\\0\end{bmatrix},\begin{bmatrix}0\\-2\\0\\0\end{bmatrix}, \begin{bmatrix}2\\0\\2\\-2\end{bmatrix}, \begin{bmatrix}0\\2\\0\\0\end{bmatrix}\Big)=\text{span}\Big( \begin{bmatrix}2\\0\\2\\-2\end{bmatrix}, \begin{bmatrix}0\\2\\0\\0\end{bmatrix}\Big)=\text{span}\Big( \begin{bmatrix}1\\0\\1\\-1\end{bmatrix}, \begin{bmatrix}0\\1\\0\\0\end{bmatrix}\Big)$

Since $\begin{bmatrix}1\\0\\1\\-1\end{bmatrix}, \begin{bmatrix}0\\1\\0\\0\end{bmatrix}$ are linearly independent, the basis of $\text{range}([T]_{B})$ is $\Big\{ \begin{bmatrix}1\\0\\1\\-1\end{bmatrix}, \begin{bmatrix}0\\1\\0\\0\end{bmatrix} \Big\}$

Since this is the basis based on standard matrix of $T$, we need to unvectorize it as follows:

$\begin{bmatrix}1\\0\\1\\-1\end{bmatrix}= \begin{bmatrix}1&0\\0&0\end{bmatrix}+ \begin{bmatrix}0&0\\1&0\end{bmatrix}- \begin{bmatrix}0&0\\0&1\end{bmatrix}= \begin{bmatrix}1&0\\1&-1\end{bmatrix}$

$\begin{bmatrix}0\\1\\0\\0\end{bmatrix}= \begin{bmatrix}0&1\\0&0\end{bmatrix}$

Therefore, the basis of $\text{range}(T)$ is $\Big\{ \begin{bmatrix}1&0\\1&-1\end{bmatrix} , \begin{bmatrix}0&1\\0&0\end{bmatrix}\Big\}$

ii) Basis of $\text{null}(T)=\{ \vec{v}\in \mathcal{M}_{2}(\mathbb{C})\text{ | } T(\vec{v})=0\}$

Consider $\text{null}([T]_{B})$

From part a),

$\begin{bmatrix}0&0&2&0&|&0\\-2&-2&0&2&|&0\\0&0&2&0&|&0\\0&0&-2&0&|&0\end{bmatrix}\xrightarrow{\text{Row Operations}}\begin{bmatrix}-2&-2&0&2&|&0\\0&0&2&0&|&0\\0&0&0&0&|&0\\0&0&0&0&|&0\end{bmatrix}$

$-x_{1}-x_{2}+x_{4}=0 \implies x_{1}=-x_{2}+x_{4}$, $x_{3}=0$, $x_{2}$ and $x_{4}$ are free. Thus
$\vec{x}=\begin{bmatrix}x_{1}\\x_{2}\\x_{3}\\x_{4}\end{bmatrix}=\begin{bmatrix}-x_{2}+x_{4}\\x_{2}\\0\\x_{4}\end{bmatrix}=x_{2}\cdot\begin{bmatrix}-1\\1\\0\\0\end{bmatrix}+x_{4}\cdot \begin{bmatrix}1\\0\\0\\1\end{bmatrix}=\text{span}\Big(\begin{bmatrix}-1\\1\\0\\0\end{bmatrix}, \begin{bmatrix}1\\0\\0\\1\end{bmatrix}\Big)$

Since $\begin{bmatrix}-1\\1\\0\\0\end{bmatrix}, \begin{bmatrix}1\\0\\0\\1\end{bmatrix}$ are linearly independent, the basis of $\text{null}([T_{B}])$ is $\Big\{ \begin{bmatrix}-1\\1\\0\\0\end{bmatrix}, \begin{bmatrix}1\\0\\0\\1\end{bmatrix} \Big\}$.

Since this is the basis based on standard matrix of $T$, we need to unvectorize it as follows:

$\begin{bmatrix}-1\\1\\0\\0\end{bmatrix}=-1\cdot\begin{bmatrix}1&0\\0&0\end{bmatrix}+\begin{bmatrix}0&1\\0&0\end{bmatrix}=\begin{bmatrix}-1&1\\0&0\end{bmatrix}$

$\begin{bmatrix}1\\0\\0\\1\end{bmatrix}=\begin{bmatrix}1&0\\0&0\end{bmatrix}+\begin{bmatrix}0&0\\0&1\end{bmatrix}=\begin{bmatrix}1&0\\0&1\end{bmatrix}$

Therefore, the basis of $\text{null}([T]_{B})=\Big\{ \begin{bmatrix}-1&1\\0&0\end{bmatrix}, \begin{bmatrix}1&0\\0&1\end{bmatrix} \Big\}$

d)
Consider $\det([T]_{B}-\lambda I)$

$\begin{vmatrix}-\lambda&0&2&0\\-2&-2-\lambda&0&2\\0&0&2-\lambda&0\\0&0&-2&-\lambda\end{vmatrix}=(-\lambda)\begin{vmatrix}-2-\lambda&0&2\\0&2-\lambda&0\\0&-2&-\lambda\end{vmatrix}+2\begin{vmatrix}-2&-2-\lambda&2\\0&0&0\\0&0&-\lambda\end{vmatrix}$

Since $\begin{bmatrix}-2&-2-\lambda&2\\0&0&0\\0&0&-\lambda\end{bmatrix}$ has zero row, its determinant is zero.

$=(-\lambda)\begin{vmatrix}-2-\lambda&0&2\\0&2-\lambda&0\\0&-2&-\lambda\end{vmatrix}=(-\lambda)(-2-\lambda)\begin{vmatrix}2-\lambda&0\\-2&-\lambda\end{vmatrix}=(-\lambda)(-2-\lambda)(2-\lambda)(-\lambda)=-\lambda^{2}(2+\lambda)(2-\lambda)$
Therefore, eigenvalues are 0,-2, and 2.

e)

If $T(X)=2X$, then $[T]_{B}\cdot[X]_{B}=2[X]_{B}$. Then $[T]_{B}\cdot[X]_{B}-2[X]_{B}=0\implies([T]_{B}-2I)[X]_{B}=\vec{0}$
- This implies that $[X]_{B}$ is solution for $\Big[[T]_{B}-2I\text{ | }\vec{0}\Big]$

Consider $\Big[[T]_{B}-2I\text{ | }\vec{0}\Big]$
$\begin{bmatrix}-2&0&2&0&|&0\\-2&-4&0&2&|&0\\0&0&0&0&|&0\\0&0&-2&-2&|&0\end{bmatrix}\xrightarrow{R_{1}+R_{4}}\begin{bmatrix}-2&0&0&-2&|&0\\-2&-4&0&2&|&0\\0&0&0&0&|&0\\0&0&-2&-2&|&0\end{bmatrix}\xrightarrow{R_{2}-R_{1}}\begin{bmatrix}-2&0&0&-2&|&0\\0&-4&0&4&|&0\\0&0&0&0&|&0\\0&0&-2&-2&|&0\end{bmatrix}$
$\xrightarrow{R_{3}\leftrightarrow R_{4}}\begin{bmatrix}-2&0&0&-2&|&0\\0&-4&0&4&|&0\\0&0&-2&-2&|&0\\0&0&0&0&|&0\end{bmatrix}\xrightarrow{-\frac{1}{2}R_{1}\text{ , } \frac{1}{4}R_{2}\text{ , } -\frac{1}{2}R_{3}}\begin{bmatrix}1&0&0&1&|&0\\0&-1&0&1&|&0\\0&0&1&1&|&0\\0&0&0&0&|&0\end{bmatrix}$


$x_{1}=-x_{4}, x_{2}=x_{4}, x_{3}=-x_{4}$ and $x_{4}$ is free. Thus, $[X]_{B}=\text{span}\Big(\begin{bmatrix}-1\\1\\-1\\1\end{bmatrix}\Big)$

This is standard unvectorized as

$-\begin{bmatrix}1&0\\0&0\end{bmatrix}+\begin{bmatrix}0&1\\0&0\end{bmatrix}-\begin{bmatrix}0&0\\1&0\end{bmatrix}+\begin{bmatrix}0&0\\0&1\end{bmatrix}=\begin{bmatrix}-1&1\\-1&1\end{bmatrix}$


$\therefore X=c\begin{bmatrix}-1&1\\-1&1\end{bmatrix}$ where $c\in\mathbb{C}$ (e.g. $\begin{bmatrix}-1&1\\-1&1\end{bmatrix}$)


No. 3 

