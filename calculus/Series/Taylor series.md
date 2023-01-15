This is very closely linked to [[Power Series]]. 
# Definition
Let *f* be *a* function for which all derivatives exist in some point a. 
The Taylor series of *f* at *a* is given by:$$\sum\limits_{n=0}^{\infty}\frac{f^{(n)}(a)}{n!} (x-a)^n$$ Here $f^{(n)}(a)$ is the n-th derivative of $f$ at $a$.
For a=0 the series is also called the Maclaurin series of $f$.
# Theorem
if $f$ is equal to a powerseries near a, then$$\sum\limits_{n=0}^{\infty}\frac{f^{(n)}(a)}{n!} (x-a)^n$$ on an open interval containing a. 
If this holds, the function is called **analytic** at $a$.
# Analytic function
Let f(x) be a function for which **derivatives** of an **arbitrary** order **exist** in x=a and let $$T_k(x)=\sum\limits_{n=0}^{\infty}\frac{f^{(n)}(a)}{n!} (x-a)^n$$Then the funcion is **analytic** at *a* when the remainders $R_n(x)=f(x)-T_n(x)$ satisfy $\lim\limits_{n\to\infty}R_n(x)=0$ for all *x* near *a*
# Applications
**Applications** of power series **representations** (Taylor series) include:
-   ﻿﻿writing **function** **values** as **series**
-   ﻿﻿computing **high order** derivatives of **functions**
-   computing certain **limits**  
*   computing certain **integrals** (as series)
# Polynomials 
## Theorem
Suppose *f* is a fuction that is *k* times differentiable at the point x=a then: $$f(x)=T_k(x)+h_k(x)(x-a)^k$$ Where $h_k$ is a function with$$\lim\limits_{n\to a}h_{k}(x)=0$$
## Lagrange remainder
Suppose f is a function that is k + 1 times differentiable on an interval containing a and x then$$f(x)=T_k(x)+\frac{f^{k+1}(c)}{(k+1)!}(x-a)^{k+1}$$for some c between x and a.
# Taylor's inequality
If $|f^{k+1}(x)|≤M$ for |x - a| ≤ d then$$|f(x)-T_{k}(x)|≤\frac{m}{(k+1)!}|x-a |^{k+1}$$for $|x-a|≤d$ 