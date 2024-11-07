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

## Model of $SV_{i}$
Automaton Model $\left( S_{i}, \sum^{o}_{i}, g_{i}, x_{0} \right)$
- $S_{i}\subseteq 2^{X}$: set of states of $SV_{i}$
	- Candidates of the current state of the DES G
- $g_{i}$: $S_{i}\times \sum^{o*}_{i}\to S_{i}$ : State Trainsition function 

**Q)** For $g_{i}$ the output supposed to be the next state, but it returns the current state again


To determine the state of $SV_{i}$, a state estimate function $M^{s}_{i}:X\times \sum^{o*}_{i}\to 2^{X}$ is defined as 
$$M^{s}_{i}(t,u)=\left\{ x\in X\text{ | }\exists \text{ }v\in \sum*, M^{e}_{i}(v)=u, f(t, v)=x \right\}$$
- This gives a set of states of the DES which is reachable from state $t$ vis string observed as $u$

Then, $g_{i}$ is described as
$$g_{i}(s_{i}, \sigma)=\bigcup_{x\in S_{i}} M^{s}_{i}(x, \sigma)$$

Active Event Set for $SV_{i}$ at state $s_{i}$ defined as
$$F_{i}(s_{i})=\bigcup_{x\in S_{i}}M^{s}_{i}(x, \sigma)$$

DES receives a net control pattern $\pi$, which is the intersection of each supervisor's control pattern
$$\pi=\bigcap^{n}_{i=1}\pi_{i}$$
- $\pi_{i}\in \Pi_{i}(s_{i})$ is selected control pattern based on the current state $s_{i}$
- When $\pi$ occurs, DES changes to a new state and the control pattern is updated

## Bellman Optimal Equation
$P_{i}(s_{i}, \pi_{i}, s'_{i})$
- Probability of transition from $s_{i}$ to $s_{i}'$ when $SV_{i}$ selects $\pi_{i}$
$$P_{i}(s_{i}, \pi_{i}, s'_{i}) = \sum_{\sigma^{o}_{i}\in\left\{ \pi_{i}\cap \sum^{o}_{i} \right\}}P^{1}_{i}(s_{i}, \pi_{i}, \sigma^{o}_{i})\cdot P^{2}_{i}(s_{i}, \sigma^{o}_{i}, s'_{i})$$
- $P^{1}_{i}(s_{i}, \pi_{i}, \sigma^{o}_{i})$: Probability that $SV_{i}$ observes the occurence of an event $\sigma^{o}_{i}\in\left\{ \pi_{i}\cap \sum^{o}_{i} \right\}$, when $SV_{i}$ selects $\pi_{i}$ at $s_{i}$
- $P^{2}_{i}(s_{i}, \sigma^{o}_{i}, s'_{i})$: Probability that $SV_{i}$ makes a transition from $s_{i}$ to $s_{i}'$ by obeserved event $\sigma^{o}_{i}$


$Q(s_{i}, \pi_{i})$
- Discounted exprected total reward in the case that $SV_{i}$ selects $\pi_{i}$ at $s_{i}$


$R_{i}(s_{i}, \pi_{i}, s'_{i})$
- Expected reward via transition from $s_{i}$ to $s_{i}'$ by selecting $\pi_{i}$

$$R_{i}(s_{i}, \pi_{i}, s'_{i})=R^{1}_{i}(s_{i}, \pi_{i})+R^{2}_{i}(s_{i}, \sigma^{o}_{i}, s'_{i})$$
- $R^{1}_{i}(s_{i}, \pi_{i})$: Expected reward of $\pi_{i}$ at $s_{i}$
	- Intuitively, it represents for the cost to disable controllable events *which is not included in the control pattern*
	- **Q)** What the hell does this mean?
- $R^{2}_{i}(s_{i}, \sigma^{o}_{i}, s'_{i})$: Expected reward when $SV_{i}$ observes an event $\sigma^{o}_{i}\in \sum^{o}_{i}$, and make transition from $s_{i}$ to $s_{i}'$
	- **Q)** Why reward is assign for observation?

$T^{*}(s_{i}, \sigma^{o}_{i})$: Discounted expected total reward when $SV_{i}$ observes $\sigma^{o}_{i}$ at state $s_{i}$ and selects the control pattern which has the maximum $Q^{*}_{i}$ value at the new state
$$T^{*}(s_{i}, \sigma^{o}_{i})=\sum_{s'_{i}\in S_{i}}\left[P^{2}_{i}(s_{i}, \sigma^{o}_{i}, s'_{i})\cdot \left(R^{2}_{i}(s_{i}, \sigma^{o}_{i}, s'_{i})+\gamma\max_{\pi'_{i}\in\Pi_{i}(s_{i})}Q^{*}_{i}(s'_{i}, \pi'_{i})\right)\right]$$
---
# Equations
## Eq 1.
$$Q(x,a)\leftarrow Q(x,a)+\alpha[r+\gamma\max_{a'}Q(x',a')-Q(x,a)]$$
- Typical Q Value update equation
- $\alpha$: Learning Rate
- $\gamma$: DIscount factor

## Eq 2.
$$\sum^{\infty}_{k=1}a_{k}(x,a) =\infty$$
$$\sum^{\infty}_{k=1}a_{k}(x,a)^{2}< \infty $$
- $a_{k}(x,a)$ Learning Rate at state $x$ when $a$ is selected $k$ times
- The Q values converges with probability 1 to a true value as the number of updates of the Q values goes to the infinity if two conditions above satisfied


## Eq 3, 4.
$f$ is state trainsition funciton of DES
- Deterministic Transition Function: a function that defines the next state of a system based on the current state and input
$f:X\times \sum^{*}\to X$
- $f(x, \epsilon)=x$
- $\forall \text{ }t\in \sum^{*}, \forall \text{ }\sigma\in \sum$, $f(x, t\sigma)=f(f(x,t),\sigma)$

- $x$ is state, $f(x,\sigma)$ represents the new state after $\sigma$ happened during at state $x$
- $t$ is any finite string of $\sum$, thus *any finite sequence of event*
	- **Q)** what does $t\sigma$ mean?
- Intuitively, this mean that $f$ will give the same result state regardless we provide events as a entire string, or pass its fragments separately (but the order of events shouldn't be changed)

## Eq. 5
Active Event Set
$F_{G}(x)=\left\{ \sigma\in \sum:f(x,\sigma)\text{ is defined} \right\}$
- Set of event that result state is defined
	- *Set of Events that lead to the legal state*

## Eq. 6
$$M^{e}_{i}\Huge\{^{\sigma \text{ if } \sigma\in \sum^{o}_{i} }_{{\epsilon \text{ if } \sigma\in \sum^{uo}_{i} }}$$
- Projection returns any observable alphabet as it is
- Otherwise, it returns epsilon
	- Filter observable events only

## Eq. 7

Each supervisor oberves the occurrence of events in the DES through the corresponding projection
- $M^{e}_{i}:\sum\to \sum^{o*}_{i}\cup \{\epsilon\}$: Projection for $SV_{i}$
$$M^{e}_{i}(\epsilon)=\epsilon$$
$$\forall \text{ }t\in \sum*, \forall \text{ }\sigma\in \sum \text{ , }M^{e}_{i}(t\sigma)=\Huge\{^{M^{e}_{i}(t)\sigma \text{ (if }\sigma\in \sum^{o}_{i})}_{M^{e}_{i}(t) \text{ (if }\sigma\in \sum^{uo}_{i})}$$
- $\sum^{o*}_{i}$: Set of finite sequence of observable events of $SV_{i}$
- 


# Learning Algorithm

1. Initalize $T_i, R^1_i$ and $\eta_i$ of all $SV_i$
2. Initialize $Q$ values for all $SV_i$ by Eq.(24)
3. Repeat until any $s_i$ is a terminal state
    _**(For each episode):**_
4. Initialize a state $s_i \leftarrow x_0$ for all $SV_i$
5. Repeat for each $SV_i$
    _**(for each step of an episode):**_
6. Select a control pattern $\pi_i\in\Pi_i(s_i)$ based on $Q_i$ values by $SV_{i}$ (As a result, a net control pattern $\pi$ is assigned to the DES G)
7. Observe the occurence of event $\sigma^{o}_{i}\in \sum^{o}_{i}$
8. Acquire reward rewards $r^{1}_{i}$ and $r^{2}_{i}$
9. Make a transition $s_{i}\longrightarrow^{\sigma^{o}_{i}} s'_{i}(=g_{i}(s, \sigma^{o}_{i}))$ in $SV_{i}$
10. Update $T_{i}(s_{i}, \sigma^{o}_{i})$, $R^{1}_{i}(s_{i}, \pi_{i})$, and $\eta_{i}(s_{i}, \sigma^{o'}_{i})$ by Eq.(21), Eq.(22), and Eq.(23) respectively
11. Update the $Q_{i}$ values by Eq. 24
12. $s_{i}\leftarrow s'_{i}$

