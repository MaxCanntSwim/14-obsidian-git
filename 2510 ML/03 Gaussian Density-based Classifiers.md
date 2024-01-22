- Classification using Gaussian densities
- Quadratic classifier
- Linear classifier
- Nearest mean classifier
___
# Classification using Gaussian densities
## Estimate class Priors
Given a training set, how can you estimate $\hat{p}(y)$.
The classes are discrete, $\hat{p}(y)$ is a true probability. 
Often they are known/assumed
Otherwise, just count $$\hat{y_{1}}=\frac{N_{1}}{N}$$
## Estimate unconditional probability
How to estimate the data distribution $\hat{p}(\vec{x})$
explicit computation: $$p(\vec{x})=p(\vec{x}|y_{1})p(y_{1})+p(\vec{x}|y_{2})p(y_{2})$$
However, if you just need to find the largest posterior, the unconditional probability is not needed. 
