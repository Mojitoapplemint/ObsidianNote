Horizon
- Number of time steps during which the agents will interact with their environment

# Finite State Controller
## Policy Representation
A tree-based representation of a policy requires the agent to perfectly remember the entire history in order to determine its next action, which in the case of an infinite horizon problem would imply that an agent needs an infinite amount of memory. Clearly, this is not possible

Thus, consider sets of interval states $\mathbb{I}_{i}$, which represent and agent $i$'s finite memory
- Policy is represented as a finite-state controller

In FSCs, there is designated initial node and following the action selection at that node, the controller transitions to the next node depending on the observation seen.
- Nodes represent $i$'s interval states $\mathbb{I}_{i}$ and prescribe actions based on this finite memory

For Dec-POMDP, there is one FSC for each agent, thus set of controller provides the joint policy

## Moore and Mealy FSC

