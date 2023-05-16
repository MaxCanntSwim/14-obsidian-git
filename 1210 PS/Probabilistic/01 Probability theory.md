# Definition
an **experiment** is an **activity** or **procedure** that produces **distinct** possibilities, called **outcomes**. 
In probability and statistics, **randomness** is involved: outcome is **uncertain**.
The **set** of all **outcomes** is called the **sample space**. 

When **grouping** outcomes together in an experiment, it is called an **event**: this is a **subset** of Ω (sample space)
# Independence
The events $A_{1}, A_{2},...,A_{m}$ are called independent if each collection $A_{i1}, A_{i2},...,A_{im}$ it holds that $$P(A_{i1}∩ A_{i2}∩...∩A_{im})=P(A_{i1})P(A_{i2})...P(A_{im})$$

## 2 variables
For a two-variable function
$P(D|T)=P(D)$
$P(T|D)=P(T)$
$P(D∩T)=P(D)P(T)$

# Jensen's inequality
1. Let g be a **convex** function and let X be a random variable. Then $$g(E[X])≤E[g(X)]$$
2. Let g be a **concave** function and let X be a random variable. Then $$g(E[X])≥E[g(X)]$$
# Example
Throw a red and a blue die
e.g red : 5
	blue : 3
	outcome = (5,3)
**Sample space**: the set of all outcomes
$\Omega =\{ (1,1), (1,2), (1,3)... \}$
	=$\{ (i,j):1≤i,j≤6 \}$
E: sum of the two die throws is 4
	=$\{ (3,1),(2,2),(1,3) \}$