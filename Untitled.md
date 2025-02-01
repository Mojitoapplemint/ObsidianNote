
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


**

"AI is conquering the world." 

Considering that generative AI like ChatGPT has extremely influenced numerous fields and industries, no one would entirely oppose the statement above. Artificial Intelligence can be classified into three categories based on its learning algorithm: Machine Learning(ML), Deep Learning(DL), and Reinforcement Learning(RL). Despite ML and Generative AI based on DL becoming more popular than RL, the model that spread the power of AI worldwide and initiated the AI trend was based on RL, AlphaGo. AlphaGo is the RL model created by Google that plays Go, the ancient Chinese board game that some researchers had claimed that computers would never defeat top humans. Thus, AlphaGo scoring 4:1 against Lee Sedol, winner of 18 world titles, was enough to emphasize the power of AI. 

Reinforcement Learning trains the learner by assigning numerical rewards to their action and lets them discover which actions yield the most reward by trying as various actions as possible. The positive reward encourages the agent to choose the same action and the negative one discourages it. Then, the agent records how "good" the action was; repeating this trial-and-error process to maximize the long-run cumulative rewards will allow the agent to construct the recipe for how to behave at a certain moment.

This research aims to test the capability of RL for a further generalized situation: What if there is more than one decision-maker cooperating to find the optimal solution? What if each does not have full access to observe and control the system, but only part of it? The mathematical model where multiple agents cooperate to manage the system despite their partial observation and control is called the Decentralized Partially-Observable Markov Decision Process(Dec-POMDP). This generalization is worth considering since a single computer managing a large system would require extreme performance which is less cost-efficient. In particular, this research will focus on a specific open problem called "Decentralized control with communication between controllers," featured in  “Unsolved Problems in Mathematical Systems and Control Theory[a],” where n controllers can observe only part of the system, aiming to meet the specific control objective. They can exchange information, such as their partial observation, denoted communication. However, there must be some constraints on the communication channel, such as distance limitation or uncertainty of conveyed information. The problem asks how to synthesize controllers and communication protocol(which information must be communicated) for each directed pair of controllers, such that when all controllers use their received communication, the entire system meets the control objective.

The ultimate question of this research is to demonstrate whether RL can find the optimal solution for this problem, and if it can, how efficient the required training is. Some researchers have constructed some algorithms to solve Dec-POMDP[b]. Since the paradigm of those algorithms aligns with the Multi-agent RL(MARL), this research will eventually implement the algorithm and solve the proposed communication problem. 

Since the components and algorithms of MARL are defined heavily based on Control Theory and Game Theory, mathematics can explain the performance and logic of MARL, which makes MARL beautiful. For example, unlike DL whose solution definition relies on stochastic performance, the solution of MARL can be "proved" to be optimal as it converges to a specific equilibrium(e.g. Nash Equilibrium) defined by Game Theory.

  
  
  
  
  
  
  
  
  
  

Fortunately, Mount Allison University did not offer any course focusing on Reinforcement Learning and Decentralized Partially-Observable Markov Decision Processes. Nevertheless, I am confident that I am satisfying not only the required knowledge but mindset as a researcher because I will have 1 year of independent study experience about RL and Dec-POMDP before summer. This independent study has been motivated by the uncertainty of one paper introducing one RL algorithm that solves one Dec-POMDP problem by Japanese researchers Yamasaki and Ushio in 2005. The proposed algorithm contained ambiguities in logic and definitions that did not match the typical Dec-POMDP paradigm that has been researched. Thus, we conducted an independent study to reproduce their algorithm in Python and demonstrate its capability of solving Dec-POMDP.

I began the study by understanding the concept of RL and how it works. Once a week, I met with my supervisor, Dr. Laurie Ricker, to report implementation progress, discuss the results of the experiments and adjust the research direction. Other than that, I challenged myself to work independently with the least external help because I did not want to simply follow a certain curriculum but be self-reliant. Once I got a confirmation on how to approach the problem, I was responsible for experimenting, analyzing the result and detecting the possible errors. Then, based on the discussion with Dr. Ricker about the result and error, I came up with another experiment idea with the improved model. Throughout the semester, I built two AI models that play TicTacToe to understand the classic RL. Then, I created three models based on Yamasaki and Ushio's paper to demonstrate their algorithm, but none of them showed the same performance as the paper. Under Dr.Ricker's confirmation, I concluded that their algorithm was wrong. Then, I had to detect and logically explain the error of their work. As I repeatedly read and analyzed their paper, I could find that one of their assumptions did not align with the Dec-POMDP principles: they applied certain probability distribution on a certain algorithm that does not require it. As a consequence, I could complete my first research.

Since I understood RL fundamentals and why Yamasaki and Ushio's algorithms did not work, I started aiming to find a proper algorithm and solve the proposed Dec-POMDP problem in the winter semester. The ultimate objective of the second independent study is to perfect my insight toward Dec-POMDP by solving the proposed problem and then challenging other problems. I also expect to explore diverse RL paradigms on the same problem and compare their performance and cost efficiency to find the most suitable one for certain cases. This eventually motivated us to extend this project to solve the proposed open communication problem as summer research to test both RL performance capability and my research capability.

I appreciate this experience because it changed my future vision. Even though solving rigorous problems was truly challenging and stressful, I found myself persistently thinking of different approaches, enjoying the entire process, and eventually making steady progress. Hence, this study reminded me of the joy of learning and encouraged me to learn further rather than diving into job hunting. Dr. Ricker and I have a vision for my graduating year to extend the summer research even further into my thesis for a Joint Honour degree in Mathematics and Computer Science. It will still mainly focus on RL and Dec-POMDP but add another feature, history through iterative training; whether the RL algorithm allows multiple learners to find optimal solutions using their memory from past training as a reference despite its partial observation. 

My future vision does not stop at the Honour thesis but continues for a Master's degree. Since I have a passion for both Math and Computer Science, I have struggled to choose one field between them for my Master's. The Deep Learning Bootcamp that I took last summer did not satisfy me because I could not understand how the DL algorithm works. However, the independent study made me consider Reinforcement Learning a great candidate because I can mathematically understand the RL algorithm. I expect this summer research will be a meaningful project throughout my research life.

**