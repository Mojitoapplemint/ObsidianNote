MARL algorithms are designed to learn a joint policy that satisfies the properties of a specific solution concept (e.g., Nash equilibrium)

1. Policies are conditioned on observation histories
	- How many possible observation each agent can have?
	- $\{ 1,2,3 \}\times \{ 3, \{ 4,5 \} \}\implies |O_{i}|=6$ local observation(projection)
2. All agents share the common reward function

# Central Q Learning
Q table
- Column : All possible joint action
- Row: All possible State

| $S$ \ $A$ | (O,O) | (O,X) | (X,O) | (X,X) |
| --------- | ----- | ----- | ----- | ----- |
| $s_{0}$   |       |       |       |       |
| $\vdots$  |       |       |       |       |
| $s_t$     |       |       |       |       |
# Environment
## Control Policy
All doors are opened as default
- Control Policy refers that which event should be disabled (a.k.a Which door should be closed)

**Q)** Closed door is assumed to be opened automatically at the next time step?

## Reward Function
1. Have some instance variables that stores agents' state from previous time step
2. If both cat and mouse moved after applying joint policy, they get +1
3. (3,3) happens, then both get -100

**Note)**
Negative Reward when closing the door?
- For now, no 

# Limitation
The computation is not that efficient(?)
- [[marl-book.pdf#page=112&selection=50,0,52,38|The Complexity of Computing Equilibria]]



