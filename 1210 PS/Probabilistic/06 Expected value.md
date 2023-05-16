# Expectations of standard distributions
| Distribution        | Expectation                                                                                               | Result              |
| ------------------- | --------------------------------------------------------------------------------------------------------- | ------------------- |
| Bin(n,p)            | $\sum\limits_{k=0}^{n}k\binom{n}{k}p^{k}(1-p)^{n-k}$                                                      | $np$                |
| Geo(p)              | $\sum\limits^{\infty}_{k=1}kp(1-p)^{k-1}$                                                                 | $\frac{1}{p}$       |
| Pois($\mu$)         | $\sum\limits_{k=0}^{\infty}k \frac{\mu^{k}}{k!}e^{-\mu}$                                                  | $\mu$               |
| Exp($\lambda$)      | $\int\limits_{0}^{\infty}x\lambda e^{-\lambda x}dx$                                                       | $\frac{1}{\lambda}$ |
| N($\mu,\sigma^{2}$) | $\int\limits_{-\infty}^{\infty}x \frac{1}{\sigma\sqrt{2\pi}}e^{-\frac{1}{2}(\frac{x-\mu}{\sigma})^{2}}dx$ | $\mu$                    |
# Example
You have a box with 5 balls, 
	2 green balls
	3 red balls
If you pick a green ball you get 1 euro, if you pick a red ball you lose 1 euro. 

## Games 1
pick 1 ball, what is the chance of you ending up with more money
	the chance of getting a green ball first is $\frac{2}{5}$ and the chance of picking a red ball is $\frac{3}{5}$
		This game is obviously in favour of the house. 
## Game 2
We change the game, you can continue picking balls for as long as you want. 
	We make a strategy 
		![[Screenshot 2023-05-16 at 12.56.27.jpg]]
	Using this strategy our chance of gaining 1 euro are $$P(X=1)=\frac{2}{5}+{\frac{3}{5}}*{\frac{2}{4}}*{\frac{1}{3}}={\frac{1}{2}}$$ ![[Screenshot 2023-05-16 at 12.59.37.jpg]]

# Definition
The expectation $E[X]$ of a discrete random variable X is defined as the number $$E[X]=\sum\limits_{a_{i}}a_{i}*P(X=a_{i})$$ Thus the expectation of the game above is $$1*0.5+0*0.2+-1*0.3$$

## Centre of mass
The expectation of a continuous random variable X with pdf f is given by $$E[X]=\int \limits_{-\infty}^{+\infty}xf(x)dx$$ Interpretation: 
$E[X]$ is centre of mass of the distribution. 
					![[Screenshot 2023-05-16 at 13.11.52.jpg]]

