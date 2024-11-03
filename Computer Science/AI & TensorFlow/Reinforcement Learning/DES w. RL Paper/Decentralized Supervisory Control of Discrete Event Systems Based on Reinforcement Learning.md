# Introduction
A Controller called a super visor assigns control patterns to the Discrete Event System(DES)
- DES: set of events permitted to occur at the current state of the DES

Because of inherent restrictions of the systems or controllers, many DESs are often controlled in a decentralized manner where local supervisors assign control patterns based on their local observations.

**Decentralized Control method based on RL**
Supervisors exist locally and control the DES jointly without direct negotiation between the supervisors. Each supervisor obtains a control pattern through learning without knowl edge of detailed specifications and precise costs in the de centralized DES.

# System Model
## Terminologies and Notations
Decentralized Supervisory control architecture is composed of $n$ local supervisors and a DES
- Supervisor is denoted by $SV_{i} \text{ }(1\leq i\leq n)$ and has the corresponding learning unit denoted by $LU_{i}$

![[Pasted image 20241030231152.png|400]]
$X$ is set of states of the DES

$\sum$ is a set of events
- $\sum^{c}\subseteq \sum$ is a set of controllable events
- $\sum^{o}\subseteq \sum$ is a set of observable events

And $\sum^{c/o}_{i}$ is a set of controllable/observable events of $SV_{i}$
- $\sum^{uc/uo}_{i}$ is a set of uncontrollable/unobservable events of $SV_{i}$

$\sum^{*}$: Zero or more repetition of elements in $\sum$
- Set of all finite strins over $\sum$, including $\epsilon$
- {"a", "b", "c"}* = { ε, "a", "b", "c", "aa", "ab", "ac", "ba", "bb", "bc", "ca", "cb", "cc", "aaa", "aab", ...}

$f$ is state trainsition funciton of DES
- Deterministic Transition Function: a function that defines the next state of a system based on the current state and input
$f:X\times \sum^{*}\to X$
- $f(x, \epsilon)=x$
- $\forall \text{ }t\in \sum^{*}, \forall \text{ }\sigma\in \sum$, $f(x, t\sigma)=f(f(x,t),\sigma)$

Active Event Set
$F_{G}(x)=\left\{ \sigma\in \sum:f(x,\sigma)\text{ is defined} \right\}$

Each supervisor oberves the occurrence of events in the DES through the corresponding projection
- $M^{e}_{i}:\sum\to \sum^{o*}_{i}\cup \{\epsilon\}$: Projection for $SV_{i}$
$$M^{e}_{i}(\epsilon)=\epsilon$$
$$\forall \text{ }t\in \sum*, \forall \text{ }\sigma\in \sum \text{ , }M^{e}_{i}(t\sigma)=\large\{^{M^{e}_{i}(t)\sigma \text{ (if }\sigma\in \sum^{o}_{i})}_{M^{e}_{i}(t) \text{ (if }\sigma\in \sum^{uo}_{i})}$$

**Q)** Why $t$ and $\sigma$ are multiplied?

## Model of $SV_{i}$
Automaton Model $\left( S_{i}, \sum^{o}_{i}, g_{i}, x_{0} \right)$
- $S_{i}$



1. Initalize $T_i, R^1_i$ and $\eta_i$ of all $SV_i$
2. Initialize $Q$ values for all $SV_i$ by EQ.(24)
3. Repeat until any $s_i$ is a terminal state
	(For each episode):  
    a. Initialize a state $s_i \leftarrow x_0$ for all $SV_i$
    b. Repeat for each $SV_i$ 
	(for each step of an episode):
		i. Select a control pattern $\pi_i\in\Pi_i(s_i)$ based on $Q_i$ values by $SV_{i}$ (As a result, a net control pattern $\pi$ is assigned to the DES G)
		ii. Observe the occurence of event $\sigma^{o}_{i}\in \sum^{o}_{i}$
		iii. Acquire reward rewards $r^{1}_{i}$ and $r^{2}_{i}$
		iv. Make a transition $s_{i}\longrightarrow^{\sigma^{o}_{i}} s'_{i}(=g_{i}(s, \sigma^{o}_{i}))$ in $SV_{i}$
		v. Update $T_{i}(s_{i}, \sigma^{o}_{i})$, $R^{1}_{i}(s_{i}, \pi_{i})$, and $\eta_{i}(s_{i}, \sigma^{o'}_{i})$ by Eq.(21), Eq.(22), and Eq.(23) respectively
		vi. Update the $Q_{i}$ values by Eq. 24
		vii. $s_{i}\leftarrow s'_{i}$
