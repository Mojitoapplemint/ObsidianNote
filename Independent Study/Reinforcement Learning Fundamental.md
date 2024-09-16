
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

## Exploration and Exploitation Trade-off
