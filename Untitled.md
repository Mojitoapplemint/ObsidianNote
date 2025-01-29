Let $G=(Q,E,f,q_{0})$ be deterministic finite automata
- $Q$ : Set of state
- $q_{0}\in Q$ : Initial State
- $E$ : The event set
- $f:Q\times E\to Q$ : Transition Function

$L(G)=\{ s\in E^{*}\text{ | }f(q_{0}, s)\text{ is defined} \}$
- Sequence of feasible event
	- Language of $G$?

$\forall \text{ }k\in\mathbb{Z}_{r}=\{ 1,2,\dots r \}$, a partition, $E=E_{c,k}\cup E_{uc, k}$

An event is enabled if it is enabled by all supervisors

$\{ v_{k}:\forall \text{ }k\in\mathbb{Z}_{r},\quad p_{k}(L(G))\to E_{cp, k} \}$
