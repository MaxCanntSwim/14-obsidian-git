given a random variable $X:\Omega \to ℝ$ and function $g:ℝ\toℝ$, we can define a new random variable $Y:\Omega \to ℝ$ by composition $$Y=g(X)$$
To find the distribution function $F_{Y}$ for $Y=g(X)$, we determine $$F_{Y}=P(Y≤x)=P(g(X)≤x)$$
# Example
Suppose $X~U(-1,2)$ and $g(x)=x^{2}$. Define $Y=g(x)$.
Then $Y ≤ x$ if $X ∈ [-\sqrt{x},\sqrt{x}]$, so $$F_{Y}(x)=P(Y≤x)=P(X^{2}≤x)=P(-\sqrt{x}≤X≤\sqrt{x})$$
				![[Screenshot 2023-05-16 at 13.54.45.jpg]]

# Theorem
Let X be a RV, and g:ℝ→ℝ a function. 
If X is discrete, then $$E[g(x)]=\sum\limits_{i}g(a_{i})P(X=a_{i})$$
If X is continuous with pdf f, then $$E[g(X)]=\int\limits_{-\infty}^{+\infty}g(x)f(x)dx$$

