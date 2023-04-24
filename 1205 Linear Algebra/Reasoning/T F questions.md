# How to solve
Let a statement **S** be given
1. **List**
		list all (some) definitions and theorems which you believe to be relevant for **S**
2. Try
		If you thing **S** is **true**
			Try to give a **proof**
		if you think **S** is **false** 
			Try to construct a **counterexample**
3. answer
		make your **decision** and give a clear **description** of your **proof** or **counterexample**

## Example
If the Span{v1, v2, v3} = Span{v1, v2} then {v1, v2, v3} is linearly dependent. 
1. list
		def. Span{v1, v2 ,..., vp} = set of all linear combinations $c_{1}v_{1}+c_{2}v_{2}+...+c_{p}v_{p}$
.
		def. $\{v_{1}+v_{2}+...+v_{p}\}$ is linearly dependent if $c_{1}\vec{v_{1}}+c_{2}\vec{v_{2}}+...+c_{p}\vec{v_{p}}=\vec{0}$ has non-trivial solutions($c_{1},c_{2},...,c_{p}$ cannot all be equal to 0) 
2. Span$\{v_{1}+v_{2}+v_{3}\}$ = Span$\{v_{1}+v_{2}\}$
		⇒$\vec{v}_{3}∈Span\{v_{1}+v_{2}\}$, i.e., $\vec{v}_{3}=c_{1}\vec{v_{1}}+c_{2}\vec{v_{2}}$ for some c1, c2
		⇒$c_{1}\vec{v_{1}}+c_{2}\vec{v_{2}}+(-1)\vec{v_{3}}=\vec{0}$
		hence (c1,c2,-1) is non trivial solution of $c_{1}\vec{v_{1}}+c_{2}\vec{v_{2}}+c_{3}\vec{v_{3}}=\vec{0}$
		hence {v1, v2, v3} is linearly dependent. 

if two matrices $$A=\left[
\begin{array}{*{3}{rC}l}
    a_{1} &  &  a_{2} &  &  ... &  &  a_{n} 
\end{array}
\right] and B=\left[
\begin{array}{*{3}{rC}l}
    b_{1} &  &  b_{2} &  &  ... &  &  b_{n} 
\end{array}
	\right]$$ are row equivalent then Span{$a_{1} ,a_{2}, ...,a_{n}$} = Span{$b_{1}, b_{2}, ...,b_{n}$}. 