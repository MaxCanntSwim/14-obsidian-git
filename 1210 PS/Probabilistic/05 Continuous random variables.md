f(x): pdf (probability density function)
Definition
A random variable X is continuous if $$P(a≤X≤b)=\int^{b}_{a}f(x)dx$$
for all values a ≤ b and a function f:ℝ→$[0,\infty)$
- f is the probability density function of X
- the distribution function of X is $F(x)=P(X≤x)=\int^{x}_{-\infty}f(x)dx$
- $f(x)=\frac{d}{dx}F(x)$

# Specific families
1. **Uniform random variable**
		example: bus leaves at 8:15, 8:30, 8:45, 9:00...
		you arrive at the bus station: how long do you need to wait for the next bus in minutes?
		→ outcomes for X in $[0, 15)$.![[IMG_3982.jpeg]]
		Definition 
		A continuous random variable X has a uniform distribution on the interval $[\alpha, \beta]$ if its probability density function f is given by: $$f(x)=
		\left[
\begin{array}{*{3}{rC}l}
    \frac{1}{\beta-\alpha} \,\,\,\,\,\,\,\,\,\,\,\,for\,\,x∈[\alpha,\beta] \\
    0\,\,\,\,\,\,for\,\,x\,\,not\,\,in\,\,[\alpha,\beta]
\end{array}
\right]$$
		Notation X ~ $U(\alpha,\beta)$
2. **The exponential distribution**
		A continuous random variable X has an **exponential distribution with parameter λ** if its probability density function f is given by: 
		The **exponential distribution** often arises in the context of **waiting times**, such as the time until a radioactive particle decays, the next earthquake occurs, or a new visitor arrives at a website.
		example: Natural decay, like carbon 
		Carbon 14 isotopes decay to Nitrogen 14 (this takes years)
		→ consider one such atom, let X be the time in years until decay
		→ from physics/experiments: $P(X ≥ a)=e^{-\lambda*a}$ with $\lambda =\frac{1}{8000}$
		$F_{x}(a)=P(x≤a)=1-e^{\lambda*a}$ 
		$f_{x}(a)=F_{x}'(a)=O-(-\lambda)*e^{-\lambda*a}=\lambda e^{-\lambda*a}$
		→  property: the exponential distribution is memoryless
		given that I need to wait at least **t** years, what is the probability that I need to wait at least **s** more years
		P(X ≥ s+t | X ≥ t)=$\frac{P(X≥s+t and X≥t)}{P(X≥t)}=\frac{e^{-\lambda(s+t)}}{e^{-\lambda*t}}=\frac{e^{-\lambda s-\lambda t}}{e^{-\lambda*t}}=e^{-\lambda s}$ 
		Notation: X ~ $Exp(\lambda)$ ![[Screenshot 2023-05-01 at 09.50.24.jpg]]
3. **The Pareto distribution**
		A continuous random variable X has a **Pareto distribution with parameter $\alpha >0$** if its probability density function f is given by:$$f(x)=
		\left[
\begin{array}{*{3}{rC}l}
    \frac{\alpha}{x^{\alpha+1}} \,\,\,\,\,\,\,\,\,\,\,\,for\,\,x≥1 \\
    0\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,for\,\,x  <1
\end{array}
\right]$$
		$P(X>x)=x^{-\alpha}\,\,\,\,(a>0)$
		ꜜ
		$P(X≤x)=1-x^{-\alpha}=F_{x}(x)$
		⇒ $f_{x}(x)=(1-x^-\alpha)'=0-(-\alpha)x^{-\alpha-1}=\frac{\alpha}{x^{\alpha+1}}$ 
		Notation: X ~ $Par(\alpha)$![[Screenshot 2023-05-01 at 10.03.22.jpg]]
4. **Normal distribution**
		A continuous random variable X has a **normal distribution with parameters $\mu$ and $\sigma^{2}$** if its probability density function is given by: $$f(x)=\frac{1}{\sigma\sqrt{2\pi}}e^{-\frac{1}{2}(\frac{x-\mu}{\sigma})^{2}}$$
		If $\mu=0$ and $\sigma^{2}=1$, then X ~ $N(0, 1)$ has a **STANDARD normal distribution**. 
		The normal distribution function can not be expressed in elementary functions
		Property: symmetric around $\mu$
		Notation: X ~ $N(\mu, \sigma^{2})$![[IMG_3986.jpeg]]![[Screenshot 2023-05-01 at 10.11.28.jpg]]![[Screenshot 2023-05-01 at 10.11.48.jpg]]
		The right tail probabilities are given for the standard normal distribution: $$P(Z \ge a)$$ ![[Screenshot 2023-05-01 at 10.21.13.jpg]]Table for $N(0,1)$: value "4052" in row 0.2 and column 4 means: ![[IMG_3987.jpeg]]
# Quantiles
## Definition
Let X be a continuous random variable 0 ≤p≤1. The pth quantile or the 100pth percentile of the distribution of X is the smallest number $q_{p}$ such that $$F_{x}(q_{p})=P(X≤q_{p})=p$$