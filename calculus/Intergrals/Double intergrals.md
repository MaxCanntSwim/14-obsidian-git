A possible way to solve this is using the Riemann sum.
For the function $z=f(x,y)$.
we make small squares on the region of the graph. This can be described by 
$\Delta A=\Delta x \Delta y$
than we can make an approximation of the volume:
$$Volume≈\sum\limits_{i=1}^{n}\sum\limits_{j=1}^{m}f(x_{i},y_{j})\Delta A$$
# The double (Riemann) integral
## Definition
The double [[Integral]] of $f(x,y)$ over a region $D⊂ℝ^2$ is $$\int \int _{D}f(x,y)dA=\lim\limits_{\Delta A_{i} \to 0^{+}}\sum\limits_{i}f(x_{i}^{*},y_{j}^{*})\Delta A_{i}$$**Theorem**
The Riemann integral exists for any continuous function on a well-behaved region D.

# Properties
Let $f,g$ be continuous functions on well-behaved $D⊂ℝ^2$. 
$$\int \int _{D}f(x,y)+g(x,y)dA=\int \int _{D}f(x,y)dA+\int \int _{D}g(x,y)dA$$
$$\int \int _{D}cf(x,y)dA=c\int \int _{D}f(x,y)dA$$
if $f≥g$ on D then $\int \int _{D}f(x,y)dA≥\int \int _{D}g(x,y)dA$
if $D_{1}$ and $D_{2}$ are disjoint and well-behaved, then$$\int \int _{D_{1}}f(x,y)dA+\int \int _{D_{2}}f(x,y)dA=\int \int _{D_{1}∪D_{2}}f(x,y)dA$$
## Area
for a well-behaved region $D⊂ℝ^2$ we have $$Area(D)=\int \int_{D}1dA$$
## Separable functions
if $f(x,y)=g(x)h(y)$ on the rectangle $R=[a,b]*[c,d]$ then$$\int \int_{R}f(x,y)dA=(\int_{a}^{b}g(x)dx)(\int_{c}^{d}h(y)dy)$$
