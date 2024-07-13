A vector in the direction of the steepest increase of the function at certain points, where function referred to **loss function** in DL
- The gradients of the loss function with respect to the paramters of the NN *indicate the direction in which the parameters should be adjust to reduce the loss*

# Gradient Descent
![[Pasted image 20240713142635.png|400]]
The optimization algorithm commonly used to update the parameters of the network based on the gradients of the loss function
- Iteratively mode the parameters **in the direction opposite to the gradient** to minimize the loss

# Backpropagation
[Additional Resource](https://evan-moon.github.io/2018/07/19/deep-learning-backpropagation/)
The algorithm to compute gradients
- After compute the loss value between target and the actual outputs, propagate it backwards to update parameters of each node