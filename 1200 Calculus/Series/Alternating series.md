An **alternating series** is a [[Series]] whose **terms** are **alternately positive and negative**. 
If alternating series $\sum\limits_{n=1}^{\infty}{b_n}$ satisfies
1. $|b_{n+1}|≤|b_n|$ for all n
2. $\lim\limits_{n \to \infty}|b_n|=0$
**then** the series is **convergent**. 
# Comparison tests
**Suppose** both $\sum\limits_{n=1}^{\infty}{a_n}$ and $\sum\limits_{n=1}^{\infty}{b_n}$ are series with **positive** terms. 
1. If $\sum\limits_{n=1}^{\infty}{b_n}$ is **convergent** and $a_n≤b_n$ for all n,
		then $\sum\limits_{n=1}^{\infty}{a_n}$ is also **convergent**. 
2. If $\sum\limits_{n=1}^{\infty}{b_n}$ is **divergent** and $a_n≥b_n$ for all n, 
		then $\sum\limits_{n=1}^{\infty}{a_n}$ is also **divergent**
3. If $\lim\limits_{n \to \infty}\frac{a_n}{b_n}=c$ where **c** is a finite number and **c > 0**, then either **both** series **converge** or both **diverge**. 
## Intergral test
Suppose $f(k)=a_k$ where f is a **positive**, **continuous** and **decreasing** function on the interval $[1,\infty)$ and let $\sum\limits_{n=1}^{\infty}{a_n}$ is **convergent** then, $$\int_{n+1}^{\infty} f(x) \,dx≤s-s_n≤\int_{n}^{\infty} f(x) \,dx$$ Where $s=\sum\limits_{k=1}^{\infty}{a_k}$ and $s_n=\sum\limits_{k=1}^{n}{a_k}$.
**Improved** error bound: $$s_n+\int_{n+1}^{\infty} f(x) \,dx≤s≤s_n+\int_{n}^{\infty} f(x) \,dx$$Where $s=\sum\limits_{k=1}^{\infty}{a_k}$ and $s_n=\sum\limits_{k=1}^{n}{a_k}$.
## alternating series: error bound
**Suppose** the series $\sum\limits_{n=1}^{\infty}{a_n}$ satisfies the conditions of the **Alternating Series Test** and has **sum** s, then for each **partial** sum: $$s_N=\sum\limits_{n=1}^{N}a_n$$
the following **holds**: $|s-s_N|≤|a_{N+1}|$ 

# Absolute convergence
A series $\sum\limits_{n=1}^{n}{a_n}$ is called **absolutely convergent** if the series $\sum\limits_{n=1}^{n}|{a_n}|$. 
A series $\sum\limits_{n=1}^{n}{a_n}$ is called **conditionally convergent** if it is convergent but not **absolutely convergent**. 
If a series is absolutely convergent, than it is convergent. 
# Riemann's rearrangement theorem:
**Rearranging** the **terms** of an **absolutely convergent** series produces another **absolutely convergent** series with the **same** sum.
Given a **conditionally convergent** series and a **real** number **r** there exists a **rearrangement** of **terms** such that the **sum** of the **rearranged** series equals **r**.