The technique of implicit differentiation allows you to find the  [[Derivative]] of y with respect to x without having to solve the given equation for y. The chain rule must be used whenever the function y is being differentiated because of our assumption that y may be expressed as a function of x.
___

$$x^2+y^2=4$$
Consider a part of the curve where $y = y(x)$ can be assumed $$x^2+y^2=4<=>x^2+(y(x))^2=4$$
Differentiate left and right with respect to x. 
$2x+2y\frac{dx}{dy}=0$
$x+y\frac{dx}{dy}=0$
$y\frac{dx}{dy}=-x$
$\frac{dx}{dy}=-\frac{x}{y}$

## Example two
$$x^3+y^3=6xy$$
$3x^2+3y^2\frac{dy}{dx}=6(y+x\frac{dy}{dx})$
$x^2+y^2\frac{dy}{dx}=2y+2x\frac{dy}{dx}$
$(-2x+y^2)\frac{dy}{dx}=2y-x^2$   =>   $$\frac{dy}{dx}=\frac{2y-x^2}{-2x+y^2}$$
To determine the horizontal tangent, we have to respect the following rules. 
1) $2y-x^2=0$   => $y=\frac{1}{2}x^2$
2) $-2x+y^2/=0$ 
3) $x^3+y^3=6xy$   => $x^3+(\frac{1}{2}x^2)^3=6x\frac{1}{2}x^2$

$x^3+\frac{1}{8}x^6=3x^3$   =>  $\frac{1}{8}x^6=2x^3$
$x^6=16x^3$            =>  $x^3(x^3+16)=0$

$x=0$         v       $x^3+16=0$
reject                 $x=\sqrt[3]{16}$
$x=2^{\frac{4}{3}}$ and $y=2^{\frac{5}{3}}$

