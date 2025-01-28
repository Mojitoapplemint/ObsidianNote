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
$$\mathcal{T}_{i}(s^{t+1}\text{ | }s^{t}, a^{6})\propto \sum_{a_{-i}\in A_{-i}}\mathcal{T}(s^{t+1}\text{ | }s^{t}\langle a^{t}_{i}, a_{-i} \rangle)\prod_{j\neq i}\pi_{j}(a_{j}\text{ | }s^{t})$$

## Independent Q Learning
// Algorithm controls agent $i$
1. Initialize : $Q_{i}(s, a_{i})=0$ for all $s\in S, a_{i}\in A_{i}$
2. Repeat for every episode : 
3. **For** $t=0,1,2\dots$ **do** 
	1. Observe current state $s'$
	2. With probability $\epsilon$ : choose random joint action $a^{t}_{i}\in A_{i}$
	3. Otherwise : Choose joing action $a^{t}_{i}=\arg\max_{a_{i}}Q_{i}(s^{t}, a_{i})$
	4. (Meanwhile, other agents choose their action $a_{j}^{t}$)
	5. Observe own reward $r^{t}$ and next state $s^{t+1}$
	6. $Q_{i}(s^{t}, a^{t}_{i})\leftarrow Q_{i}(s^{t}, a^{t}_{i})+\alpha[r^{t}_{i}+\gamma\displaystyle\max_{a_{i}'}Q_{i}(s^{t+1}, a_{i}')-Q(s^{t}, a^{t}_{i})]$



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

# Limitation
The computation is not that efficient(?)
- [[marl-book.pdf#page=112&selection=50,0,52,38|The Complexity of Computing Equilibria]]



