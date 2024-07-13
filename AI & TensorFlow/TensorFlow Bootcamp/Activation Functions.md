[Activation Function Cheat Sheet]([Activation Functions — ML Glossary documentation (ml-cheatsheet.readthedocs.io)](https://ml-cheatsheet.readthedocs.io/en/latest/activation_functions.html))

# ReLU (Rectified Linear Units)
```python
def RelU(X):
	return max(X, 0)
```
![[Pasted image 20240524161026.png|400]]

## Leaky ReLU
```python
def leakyReLU(X, a):
	return max(aX, X)
```
- `a` is hyperparameter: 0.01, 0.001, etc
- Prevents Dying ReLU
![[Pasted image 20240713144725.png]]

# Sigmoid
```python
def sigmoid(X)
	return 1/(1+exp(-X))
```
$$\text{Sigmoid}=\frac{1}{1+e^{-x}}$$
![[Pasted image 20240524161138.png|400]]

# Softmax
$$\text{Softmax}(x_{i})=\frac{e^{x_{i}}}{\sum^{n}_{j=1}e^{x_{j}} }$$
- Making outputs **sum to 1**
- Useful to scale model outputs into probabilities

# Tanh