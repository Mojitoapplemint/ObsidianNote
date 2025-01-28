MARL algorithms are designed to learn a joint policy that satisfies the properties of a specific solution concept (e.g., Nash equilibrium)

1. Policies are conditioned on observation histories
	- How many possible observation each agent can have?
	- $\{ 1,2,3 \}\times \{ 3, \{ 4,5 \} \}\implies |O_{i}|=6$ local observation(projection)
2. All agents share the common reward function

# POSG Procedure
1. The game starts in an initial state $s^{0}\in S$ sampled from $\mu$
2. At time $t$, given the current state $s^{t}\in S$ and previous joint action $a^{t-1}\in A$ (for $t=0$, we set $a^{t-1}=\emptyset$), each agent receives an observation $o^{t}_{i}\in O_{i}$
3. Each agent chooses an action $a^{t}_{i}\in A_{i}$ based on action probabilities given by its policy $\pi_{i}(a^{t}_{i}\text{ | }h^{t}_{i})$ which forms joint action
	- $h^{t}$ here refers to agent $i$'s *observation history* $h^{t}_{i}=(o^{0}_{i}, \dots o^{t}_{i})$
	- Note that agent's observation may or may not include other's action
4. With joint action, the game transitions into the next state $s^{t+1}\in S$ with probability $\mathcal{T}(s^{t+1}\text{ | }s^{t}, a^{t})$ and each agent $i$ receives reward $r_{i}=\mathcal{R}_{i}(s^{t}, a^{t}, s^{t+1})$
5. Repeat 1~4 until reaching a terminal state $s^{t}\in \bar{S}$

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
- For now, no because the reward should be assign on what we want to achieve or do not want to, not how

# Central Q Learning
Q table
- Column : All possible joint action
- Row: All possible State

| $S$ \ $A$ | (O,O) | (O,X) | (X,O) | (X,X) |
| --------- | ----- | ----- | ----- | ----- |
| $s^{0}$   |       |       |       |       |
| $\vdots$  |       |       |       |       |
| $s^{t}$   |       |       |       |       |

## CQL algorithm for stochastic games
Initialize : $Q(s,a)=0$ for all $s\in S$ and $a\in A=A_{1}\dots A_{n}$
Repeat for every episodes:
**for** $t=0,1,\dots$ **do**
- Observe current state $s'$
- with probability $\epsilon$ : choose random joint action $a^{t}\in A$
- Otherwise : Choose joing action $a^{t}=\arg\max_{a}Q(s^{t}, a)$
- Apply joint action $a^{t}$, observe reward $r^{t}_{1}, \dots r^{t}_{n}$ and next state $s^{t+1}$
- Transform $r^{t}_{1}\dots r^{t}_{n}$ into scalar reward $r^{t}$
- $Q(s^{t}, a^{t})\leftarrow Q(s^{t}, a^{t})+\alpha[r^{t}+\gamma\displaystyle\max_{a'}Q(s^{t+1}, a')-Q(s^{t}, a^{t})]$

# Independent Q Learning
Each agent $i$ learns its own policy $\pi_{i}$ using only its local history of own observations, actions, and rewards, while ignoring the existence of other agents
- Effects of other agent's actions are simply part of the environment dynamics in perspective of $i$

From the perspective of each agent, policies of other agents become part of the environment's state transition function
$$\mathcal{T}_{i}(s^{t+1}\text{ | }s^{t}, a^{6})\propto \sum_{a_{-i}\in A_{-i}}\mathcal{T}(s^{t+1}\text{ | }s^{t},\langle a^{t}_{i}, a_{-i} \rangle)\prod_{j\neq i}\pi_{j}(a_{j}\text{ | }s^{t})$$

Q table
- Column : All possible Action
- Row: All possible State

For each agent $i$,

| $S$ \ $A$   | O   | X   |
| ----------- | --- | --- |
| $s^{0}_{i}$ |     |     |
| $\vdots$    |     |     |
| $s^{t}_{i}$ |     |     |


## Independent Q Learning
// Algorithm controls agent $i$
1. Initialize : $Q_{i}(s, a_{i})=0$ for all $s\in S, a_{i}\in A_{i}$
2. Repeat for every episode : 
3. **For** $t=0,1,2\dots$ **do** 
	1. Observe current state $s'$
	2. With probability $\epsilon$ : choose random joint action $a^{t}_{i}\in A_{i}$
	3. Otherwise : Choose joing action $a^{t}_{i}\in\arg\max_{a_{i}}Q_{i}(s^{t}, a_{i})$
	4. (Meanwhile, other agents choose their action $a_{j}^{t}$)
	5. Observe own reward $r_{i}^{t}$ and next state $s^{t+1}$
	6. $\small Q_{i}(s^{t}, a^{t}_{i})\leftarrow Q_{i}(s^{t}, a^{t}_{i})+\alpha[r^{t}_{i}+\gamma\displaystyle\max_{a_{i}'}Q_{i}(s^{t+1}, a_{i}')-Q_{i}(s^{t}, a^{t}_{i})]$

# Limitation
The computation is not that efficient(?)
- [[marl-book.pdf#page=112&selection=50,0,52,38|The Complexity of Computing Equilibria]]

---
