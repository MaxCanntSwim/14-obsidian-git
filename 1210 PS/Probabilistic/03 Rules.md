# Sum rule
from definition: if B, B are disjoint, then P(A∪B) = P(A) + P(B)

if A, B are not disjoint
![[IMG_3920.jpeg]]
also C and A∩B are disjoint and C∪(A∩B)=B
So P(B)=P(C∪(A∩B)) = P(C)+P(A∩B)
**P(A∪B)=P(A)+P(B)-P(A∩B)**

# Complement rule
A domain Ω and a subset A and $A^{c}$ the **complement**. 
To calculate the **complement**:$$P(A^{c})=1-P(A)$$
Thus: P($A ∪ A^{c}$)= P(A)+P($A^{c}$)
	=P(Ω)
Thus it follows that a subset **union** with its complement results in the entire **sample space**. 

# Conditional probability
The chance of a result occurring in a pre-defined sub-space$$P(A|C)=\frac{P(A∩C)}{P(C)}$$

## Examples
What is the probability that the first dice we throw is a 5 if we know that the sum of the two is 9. 
A is the total amount of combinations where the first dice throw is 5, there are 6 entries in this set. 
C is all possible combinations where the sum is 9, thus C contains 4 entries. 
This is **conditional probability**, thus the formula for this is: $$P(A|C)=\frac{P(A∩C)}{P(C)}$$
Provided that P(C)>0
P(A∩C)=1, since the only way to make 9 with the first entry being 5 is by the second entry being 4. 
Thus the final result is $\frac{1}{4}$.

# Multiplication rule
Theorem:
for any two events A and C it holds that:
$P(A∩C)=P(A | C)P(C)$

## Example
A box contains 10 pebbles of which 3 are granite.
You take out 2 pebbles (without looking).
What is the probability that both are granite?
C     first one is made of granite
A     second one is made of granite
____
$P(A∩C)=P(C)*P(A | C)$
$\frac{3}{10}*\frac{2}{9}=\frac{1}{15}$

# Law of total probability
Theorem:
Let A and C be two events. We have:$$P(A)=P(A|C)P(C)+P(A|C^{c})P(C^{c})$$
Theorem: 
Suppose $C_{1},C_{2},...,C_{m}$ are disjoint events such that$$C_{1}∪C_{2}∪...∪C_{m}=Ω$$
for any event A we have: $$P(A)=P(A|C_{1})P(C_{1})+P(A|C_{2})P(C_{2})+...+P(A|C_{m})P(C_{m})$$

## Example
A company has three machines C1, C2 and C3 for making resistors.
The accuracy (percentage of correctly produced resistors) and production share of the machines are given in the following table:
![[Screenshot 2023-04-25 at 10.04.42.jpg]]
All of the resistors are mixed together at random in one bin.
What is the probability that an arbitrary resistor is accurate?
![[IMG_3922.jpeg]]
What we want to know P(A).
A = $(A∩C_{1})∪(A∩C_{2})∪(A∩C_{3})$
P(A) = $P(A∩C_{1})+P(A∩C_{2})+P(A∩C_{3})$
		=$P(C_{1})P(A|C_{1})+P(C_{2})P(A|C_{2})+P(C_{3})P(A|C_{3})$
		=$0.3*0.8+0.5*0.9+0.2*0.6$

# Bayes' Rule:
Theorem: 
Suppose the events $C_{1},C_{2},...,C_{m}$ are disjoint and fill up the sample space Ω. then the conditional probability of $C_{i}$ given some event A is given by $$P(C_{i})=\frac{P(A|C_{i})P(C_{i})}{P(A|C_{1})P(C_{1})+P(A|C_{2})P(C_{2})+...+P(A|C_{m})P(C_{m})}$$
Very often (as in the post-lecture video) m = 2 and $C_{1}=B$, $C_{2}=B^{c}$

## Example
![[Screenshot 2023-04-25 at 10.04.42.jpg]]
I take a resistor out of the bin and I notice it is accurate.
What is the probability that it was made by machine 1?
$$P(C_{1}|A)=\frac{P(C_1∩A)}{A}$$
$$=\frac{P(A|C_{1})P(C_{1}))}{P(C_{1})P(A|C_{1})+P(C_{2})P(A|C_{2})+P(C_{3})P(A|C_{3})}$$
