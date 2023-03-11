**Definition**
A square n x n matrix A is invertible if there is an n x n matrix C such that$$CA=I_{n}\,\,\,\,and\,\,\,AC=I_{n}$$
If C exists, it is unique and it is called the inverse of A. it is denoted by $A^{-1}$.

If C does not exist, we call A singular. 
**Theorem**
A 2 x 2 matrix A is invertable if $ad-bc≠0$, then it has the inverse:$$A=
\left[
\begin{array}{*{3}{rC}l}
    a &  &  b \\
    c &  &  d 
\end{array}
\right]
\,\,\,then\,\,\,A^{-1}=\frac{1}{ad-bc}
\left[
\begin{array}{*{3}{rC}l}
    d &  &  -b \\
    -c &  &  b 
\end{array}
\right]$$if $ad-bc=0$ then A is singular. 

**Theorem**
If **A** is an invertible **n x n** matrix, then for each **b** in $ℝ^{n}$ the equation $$A \vec{x}=\vec{b}$$has unique solution $$\vec{x}=A^{-1}\vec{b}$$
# Properties
Let A and B be n x n invertible matrices, then: 
1. $A^{-1}$ is invertible and $(A^{-1})^{-1}=A$
2. AB is invertible and $(AB)^{-1}=B^{-1}A^{-1}$
3. $A^{T}$ is invertible and $(A^{T})^{-1}=(A^{-1})^{T}$

# Alg for finding $A^{-1}$ 
**Theorem**
An n x n matrix A is invertible if and only if A is row equivalent to $I_{n}$.

## The Algorithm
1. Row reduce the augmented matrix $[A|I_{n}]$
2. if A is row equivalent to $I_{n}$ then $[A|I_{n}]$ is row equivalent to $[I_{n}|A^{-1}]$
3. Otherwise, A is not invertible

# The invertible Matrix Theorem
If A is an n x n matrix, then the following statements are equivalent:
1. A is an **invertible** matrix
2. A is **row equivalent** to $I_{n}$
3. A has **n** pivot positions
4. The equation $A \vec{x}=\vec{0}$ has only the **trivial** solution
5. The columns of A are **linearly independent**
6. The equation $A \vec{x}=\vec{b}$ has at least one solution for each **b** in $ℝ^{n}$
7. The columns of **A** **span** $ℝ^{n}$
8. There is an n x n matrix **C** such that $CA=I_{n}$
9. There is an n x n matrix **D** such that $AD=I_{n}$
10. $A^{T}$ is an **invertible** matrix
13. The columns of A form a basis of $ℝ^{n}$
14. $ColA=ℝ^{n}$
15. $dimColA=n$
16. $rank A=n$
17. $Nul A = \{\vec{0}\}$
18. $dim Nul A = 0$