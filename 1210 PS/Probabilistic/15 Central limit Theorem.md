# Definition
$X_{1},...,X_{n}$ are i.i.d. RV's
With $E[X_{i}]=\mu$ and $Var(X_{i})=\sigma^{2}$
		$E[\bar{X_{n}}]=\mu$ and $Var(\bar{X_{n}})= \frac{\sigma^{2}}{n}$
___
**Central limit theorem (CLT)**
$\bar{X_{n}}$ has (approximately) a normal distribution
notation: $\bar{X_{n}} \approx N(\mu, \frac{\sigma^{2}}{n})$
Corollary: $$\frac{\bar{X}_{n}-\mu}{\frac{\sigma}{\sqrt{n}}} \approx N(0,1)$$
In other words: for large n, the variable $Z_{n}$ approximately has a normal distribution $$Z_{n}\approx N(0,1)$$
Since $\bar{X_{n}}= \frac{\sigma}{\sqrt{n}}Z_{n}+\mu$
$$\bar{X}_{n}\approx N(\mu,\sigma^{2}/n)$$
And since $\sum^{n}_{i=1}X_{i}=n\bar{X}_{n}$ 
$$\sum\limits_{i=1}^{n}X_{i}\approx N(n\mu,n\sigma^{2})$$


# Example
An industrial robot works non-stop and contains a very fragile component. Its active lifetime X, measured in days, is distributed as Exp(1). Upon failure, the component is automatically replaced by a new one.

Suppose there are 100 components available, including the one that is currently used. What is the probability that the robot will run out of components in the next 90 days?

We need to know $P(\sum\limits^{100}_{i=1}X_{i}<90)$
But we do not know the density function of $\sum\limits^{100}_{i=1}X_{i}$
___
Since $E[X_{i}]=1$ and $Var(X_{i})=1$, by the CLT we know that $\sum_{i=1}^{100}X_{i}\approx N(100*1,100*1)$
$$P(\sum\limits_{i=1}^{100}X_{i}<90)\approx P(S<90)=P( \frac{s-100}{10}< \frac{90-100}{10})=P(Z<-1)$$
Where S ~ N(100, 100) and Z ~ (0, 1)