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
At each time $t$, each agent $i\in I$ receives an observation $o^{t}_{i}\in O_{i}$