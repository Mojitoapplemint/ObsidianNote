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

This then unvectorized as follows:

$\begin{bmatrix}1\\0\\1\\-1\end{bmatrix}= \begin{bmatrix}1&0\\0&0\end{bmatrix}+ \begin{bmatrix}0&0\\1&0\end{bmatrix}- \begin{bmatrix}0&0\\0&1\end{bmatrix}= \begin{bmatrix}1&0\\1&-1\end{bmatrix}$

$\begin{bmatrix}0\\1\\0\\0\end{bmatrix}= \begin{bmatrix}0&1\\0&0\end{bmatrix}$

Therefore, the basis of $\text{range}(T)$ is $\Big\{ \begin{bmatrix}1&0\\1&-1\end{bmatrix} , \begin{bmatrix}0&1\\0&0\end{bmatrix}\Big\}$
