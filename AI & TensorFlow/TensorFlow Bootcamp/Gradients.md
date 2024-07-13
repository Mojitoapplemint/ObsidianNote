A vector in the direction of the steepest increase of the function at certain points, where function referred to **loss function** in DL
- The gradients of the loss function with respect to the paramters of the NN *indicate the direction in which the parameters should be adjust to reduce the loss*

# Gradient Descent
![[Pasted image 20240713142635.png|400]]
The optimization algorithm commonly used to update the parameters of the network based on the gradients of the loss function
- Iteratively mode the parameters **in the direction opposite to the gradient** to minimize the loss

# Backpropagation
[Additional Resource](https://evan-moon.github.io/2018/07/19/deep-learning-backpropagation/)
The algorithm to compute gradients *used by optimization algorithm*
- After compute the loss value between target and the actual outputs, propagate it backwards to **update parameters of each node**

# Gradient Vanish
The phenomenon that gradients are getting extremely small at *further layers from the output layer* during backpropagation

**Caused by the slope of the activation functions**

![[Pasted image 20240713144116.png|400]]
In [[Activation Functions#Sigmoid|sigmoid]] activation function, the steepest slope value of 0.25
- During the backpropagation, as the slope(derivative) is keep multiplied, the value of gradients is getting smaller and smaller and eventually vanishes

To resolve this problem, [[Activation Functions#ReLU (Rectified Linear Units)|ReLU]] activation is often utlized since it returns slope value of 1 for positive input