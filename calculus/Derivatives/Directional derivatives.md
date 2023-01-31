Suppose we want the slope at $(x_{0},y_{0})$ in the direction of $\vec{u}=\langle a,b\rangle$, call it $D_{u}f(x_{0},y_{0})$
# Definition
The directional derivative $D_{u}f(x_{0},y_{0})$ of f at $(x_{0},y_{0})$ in the direction of a unit vector $\vec{u}=\langle a,b \rangle$ is defined by:$$D_{u}f(x_{0},y_{0})=\lim\limits_{h \to 0}\frac{f(x_{0}+ah,y_{0}+bh)-f(x_{0},y_{0})}{h}$$if this limit exists. 

**Example**: 
Calculate $D_{u}f(1,1)$
given $f(x,y)=4-x^{2}-2y^{2}$ and $\vec{u}=\langle \frac{3}{\sqrt{10}}, \frac{1}{\sqrt{10}} \rangle$ 
1. $f(1,1)=4-(1)^{2}-2(1)^{2}=1$
2. $f(1+\frac{3}{\sqrt{10}}h, 1+\frac{1}{\sqrt{10}}h)=4-(1+\frac{3}{\sqrt{10}})^{2}-2(1+\frac{1}{\sqrt{10}})^{2}$ 
				$=1-\sqrt{10}h-\frac{11}{10}h^{2}$
3. $D_{u}f(1,1)=\lim\limits_{h \to 0}\frac{-\sqrt{10}h-\frac{11}{10}h^{2}}{h}$
			$=\lim\limits_{h \to 0}-\sqrt{10}-\frac{11}{10}h$ 
			$=-\sqrt{10}$

**Theorem**
Suppose f is a differentiable function of x and y, then f has a directional derivative in the direction of any unit vector $\vec{u}=\langle u_{1},u_{2} \rangle$ and $$D_{\vec{u}}f(x,y)=f_{x}(x,y)u_{1}+f_{y}(x,y)u_{2}$$
## Normalization
Given a vector u ≠ 0 we define the normalized vector $$û = \frac{1}{|\vec{u}|}u$$The normalised vector has the same direction, but is of unit length. 

# The gradient for two variables
$D_{\vec{u}}f(x,y)=f_{x}(x,y)u_{1}+f_{y}(x,y)u_{2}$ 
				$\langle f_{x}(x,y),f_{y}(x,y) \rangle*\langle u_{1},u_{2}\rangle$ 
				$\langle f_{x}(x,y),f_{y}(x,y)\rangle*\vec{u}$
## Definition
The gradient of a function f at $(x,y)$ is given by $$\nabla f(x,y)=\langle f_{x}(x,y),f_{y}(x,y)\rangle=\frac{\delta f}{\delta x}i+\frac{\delta f}{\delta y}j$$
