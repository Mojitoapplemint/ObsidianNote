[How to create a new custom layer: Making new layers and models via subclassing](https://www.tensorflow.org/guide/keras/making_new_layers_and_models_via_subclassing)

# Residual Neural Network
![[Pasted image 20240713141138.png|300]]
The classical residual network architecture *adds the input of the stack of layers to its output before passing the result to the next stack*
- Skip connections, shortcut to jump over some layers
- To avoid [[Gradients#Gradient Vanish|Gradient Vanish]]

## Doubly Residual Connection
$$x_{\ell}=x_{\ell-1}-\hat{x}_{\ell-1}$$
$$ \hat{y}=\sum_{\ell}\hat{y}_{\ell}$$
