[[Double intergrals]]
# Example
## cutting in the vertical direction
$f(x,y)=15x^{2}y$
![[Screenshot 2023-01-31 at 16.01.56.jpg]]
area slice = $\int_{y=0}^{2-2x}15x^{2}ydy=[\frac{15}{2}x^{2}y^{2}]_{y=0}^{2-2x}=\frac{15}{2}x^{2}(2-2x)^2$ 
Volume = $\int^{1}_{x=0}\int^{2-2x}_{y=0}15x^{2}y\,\,dydx=1$ 

## Cutting in the horizontal direction
Area slice = $\int_{x=0}^{1-\frac{1}{2}y}15x^{2}y\,\,dx=[5x^{3}y]_{x=0}^{1-\frac{1}{2}y}=5(1-\frac{1}{2}y)^{3}y$
volume = $\int ^{2}_{y=0}\int_{x=0}^{1-\frac{1}{2}y}15x^{2}y\,\,dxdy=1$

# Region types
## Type I
### Definition 
A region of type I is a region of the form$$D=\{(x,y)|a≤x≤b,\,\,\,\,g_{1}(x)≤y≤g_{2}(x) \}$$$$\int\int_{D}f(x,y)dA=\int _{a}^{b} \int_{g_{1}(x)}^{g_{2}(x)}f(x,y)dydx$$
![[Screenshot 2023-01-31 at 16.21.33.jpg]]
## Type II
A region of type II is a region of the form $$D=\{(x,y)|c≤y≤d,\,\,\,\,h_{1}(x)≤x≤h_{2}(x) \}$$$$\int\int_{D}f(x,y)dA=\int _{c}^{d} \int_{h_{1}(y)}^{h_{2}(y)}f(x,y)dxdy$$![[Screenshot 2023-01-31 at 16.22.43.jpg]]
