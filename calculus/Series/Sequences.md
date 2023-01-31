The terms in a series are described by $a_n$ where the n is the nth time the operation has been preformed. n is a part of the natural numbers. 

# Recursively definition
A recursive definition is based on doing a operation on previous terms. Example: 
$a_{n}=a_{n-1}/2$
Here if n = 1 is $a_1=1$
this will result in the following permutations: 
$a_2=\frac{1}{2}$
$a_3=\frac{1}{4}$
$a_4=\frac{1}{8}$
$a_5=\frac{1}{16}$

# Explicit formula
Some series can be described by an explicit formula, such as the formula above. 
This formula results in $a_n=(\frac{1}{2})^n$ 
Using this formula there is no longer a need to know the previous term. 

# Limits with sequences
A **sequence** {$a_n$} has limit **L** **if** $a_n$ -> L when **n -> ∞**
If such an **L** **exists**, the sequence is **convergent**, **otherwise** it is **divergent**. 
When there is unbounded growth the sequence is divergent. 

# Rules of calculation
Suppose $\lim\limits_{n \to \infty}a_n=L$ and $\lim\limits_{n \to \infty}b_n=M$ 
Then: 
	$\lim\limits_{n \to \infty}c\,a_n=cL$
	$\lim\limits_{n \to \infty}a_n+b_n=L+M$
	$\lim\limits_{n \to \infty}a_n*b_n=L*M$
	$\lim\limits_{x \to \infty}\frac{a_n}{b_n}=\frac{L}{M}$ if $M≠0$ 
## Substitution
Let f be a function and ($a_n$) a sequence such that
• $\lim\limits_{n \to \infty}a_n=L$
• f is **continuous** at L.
Then $\lim\limits_{n \to \infty}f(a_n) = f(L)$.

# Squeeze theorem
if $a_n≤b_n≤c_n$ when **n** is **sufficiently** large and:
$\lim\limits_{n \to \infty}a_n=L=\lim\limits_{n \to \infty}c_n$
Then $\lim\limits_{n \to \infty}b_n=L$
