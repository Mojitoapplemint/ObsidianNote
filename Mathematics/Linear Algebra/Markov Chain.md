Probabilistic model, system evolving over finite number of states over times
At each time step, either
- Stay in current state with some probability
- Move to a different state with some probability

# Mouse Maze
![[Pasted image 20241229182942.png|300]]
1. Initially there is mouse at $R_{1}$
2. Every time bell rings, mouse must move to adjacent room by door
	- Each door has the same probability of passing by
3. What is the probability after $n$ bell rings and mouse at $R_{i}$?

## Transition Matrix and MatMul
Transition Matrix $P$ : Each column is sum of all possibilities of certain state from the starting state
- Columns always sum to 1

Starting State Vector $\vec{x_{0}}=\begin{bmatrix}R_{1} \\ R_{2} \\ R_{3}\end{bmatrix}=\begin{bmatrix}1 \\ 0 \\ 0\end{bmatrix}$
- Since Mouse is initially at $R_{1}$