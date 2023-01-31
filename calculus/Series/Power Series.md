A [[Series]] of the form: 
$$\sum\limits^{\infty}_{n=0}c_n(x-a)^n=c_0+c_1(x-a)+c_2(x-a)^2+...$$
the **convergence** of this series might **depend** on **x**
# Convergence
There is an R ≥ 0, possibly ∞, such that:
* the series is (absolutely) concergent for |x-a| < R
* the series is divergent for |x-a| >R
![[Screenshot 2023-01-14 at 13.10.34.jpg]]
R is the radius of convergence
a is the center of convergence
## Definition 
For a power series $\sum\limits c_n(c-a)^n$ the interval of convergence is given by:
$(-\infty,\infty),\,\, (a-R,a+R),\,\, [a-R,a+R),\,\, (a-R,a-R]\,\,or\,\, [a-R,a+R]$  
Depending on the radius of convergence and the behaviour at boundary points. 
# Manipulation
Assume $f(x)= \sum\limits^{\infty}_{n=0}a_nx^n$ for |x| <$R_1$ and $g(x)= \sum\limits^{\infty}_{n=0}b_nx^n$ for |x| < $R_2$
$$c\,x^kf(x)= \sum\limits^{\infty}_{n=0}c\,a_nx^{n+k}\,\,\,\,\,\,\,\,\,\,|x|<R_1,k∈ℕ$$
$$f(c\,x^k)= \sum\limits^{\infty}_{n=0}a_n\,c^n\,x^{k\,n}\,\,\,\,\,\,\,\,\,\,|c\,x^k|<R_1,k∈ℕ$$
$$f(x-c)= \sum\limits^{\infty}_{n=0}a_n(x-c)^n\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,|x-c|<R_1$$
$$f(x)+g(x)= \sum\limits^{\infty}_{n=0}(a_n+b_n)x^n\,\,\,\,\,\,\,\,\,|x|<min\{R_1,R_2\}$$
## Differentiating and integrating
Suppose $f(x)=c_0+c_1(x-a)+c_2(x-a)^2+...=\sum\limits^{\infty}_{n=0}c_n(x-a)^n$. 
Then: 
* $f'(x)=c_1+2c_2(x-a)+...=\sum\limits^{\infty}_{n=1}nc_n(x-a)^{1-n}$ 
* $\int f(x)dx=C+c_0(x-a)+\frac{c_1}{2}(x-a)^2+...=C+\sum\limits^{\infty}_{n=0}\frac{c_n}{n+1}(x-a)^{n+1}$ 
The **radius** of **convergence** remains the **same**
## Examples of functions
$$\frac{1}{1-x}=\sum\limits_{n=0}^{\infty}x^n\,\,\,\,\,\,\,\,\,(-1<x<1)$$
$$\ln(1+x)=\sum\limits_{n=0}^{\infty}\frac{(-1)^n}{n+1}x^{n+1} \,\,\,\,\,\,\,\,\,(-1<x≤1)$$
$$\arctan(x)=\sum\limits_{n=0}^{\infty}\frac{(-1)^n}{2n+1}x^{2n+1} \,\,\,\,\,\,\,\,\,(-1≤x≤1)$$
# Binomial series
## Theorem
$$(1+x)^x=\sum\limits^{\infty}_{n=0}\binom{r}{n}x^n\,\,\,\,\,\,\,\,for\,\,\,\,-1<x<1$$where the binomial coefficients are given by: $$\binom{r}{0}=1,\,\,\binom{r}{1}=r,...,\binom{r}{n}=\frac{r*...*(r-n+1)}{n!}$$
# Standard series
![[Screenshot 2023-01-14 at 14.25.41.jpg]]
