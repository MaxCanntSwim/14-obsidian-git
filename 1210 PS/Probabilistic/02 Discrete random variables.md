# Definition
Let Ω be a sample space. A discrete random variable is a function 
X: Ω → ℝ that takes on a finite number of values $a_{1}, a_{2},...,a_{n}$ or an infinite number of values $a_{1}, a_{2}, a_{3},...$


## The probability mass function
### Definition
The probability mass function p of a discrete random variable X is the function p: $ℝ → [0,1]$ defined by $$p(a)=P(X=a)\,\,\,\,for\,\,\,\,-\infty<a<\infty$$
Note that p(a)=0 for most values of a. 
![[Screenshot 2023-04-28 at 09.23.15.jpg]]
## The distribution function
### Definition
The distribution function F of a discrete random variable X is the function F : $ℝ→[0,1]$ defined by $$F(a)=P(x≤a)\,\,\,\,for\,\,\,\,-\infty<a<\infty$$
![[Screenshot 2023-04-28 at 09.20.57.jpg]]

# A Bernoulli trial
An experiment with only 2 outcomes.
## Definition
A random variable X has a Bernoulli distribution if X only takes the values 0 and 1, with probabilities 
			$P(X=1)=p$
			$P(X=0)=p-1$
Notation: X ~ $Ber(p)$ means X has the Bernoulli distribution.

## Example
Throw a fair die, 
	let X=1 if the throw was a 4
	else X=0
→ X ~ $Ber(\frac{1}{6})$
![[IMG_3951.jpeg]]![[IMG_3952.jpeg]]
