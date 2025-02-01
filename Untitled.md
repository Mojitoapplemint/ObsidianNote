
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

---
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


A one-page statement of preparation of your academic preparation, qualifications, and related experience for this project:

- courses
- research experience/employment
- other employment
- extra/co-curricular activities
- other

How this project fits with longer term plans, if appropriate:

- honours
- graduate studies
- employment

Formatting requirements: minimum 3/4 inch margins all around, minimum 11pt font, Calibri or Times New Roman (or equivalent) preferred.



- 1 year of independent study
	- In detail
	- Process(내가 주체적으로 문제를 해결했음을 강조)
	- Started from prototype, detect problem, came up with improved model that solve the problem, repeat
	- Result of the research
- I kinda like researching
	- Before I started independent study, I didn't have a clear future vision, just planning to find a job from math and comp sci field.
	- However, throughout the independent study, every moment that I got stuck but finally made a progress, I got thrilled that I learned something new and I did it by myself.
		- Tell them I aware of challenges and stress of researching
		- However, after I finally solved the problem, or at least made a progress, the fact that I learned something new made myself proud and motivate to learn more, iterally until I fully understand every single possible aspect of it.
	- I start having a strong intuition that I am suitable for researcher. This 1 year of independent study enlightened me the joy of studying and learning
	- I decided to get Master's degree and even PHD
- Since I am studying both computer science and math, finding a field that contains both theoretical computer science and mathematics and still interests me was tough.
	- When I took online Deep Learning Bootcamp, the fact that I could not understand the reason why DL is work made me unsatisfied
	- RL is literally the field that I was looking for


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
