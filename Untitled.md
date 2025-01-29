
A one-page proposal should include:
- the research question, objectives, rationale for the project
- relevant theory, methodology or creative approach to be used
- anticipated results (if appropriate) and implications of the research
    
You are encouraged to use in-text citations, if appropriate. An optional page to include bibliographic details or to list "works cited" is permitted. Note, only references should appear on this page - no additional proposal details.

Formatting requirements: minimum 3/4 inch margins all around, minimum 11pt font, Calibri or Times New Roman (or equivalent) preferred.

Tips for a good proposal

Must be a true research or creative practice experience.
- Not solely literature review/technical role.
- You are responsible for addressing a research question.
    
Research proposals must be sound and do-able.
- Ensure rationale is clear/identify the gap in knowledge
- Avoid casual and conditional language (e.g. my name is..., hope to...)
- Use active voice, first person
- Be realistic
- Be sure to state what the outcome/product will be


- Generative AI based on Deep Learning and Machine Learning has become so powerful
	- One of the events that initiated the AI revolution / that made everyone recognize the power of AI was Alphago
- Alphago was built based on fundamentally different learning algorithms with GPT that is interestingly not as popular as Deep Learning and Machine Learning
	- Artificial Intelligence can be divided into three categories: Deep Learning, Machine Learning, and Reinforcement Learning
- Concept of Reinforcement Learning
	- The beauty of RL is that its performance and logic can be mathematically proved or explained, unlike DL where these typically happen behind the scene
	- Another advantage of RL against ML and DL is that it does not require any input data
- Consider a more generalized form of Reinforcement Learning
	- What if there are multiple agents?
	- What if they do not have access to the entire system, but only part of it?
		- I.e. They can observe and control only part of the system.
	- Why is such a concept valuable? 
		- Single computer managing the entire system is not efficient as it might require the controller's extreme performance
- Concept Dec-POMDP
	- Requires both strong Mathematical and Computer Science background
	- Consist Mathematical concepts from Control Theory, Game Theory
	- This research proposes to solve(find an optimal solution) via Reinforcement Learning
- Proposes open, unsolved communication problem
	- That has a Dec-POMDP structure
	- This research will again prove the power of AI as undergraduate students find optimal solutions to the problem that would be attempted by doctoral or even post-doctoral students to solve 20 years ago  




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

$\Big\{ v_{k}\Big(p_{k}(s), \{ \forall \text{ }j\in\mathbb{Z}_{+}\text{\\}\{ k \}, \quad p_{j,k}(s) \}\Big) \longmapsto E_{cp, k}\Big\}$
