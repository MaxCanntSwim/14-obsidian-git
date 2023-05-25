# Chebyshev's inequality
gives a upper bound for the probability. 
For each RV Y, for each a > 0: $$P(|Y-E[Y]|≥a)≤ \frac{1}{a^{2}}Var(Y)$$
## Example
**fair die throw**
	$E[Y]=3.5$
	$Var(Y)= \frac{35}{12}$
e.g. $a=2.4$:
	$P(| Y-3.5 |≥2.4)≤ \frac{1}{2.4^{2}}* \frac{35}{12}=0.506$

**Now choose $Y=\bar{X_n}$**
with $X_{1},...,X_{n}$ i.i.d. RVs with $E[X_{i}]=\mu$ 
											$Var(X_{i})\sigma^{2}$
→ $E[\bar{X_{n}}]=\mu~;~Var(\bar{X_{n}})= \frac{\sigma^{2}}{n}$
Cheb; $P(| \bar{X_{n}}-\mu | ≥a)≤ \frac{1}{a^{2}} *\frac{\sigma^{2}}{n}$
for fixed a, RHS → 0 as n → ∞

# Law of large numbers
For i.i.d. $X_{1},...,X_{n}$ and for each a (ε) > 0
	$P(| \bar{X_{n}}-\mu | ≥\epsilon)\to 0$ as n → ∞
	$P(| \bar{X_{n}}-\mu | ≤\epsilon)\to 1$ as n → ∞


## Example
**Throwing a thumbtack**
Whenn we throw a thumbtack, there is a brobability p that it remains pointing up, call this event A. how can we estimate p=P(A)
Throw it n times. For i = 1, ..., n define the random variables
$$X_{i}= \left[
\begin{array}{*{3}{rC}l}
    1, &  &  if~A~occurs& \\
    0, &  &  otherwise.  
\end{array}
\right]$$
Then $\bar{X_{n}}= \frac{{Number~of~times~A~occurs}}{n}=$ relative frequency
$E[X_{i}]=p$, so for any ε > 0
		$P(| \bar{X_{n}}-p |>\epsilon)\to 0$, as n → ∞
in other words: $\bar{X_{n}}\approx p$ for n large
![[Screenshot 2023-05-24 at 10.24.41.jpg]]