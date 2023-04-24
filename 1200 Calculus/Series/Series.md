Series can be used to solve [[Derivative]] functions. 

Let ($a_1,a_2,a_3,...$) be a [[Sequences]] of numbers.
The infinite sum$$a_1,a_2,a_3,...=\sum\limits_{n=0}^{\infty}{a_n}$$
is called a series. 
# Convergence and divergence
Define the **partial sums**: 
	$s_1=a_1$
	$s_2=a_1+a_2$
	$s_3=a_1+a_2+a_3$
	$$s_n=\sum\limits^{N}_{n=1}a_n$$
if $\lim\limits_{N \to \infty}s_N$ exists and equal to $L ∈ ℝ$, the series is **convergent**
and we write $$\sum\limits_{n=0}^{\infty}{a_n}=L$$
Otherwise the series is divergent. 

## Divergence test
If the series $\sum\limits_{n=1}^{\infty}{a_n}$ is convergent, then $\lim\limits_{n \to \infty}a_n=0$.
The contrapositive of this theorem is:
If $\lim\limits_{n \to \infty}a_n$ does not exist or $\lim\limits_{n \to \infty}a_n≠0$, then the series $\sum\limits_{n=1}^{\infty}{a_n}$ is divergent. 
**!!If the limit $\lim\limits_{n \to \infty}a_n$ =0 the series does not need to be convergent**, an example of this is The harmonic series $\sum\limits_{n=1}^{\infty}\frac{1}{n}$ is divergent!

## Intergral test
Suppose f(x) is a positive, continuous and decreasing function on the interval $[1,\infty)$ and let $a_n=f(n)$ then: 
* $\sum\limits_{n=1}^{\infty}{a_n}$ is convergent if $\int_{1}^{\infty} f(x) \,dx$ is divergent.
* $\sum\limits_{n=1}^{\infty}{a_n}$ is divergent if $\int_{1}^{\infty} f(x) \,dx$ is divergent.
# Geometric series
A series $\sum\limits_{n=0}^{\infty}{a_n}$ is called a **geometric series**
If there is a number r such that $\frac{a_n+1}{a_n}=r$ for all n.
This r is the **common ratio** of the series. 
given a geometric series with common ratio r, we have:
* If -1< r < 1, then the series is convergent. 
		the sum is (first term) $*\frac{1}{1-r}$.
* If r ≤ -1 or r ≥ 1, the series is divergent

# Rules of calculation
Suppose both $\sum\limits_{n=1}^{\infty}{a_n}$ and $\sum\limits_{n=1}^{\infty}{b_n}$ are convergent. Then: 
$$\sum\limits_{n=1}^{\infty}{a_n}+b_n=\sum\limits_{n=1}^{\infty}{a_n}+\sum\limits_{n=1}^{\infty}{b_n}$$
$$\sum\limits_{n=1}^{\infty} c\,\,a_n=c\sum\limits_{n=1}^{\infty}{a_n}$$
# P-Series
A series of the form $\sum\limits_{n=1}^{\infty}\frac{1}{n^p}$ is called a **p**-series.
A p-series is
* Convergent if p > 1
* Divergent if p ≤ 1