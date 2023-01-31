The definition of a [[Derivative]] of a function of two variables.
**Example**:
$p(x) = f(x,b)$
$f_{x}(a,b)=p'(a)$
$$f_{x}(a,b)=\lim\limits_{h \to 0}\frac{f(a+h,b)-f(a,b)}{h}$$
$q(y)=f(a,y)$
$f_{y}(a,b)=q'(b)$
$$f_{y}(a,b)=\lim\limits_{h \to 0}\frac{f(a,b+h)-f(a,b)}{h}$$

**Theorem**:
Suppose that f is defined on a disk D that contains the point $(a,b)$. If the function $f_{xy}$ and $f_{yx}$ are both continuous on D, then $$f_{xy}(a,b)=f_{yx}(a,b)$$
# Tangent
The formula for a tangent line is:$$y=f(a)+f'(a)(x-a)$$
## Tangent plane
The definition of a tangent plane is: 
The tangent plane to the graph of f at the point P is the plane through the tangent lines $T_{1}$ and $T_{2}$ to any two curves $C_{1}$ and $C_{2}$ through P on the surface $z=f(x,y)$
**Theorem**:
Suppose f has continuous partial derivatives. The tangent plane to the surface $z=f(x,y)$ at the point $P=(a,b,f(a,b))$ can be described by the equation:$$z=f(a,b)+f_{x}(a,b)(x-a)+f_{y}(a,b)(y-b)$$
## Definition
The function: $$L(x,y)=f(a,b)+f_{x}(a,b)(x-a)+f_{y}(a,b)(y-b)$$
is called the linearisation of f at the point $(a,b)$.

## Linearization in higher dimensions
Let ${x}=( x_{1},x_{2},...,x_{n})$ and ${a}=(a_{1},a_{2},...,a_{n})$.
The linearization  of the function f at the point **a** is$$L(x)=f(a)+f_{x_{1}}(x_{1}-a_{1})+...+f_{x_{n}}(a)(x_{n}-a_{n})$$ 
# Differentiability
## Definition
A function f of several variables is differentiable at a if $$\lim\limits_{\vec{x} \to \vec{a}}\frac{f(x)-L(x)}{|x-a|}=0$$
## Theorem
if the partial derivatives $f_{x}$ and $f_{y}$ exist near $(a,b)$ and are continuous at $(a,b)$, then f is differentiable at $(a,b)$.

