# Definition
A random variable X has a binomial distribution with parameters n and p if x can take on the values k = 0, 1,...,n with probabilities $$P(X=k)=\binom{n}{k} p^{k}(1-p)^{n-k}$$
→ repeat the same Bernoulli trial, n times
→ let Y be the number of successes
→ then y is a binomial RV: Y ~ $Bin(n, p)$
Same example as in [[02 Discrete random variables]] with the dice: throw a fair dice 10 times, let Y be the number of fours, Y ~ $Bin(10, \frac{1}{6})$

→ Can we compute P(Y=2)
e.g. 2 successes (S)
means 8 failures
using the formula$$P(Y=2)=\binom{10}{2}(\frac{1}{6})^{2}(\frac{5}{6})^{8}=\frac{10!}{2!*8!}(\frac{1}{6})^{2}(\frac{5}{6})^{8}=\frac{10*9}{1*2}(\frac{1}{6})^{2}(\frac{5}{6})^{8}$$$$P(Y=k)=p^{k}(1-p)^{n-k}\binom{n}{k}$$
![[Screenshot 2023-04-28 at 10.26.46.jpg]]
# Geometric distribution
A random variable X has a geometric distribution with parameter p if X can take on the values k = 1, 2, 3,..., with probabilities $$P(X=k)=p*(1-p)^{k-1}$$
Notation: X ~ $Geo(p)$
![[Screenshot 2023-04-28 at 10.26.33.jpg]]

# Poisson distribution
A random variable X has Poisson distribution with parameter μ if X can take on the values k = 0, 1, 2,.., with probabilities $$P(X=k)=\frac{\mu^{k}}{k!}e^{-\mu}$$
Notation: X~$Pois(\mu)$
![[Screenshot 2023-04-28 at 10.29.44.jpg]]
