- Classifiers based on probability estimates
- The curse of dimensionality
- Multivariate Gaussian distribution
- Scaling of features
___
# Classifiers based on probability estimates
In byes rule you see $p(\vec{x})$. How to get it?
It can be computed explicitly: $$p(\vec{x})=p(\vec{x}|y_{1})p(y_{1})+p(\vec{x}|y_{2})p(y_{2})$$
But if you just find the largest posterior:$$\frac{p(\vec{x}|y_{1})p(y_{1})}{p(\vec{x})}>\frac{p(\vec{x}|y_{2})p(y_{2})}{p(\vec{x})}$$
you don't actually need the $p(\vec{x})$ in the denominator, thus it can be written as $$p(\vec{x}|y_{1})p(y_{1})>p(\vec{x}|y_{2})p(y_{2})$$
## True and estimated probabilities
We only get a sample (training set), drawn from the true distribution.
Thus we will need to model the true distribution. 
We will consider
- Discriminative and generative models
- Parametric and nonparametric models
### Generative models
$$p(y|\vec{x})\propto p(y)p(\vec{x}|y)$$
When we know the prior and conditional densities, we know everything about the data for classification. 
Density has to be estimated. 
Given examples from different classes, 'standard' density estimation is sufficient. 
It is possible to 'generate' (sample) from the classes
### Discriminative Models
$$\hat{p}(y|\vec{x})$$
When we don't know the class conditional probabilities,  and the class priors, directly approximate posterior probability?
Hard problem: given measurements, e.g. person's height, how can we estimate $p(woman|height)$.
Strong assumptions are needed, or sloppy approximations are taken. 
### Parametric Modeling & Estimation
Density estimation
- Simple nonparametric approach
- Curse of dimensionality
- parametric models
# Curse of dimensionality
![[Screenshot 2024-01-21 at 15.25.51.jpg]]
For 1-dimensional data, ± 1000 objects are needed
For M-dimensional date, ± $1000^{M}$ objects are needed
## Description
At first it seems logical that the more information is known about an object the easier it would be to classify. 
However, since the densities are never known, we have to estimate. 
The number of parameters to estimate increases with the number of features. 
To estimate these well, you need more objects. 
# Multivariate Gaussians
M - Dimensional density:
$$p(\vec{x})=\frac{1}{\sqrt{(2\pi)^{M}\det{(\Sigma)}}}\exp(-\frac{1}{2}(\vec{x}-\mu)^{T}\Sigma^{-1}(\vec{x}-\mu))$$
Sometimes also denoted as:$$\mathcal{N}(\,\vec{x}\,|\,\mu,\,\Sigma)$$
![[Screenshot 2024-01-21 at 15.47.04.jpg]]
![[Screenshot 2024-01-21 at 15.47.43.jpg]]
![[Screenshot 2024-01-21 at 15.47.30.jpg]]
![[Screenshot 2024-01-21 at 15.47.51.jpg]]
## Maximum likelihood estimates
What are maximum likelihood estimators for the mean and the covariance matrix? 
$$\hat{\mu}=\frac{1}{n}\sum\limits^{n}_{i=1}\vec{x}_{i}$$
$$\hat{\Sigma}=\frac{1}{n}\sum\limits^{n}_{i=1}(\vec{x}_{i}-\hat{\mu})(\vec{x}_{i}-\hat{\mu})^{T}$$
