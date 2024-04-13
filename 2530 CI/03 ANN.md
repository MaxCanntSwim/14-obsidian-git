- How the brain neuron inspired the first artificial neuron (the perceptron);
- How to train the perceptron;
- Limitations of the perceptron;
- The multilayer perceptron;
- Feedforward inference;
- Training the multilayer perceptron through backpropagation.
___
Artificial Neuron
![[Screenshot 2024-04-13 at 11.00.55.jpg]]

Perceptron
![[Screenshot 2024-04-13 at 11.02.08.jpg]]

The multilayer perceptron
![[Screenshot 2024-04-13 at 11.03.24.jpg]]

# Activation Functions
- In a multilayer perceptron, the activation funcion is referred to as $\sigma$ 
- The activation functions are necessary to introduce nonlinearities in the network
- Smooth (differentiable) activation functions are suited to perform gradient descent
- **Sigmoid** (logistic) and hyperbolic tangent (**tanh**) are common choices
![[Screenshot 2024-04-13 at 11.06.55.jpg]]

# Forward Propagation
![[Screenshot 2024-04-13 at 11.10.59.jpg]]
We want to minimize the loss function for all samples in the training set: $$𝓛=\frac{1}{N}\sum\limits^{N}_{i=1}(y-\hat{y})^{2}$$
The loss function is dependent on correct outputs (y) and predicted outputs ($\hat{y}$) which in turn depend on the inputs (x) and weights (w and b)

the only elements we can control are the weights. thus we search of the set of weights that minimizes 𝓛 for all training samples. 

Finding the global minimum analytically is computationally unfeasible. Instead, we update the weights step by step until we find a set of weights that minimizes 𝓛 using gradient decent update: ![[Screenshot 2024-04-13 at 11.19.22.jpg]]
## Gradient descent update
![[Screenshot 2024-04-13 at 11.19.49.jpg]]

