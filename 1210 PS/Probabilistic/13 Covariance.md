# Definition
Let X and Y be two RV's. The covariance between X and Y is $$Cov(X,Y)=E[(X-E[X])(Y-E[Y])]$$If $Cov(X,Y) > 0$, then X and Y are **positively** correlated. 
If $Cov(X,Y) < 0$, then X and Y are **negatively** correlated. 
If $Cov(X,Y) = 0$, then X and Y are **uncorrelated**. 
___
A useful way to compute the covariance is $$Cov(X,Y)=E[XY]-E[X]E[Y]$$

If two RV's X and Y are independent, then they are also uncorrelated. However, uncorrelated RV's may be dependent

# Theorem
Let X and y be two RV's, then $$Var(X+Y)=Var(X)+Var(Y)-2Cov(X,Y)$$
if X and Y are uncorrelated then $Cov(X,Y)$ $$Var(X+Y)=Var(X)+Var(Y)$$

# Correlation
Let X and Y be two RV's. The correlation coefficient is $$\rho(X,Y)= \frac{Cov(X,Y)}{\sqrt{Var(X)}\sqrt{Var(Y)}}$$If $Var(X)>0$ and $Var(Y)>0$. Otherwise, $\rho(X,Y)=0$
