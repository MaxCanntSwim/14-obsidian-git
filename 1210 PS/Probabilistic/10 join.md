# Definition
Let X and Y be two discrete RVs. 
The **joint probability mass function** p of X and Y is the function defined by $p:ℝ^{2}→[0,1]$ $$p(a,b)=P(X=a,Y=b)~~for~~all~~a~~and~~b$$

Let X and Y be two discrete RVs. 
The **join density function** f of X and Y is the function $f:ℝ^{2}→ℝ$ such that $$P(a_{1}≤X≤b_{1},a_{2}≤Y≤b_{2})=\int\limits^{b_{2}}_{a_{2}}\int\limits^{b_{1}}_{a_{1}}f(x,y)~dx~dy$$

# Example
**Finding a coin in a rectangular pond**
Suppose you have lost a coin in a 2 by 4 rectangular pond. You have no reason to suspect it in any particular location
	Let X be the x-coordinate of the coin → X~U(0,4)
	Let Y be the y-coordinate of the coin → Y~U(0,2)
What is the probability that the coin is at (2,1)? 
	P(X=2,Y=1)=0

What is the probability that the coin is in the region where $0≤x≤2$ and $0,5≤y≤1$?
$$P(0≤X≤2)=\int\limits^{2}_{0} \frac{1}{4} dx= \frac{1}{2}$$
$$P(0,5≤Y≤1)=\int\limits^{1}_{0,5} \frac{1}{2}dx= \frac{1}{4}$$$$P(0≤X≤2,0,5≤Y≤1)= \frac{1}{2}$$

**Finding a coin in a circular pond**
Suppose you lost a coin in a circular pond of radius 2. 
You have no reason to suspect it in any particular location. 
$$P(a≤X≤b,c≤ Y ≤ d)= \int\limits^{d}_{c} \int\limits^{b}_{a} f(x,y)~dx~dy$$$$f(x,y) = \left[
\begin{array}{*{3}{rC}l}
    \frac{1}{4\pi} &  &   &  &  if\sqrt{x^{2}+y^{2}}≤2 \\
    0 &  &   &  &  otherwise 
\end{array}
\right]$$
Let f be the joint density function of X and Y. Then the marginal densities of X and Y can be found as $$f_{X}=(x)= \int\limits^{\infty}_{-\infty}f(x,y)dy~~~~and~~~~f_{Y}=(y)= \int\limits^{\infty}_{-\infty}f(x,y)dx$$![[Screenshot 2023-05-22 at 15.26.55.jpg]]

$$f_{X}(x)= \int^{\infty}_{-\infty}f(x,y)dy = \int^{\sqrt{4-x^{2}}}_{-\sqrt{4-x^{2}}} \frac{1}{4\pi}dy= \frac{\sqrt{4-x^{2}}}{2\pi}$$for $-2≤x≤2$
$$f_{Y}(y)= \int^{\infty}_{-\infty}f(x,y)dx = \int^{\sqrt{4-y^{2}}}_{-\sqrt{4-y^{2}}} \frac{1}{4\pi}dx= \frac{\sqrt{4-y^{2}}}{2\pi}$$

# Connection between distribution and density function
Let f be the joint density function of continuous variables X and Y. Then the joint distribution function of X and Y can be found as $$F(a,b)=\int^{b}_{-\infty}\int^{a}_{-\infty}f(x,y)~dx~dy$$
