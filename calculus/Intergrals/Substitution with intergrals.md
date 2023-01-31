Using substitution [[Integral]] might be easier to compute. 
Example: 
$$f(x)=5x\sqrt{1+x^2}$$
$$u=1+x^2$$
$$du=2x\,dx$$
hence:
$$5x\,dx=\frac{5}{2}\,du$$
substitute u and du:
$$\int5x\sqrt{1+x^2}=\int\frac{5}{2}\,\sqrt{u}\,du=\frac{5}{2}\int\sqrt{u}\,du$$
$$\frac{5}{2}\int\sqrt{u}\,du=\frac{5}{3}u^{\frac{3}{2}}+c$$
Fill u back in:
$$\frac{5}{3}(1+x^2)^{\frac{3}{2}}+c$$
