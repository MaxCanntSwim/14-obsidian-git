# Special types of matrices
Definition:
An m × n matrix A is called a:
-   ﻿﻿**zero matrix** if all entries are **zeros**.
-   ﻿﻿**square** matrix if **m = n**.

The **main diagonal** of a square matrix consists of the entries $a_{ii}$.
A **square** matrix is called **a(n)**:
-   ﻿﻿**diagonal matrix** if all off-diagonal entries are **zeros**.
-   ﻿﻿**identity matrix** if it is a diagonal matrix with **1's** on the **main diagonal**.
-   ﻿﻿**lower /upper triangular** matrix if all entries **above/ below** the main diagonal are **zeros**.

# Transposing
**Definition**:
the **Transpose** of an m x n matrix A is an n x m matrix $A^{T}$ that has its columns the rows of A in the same order. $$A=
\left[
\begin{array}{*{3}{rC}l}
    1 &  &  8 &  &  3 \\
    -2 &  &  5 &  &  7 
\end{array}
\right]
\to A^{T}=
\left[
\begin{array}{*{3}{rC}l}
    1 &  &  -2 \\
    8 &  &  5 \\
    3 &  &  7 
\end{array}
\right]$$

# Matrix multiplication
**Theorem**:
if A is an m x n matrix and B is an n x p matrix with columns $b_{1},...,b_{p}$, then the product AB is the m x p matrix whose columns are $Ab_{1},...,Ab_{p}$.
That is $$AB=A 
\left[
\begin{array}{*{3}{rC}l}
    b_{1} &  &  b_{2} &  &  ... &   &  b_{p} 
\end{array}
\right] = 
\left[
\begin{array}{*{3}{rC}l}
    Ab_{1} &  &  Ab_{2} &  &  ... &   &  Ab_{p} 
\end{array}
\right]$$
# Powers of matrices
**Definition**:
if A is an n x n matrix and if k is a positive integer, then $$A^{k}=AAA...A$$
for k=0 we define $a^{0}=I$.
