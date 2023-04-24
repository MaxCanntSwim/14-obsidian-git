Critical points for [[Two variable]] functions. 
___

## Theorem
if f has a local maximum or minimum at a point $(a,b)$ and the first order partial derivatives exist at that point, then the first order partial derivatives at that point are equal to 0. 
in a formula: $$f_{x}(a,b)=0\,\,\,\,and\,\,\,\,f_{y}(a,b)=0$$
This does not hold the other way around, thus if the partial derivatives $f_{x}(a,b)=0\,\,\,\,and\,\,\,\,f_{y}(a,b)=0$ hold, does not mean we are at a maximum or minimum. 

**Example**:
$z=x^{2}-y^{2}$
$f_{x}(x,y)=2x ⇒ f_{x}(0,0)=0$
$f_{y}(x,y)=2y ⇒ f_{y}(0,0)=0$
![[Screenshot 2023-01-31 at 13.59.53.jpg]]
## Closed and bounded region method
To find the absolute maximum and minimum values of a continuous function f on a closed and bounded domain D:
1.  ﻿﻿﻿Find the values of f at the critical points of f in the interior of the region D.
2.  ﻿﻿﻿restrict the function to the boundary of the region D to find the values at the critical points on this boundary.
3.  ﻿﻿﻿The largest of the values from Steps 1 and 2 is the absolute maximum value; the smallest of these values is the absolute minimum value.
# Second Derivatives Test
## Theorem
Suppose that the second-order partial derivatives of f are continuous on a disk with center $(a,b)$, and suppose that $f_{x}(a,b)=0\,\,\,\,and\,\,\,\,f_{y}(a,b)=0$. Let$$D=f_{xx}(a,b)f_{yy}(a,b)-f_{xy}(a,b)^{2}$$ 
* if D > 0 and $f_{xx}(a,b)$ > 0, then $f(a,b)$ is a local minimum
* if D > 0 and $f_{xx}(a,b)$ < 0, then $f(a,b)$ is a local maximum
* if D < 0, then $(a,b)$ is a saddle point
