Let $G=(Q,E,f,q_{0})$ be deterministic finite automata
- $Q$ : Set of state
- $q_{0}\in Q$ : Initial State
- $E$ : The event set
- $f:Q\times E\to Q$ : Transition Function

$L(G)=\{ s\in E^{*}\text{ | }f(q_{0}, s)\text{ is defined} \}$
- Sequence of feasible event
	- Language of $G$?

$\forall \text{ }k\in\mathbb{Z}_{r}=\{ 1,2,\dots r \}$, a partition, $E=E_{c,k}\cup E_{uc, k}$

$E_{cp, k}=\{ E_{e}\subseteq E\text{ | }E_{uc, k}\subseteq E_{e} \}$
- $\forall \text{ }k\in\mathbb{Z}_{r}$, a partition, $E=E_{o,k}\cup E_{uo,k}$
- $\forall \text{ }k\in\mathbb{Z}_{r},\quad p_{k}:E^{*}\to E^{*}_{o,k}$  is a projection function

An event is enabled if it is enabled by all supervisors
- $\{ v_{k}:\forall \text{ }k\in\mathbb{Z}_{r},\quad p_{k}(L(G))\to E_{cp, k} \}$

The set of supervisors based on partial observations
- $L_{r}, L_{a}\subseteq L(G)$, required and admissible language

$\forall \text{ }(i,j)\in\mathbb{Z}_{r}\times\mathbb{Z}_{r}, E_{o,i,j}\subseteq E_{o,i}$ and $p_{i,j}:E\to E_{o,i,j}$

$\{ v_{k}\Big(p_{k}(s), \{ \forall \text{ }j\in\mathbb{Z}_{+}\text{\\}\{ k \}, \quad p_{j,k}(s) \}\Big) \mapsto E_{cp, k}\}$