[Activation Function Cheat Sheet]([Activation Functions — ML Glossary documentation (ml-cheatsheet.readthedocs.io)](https://ml-cheatsheet.readthedocs.io/en/latest/activation_functions.html))

# ReLU (Rectified Linear Units)
```python
def Relu(X):
	return max(X, 0)
```
![[Pasted image 20240524161026.png|400]]


# Sigmoid
```python
def sigmoid(X)
	return 1/(1+exp(-X))
```
$$\text{(Sigmoid)}=\frac{1}{1+e^{-x}}$$
![[Pasted image 20240524161138.png|400]]
