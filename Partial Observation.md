# Partially Observable Stochastic Game (POSG)
A partially observable stochastic game (POSG) is defined by the same elements of a stochastic game ,
- Finite set of agents $I=\{ 1,2\dots n \}$
- Finite set of states $S$, with subset of terminal states $\bar{S} \subset S$
- For each agent $i\in I$
	- Finite set of actions $A_{i}$
	- Reward function $\mathcal{R}_{i}:S\times A\times S\to \mathbb{R}$, where $A=A_{1}\times\dots \times A_{n}$
- State transition probability function $\mathcal{T}:S\times A\times S\to[0,1]$ such that 
$$\forall \text{ }s\in S, a\in A:\sum_{s'\in S}\mathcal{T}(s,a,s')=1$$
- Initial state distribution $\mu:S\to[0,1]$ such that
$$\sum_{s\in S}\mu(s)=1\quad \text{and}\quad \forall \text{ }s\in \bar{S}:\mu(s)=0$$

and additionally defines for each agent $i\in I$ :
- Finite set of observation $O_{i}$
- Observation function $\mathcal{O}_{i}:A\times S\times O_{i}\to [0,1]$ such that
$$\forall \text{ }a\in A, s\in S:\sum_{o_{i}\in O_{i}}\mathcal{O}_{i}(a,s,o_{i})=1$$

**Note)** POSG is more generalized concept of Dec-POMDP. Dec-POMDP is simply POSG where all agents share the reward function

# Observation Function
At each time $t$, each agent $i\in I$ receives an observation $o^{t}_{i}\in O_{i}$ with probability given by its observation function, $\mathcal{O}_{i}(a^{t-1}, s^{t},o^{t}_{i})$
- Observation is also written as $\mathcal{O}_{i}(o^{t}_{i}\text{ | }a^{t-1}, s^{t})$ to emphasize that the probability is conditioned on the state $s^{t}$ and joint action $a^{t-1}$

The observation functions in POSG can be used to represent diverse observability conditions of interest
- There is no such "the obesrvation function," it varies depends on the problem 

Ex)
1. Stochastic game : $o^{t}_{i}=(s^{t}, a^{t-1})$
	- Fully observation
2. Unobserved actions of other agents
	- Agents may observe the state and their own previous action, but not the previous of other agents
	- $o^{t}_{i}=(s^{t}, a^{t-1}_{i})$
3. **Limited View Region**
	- Agents may observe a subset of the state and joint action (i.e. agents have limited view of their surrounding environment)
	- $o^{t}_{i}=(\bar{s}^{t}, \bar{a}^{t})$ where $\bar{s}^{t}\subset s^{t}$ and $\bar{a}^{t}\subset a^{t}$

As a result, "Partial Observation" in Dec-POMDP is not static but diverse depends on the problem. The Cat and Mouse Problem can be interpreted as a Limited View Region example introduced above.