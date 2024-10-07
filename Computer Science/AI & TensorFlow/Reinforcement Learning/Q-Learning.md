Q-Learning is a type of RL
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
- One row for each possible state
- One column for each possible action
