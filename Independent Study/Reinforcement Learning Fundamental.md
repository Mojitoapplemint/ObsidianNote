
# Definition
Learning what to do -how to map situations to actions- so as *to maximize the numerical reward signal*
- **Trial-and-Error Search:** The learner is not told which actions to take, but discover which actions yield the most reward by trying them
- **Delayed Rewards:** Actions may affect not onlt the immediate rewards but also next situation and, through that, all subsequent rewards

## Markov Decision Process
Learning agent must 
1) Be able to *sense the state of its environment* to some extent
2) Be able to *take actions* that affect the state
3) *Have a goal* or goals relating to the state of environment

Will discuss deeply in Chapter 3

## Neither supervised nor unsupervised
In interactive problems, it is often impracical to obtain examples of desired behaviour that are both correvt and representative of all the situations in which the agent has to act
- Supervised Learning is not suitable

Since Reinforcement Learning is trying to maximize a reward signal instead of trying to find hidden structure, it is not unsupervised as well.

# Elements
## Policy
Agent's way of behaving at a given time
- Mapping from perceived states of the environment to actions to be taken when in those states
- Alone is sufficient to determine behaviour
	- Specifying probabilities for each action, etc)

## Reward Signal
Defines the goal of the problem
- Environment sendsa single number, reward, to the reinforcement learning agent
- Define good or bad
- Agent's objective is to maximize the total reward

## Value Function
What is good in the long run
- 

## Model (Optional)
