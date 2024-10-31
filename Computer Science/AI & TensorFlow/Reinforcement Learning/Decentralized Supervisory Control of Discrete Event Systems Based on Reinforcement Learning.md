# Introduction
A Controller called a super visor assigns control patterns to the Discrete Event System(DES)
- DES: set of events permitted to occur at the current state of the DES

Because of inherent restrictions of the systems or controllers, many DESs are often controlled in a decentralized manner where local supervisors assign control patterns based on their local observations.

**Decentralized Control method based on RL**
Supervisors exist locally and control the DES jointly without direct negotiation between the supervisors. Each supervisor obtains a control pattern through learning without knowl edge of detailed specifications and precise costs in the de centralized DES.

# System Model
Decentralized Supervisory control architecture is composed of $n$ local supervisors and a DES
- Supervisor is denoted by $SV_{i} \text{ }(1\leq i\leq n)$ and has the corresponding learning unit denoted by $LU_{i}$

![[Pasted image 20241030231152.png|400]]
- $X$ is set of states of the DES
- $\sum$ is a set of events
	- $\sum^{c}\subseteq \sum$ is a set of controllable events
	- $\sum^{o}\subseteq \sum$ is a set of observable events
- And $\sum^{c/o}_{i}$ is a set of controllable/observable events of $SV_{i}$
	- $\sum^{uc/uo}_{i}$ is a set of uncontrollable/unobservable events of $SV_{i}$
- 

