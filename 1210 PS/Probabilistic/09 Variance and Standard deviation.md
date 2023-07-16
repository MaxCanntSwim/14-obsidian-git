# Definition
The variance of a random variable X is defined as $$Var(X)=E[(X-E[X])^{2}]$$ The standard deviation of a random variable is defined as $$SD(X)=\sqrt{Var(X)}$$For any random variable X the variance can be computed by $$Var(X)=E[X^{2}]-(E[X])^{2}$$
# Expectation and variance of Standard Distributions

| Distribution        | Expectation                 | Variance                         |
| ------------------- | --------------------------- | -------------------------------- |
| Bin(n,p)            | $np$                        | $np(1-p)$                        |
| Geo(p)              | $\frac{1}{p}$               | $\frac{1-p}{p^{2}}$              |
| U($\alpha,\beta$)   | $\frac{1}{2}(\alpha+\beta)$ | $\frac{1}{12}(\beta-\alpha)^{2}$ |
| N($\mu,\sigma^{2}$) | $\mu$                       | $\sigma^{2}$                     |
| Exp($\lambda$)      | $\frac{1}{\lambda}$         | $\frac{1}{\lambda^{2}}$          | 

# Change-of-units formula
## Theorem
For any random variable X and any real values r and s it holds that $$E[rX+s]=rE[X]+s$$$$Var(rX+s)=r^{2}Var(X)$$
