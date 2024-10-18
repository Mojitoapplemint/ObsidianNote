8Q-Learning is a type of RL
- Involves and AI agent operating in an environment with states & rewards (inputs) and actions (outputs)
- Involves **model-free** environments
	- The AI agents is not seeking to learn about an underlying mathematical model probability distribution
	- Instead, the AI agent attemps to construct an optimal policy directly by interacting with the environment
- Trial and Error based approach
	- The agent repeatedly tries to solve the problem using varied approaches, and continuously updates its policy as it learns more and ore about it environment

# Characteristic
Fundamental RL characteristic also apply to QL

Additional Features
- The number of **possible states is finite**
	- The agent will always be in one of a fixed number of possible situations
- The number of **possible actions is finite**
	- The agent will always need to choose from among a fixed number of possible actions

# Q-Value
A Q-value indicates the quality of a particular action $a$ in a given states, s
$$Q(s,a)$$
- Current estimates of the sum of future rewards
	- How much additional rewards we can accumulate through all remaining steps in the current episode if the agent is in state $s$ and takes action $a$
- Increase as the ai agent gets closer and cloer to the highest reward

## Q-Table
Q-Values are stored in a Q-Table
- One row for each possible state and One column for each possible action
- Represents AI agent's policy for acting in the current environment
	- Higher the value, more likely for agent to choose
	- An optimal Q-table contains values that allow the AI agent to take the best action in any possible state
	- Providing the agent with the optimal path to the highest reward


# Temporal Differences(TD)
Method of calculating how much the Q-value for the action taken in the previous state should be changed based on what agent has learned about Q-values for the current state's action
- *Previous Q-values are updated after each step*

$$TD(s_{t}, a_{t})=r_{t}+\gamma\cdot \max_{a}(s_{t+1}, a)-Q(s_{t}, a_{t})$$
- $r_{t}$: Reward taken in the previous state
- $\gamma$: Discount factor ($0<\gamma\leq 1$)
- $\max_{a}(s_{t+1}, a)$: Largest Q-value available for current state

# Bellman Equation
Tells what new value to use as the Q-value for the action taken in the previous state
- Relies on a both the old Q-value for the action taken in the previous state and what has been learned after moving to the next state(TD)
- Includesa learning rate parameter $\alpha$ that defines how quickly Q-values are adjusted
$$Q^{new}(s_{t}, a_{t})=Q^{old}(s_{t},a_{t})+\alpha\cdot TD(s_{t},a_{t})$$

