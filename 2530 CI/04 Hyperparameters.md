Topics:
- Activation functions and loss functions
- Number of layers and number of neurons
- Regularization
- Learning rate
- Batch size
___
# Activation Functions
the activation function for the output layer's neurons depends on task and number of classes (K)
- Binary classification (K=1)$$\hat{y}=sigmoid(z)=\frac{1}{1+e^{-z}}$$
- Multiclass classification (K > 1)
	- With non mutually exclusive labels (multilabel):$$\hat{y_{i}}=sigmoid(z_{i})=\frac{1}{1+e^{-z_{i}}}$$
	- With mutually exclusive labels$$\hat{y_{i}}= softmax(z_{i})=\frac{e^{z_{i}}}{\sum^{K}_{j=1} e^{-z_{j}}}$$
- Regression (for any K)$$\hat{y_{i}}=z_{i}$$
## Hidden layers
the activation function for the hidden layers' neurons is necessary to introduce non-linearities in the network. Multiple options are available:
- Sigmoid
	- Pro: interpretable output (it's probability)
- Hyperbolic tangent (tanh)
	- Pro: allows for positive and negative output
con: vanish gradients(small and large values of z cause the gradients to be close to 0)

- Rectified Linear Unit (ReLU) $\to h=max(0,z)$
	- Pro: no vanishing gradients
	- Con: $\Delta=0$ for negative values of z
- Leaky Rectified Linear Unit (LReLU)
	- Pro: nonlinear but piecewise linear, thus easy to differentiate. always $\Delta≠0$

# Learning rate
The learning rate $\alpha$ controls the speed in which the weights are updated: $$w^{t+1}=w^{t}-\alpha \frac{𝜕𝓛(w)}{𝜕w}|_{w=w^t}$$
![[Screenshot 2024-04-13 at 14.52.56.jpg]]
## Mini-Batch gradient decent 
![[Screenshot 2024-04-13 at 14.58.12.jpg]]
Mini-batch gradient decent:
Some training examples at a time (common batch sizes: 4, 8 ,16, 32)
- fast computation
- low variance
