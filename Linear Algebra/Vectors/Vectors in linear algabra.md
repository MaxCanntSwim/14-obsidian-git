For the basic operations take a look at [[Vector]] in the calculus map. 

Given **vectors** $\vec{v}_{1},\vec{v}_{2},...,\vec{v}_{p}$ in $ℝ^{n}$ and given **scalars** $c_{1}, c_{2}, ..., c_{p}$ the **vector** $\vec{y}$ defined by$$\vec{y}=c_{1}\vec{v}_1+...+c_{p}\vec{v}_{p}$$
is called a **linear combination** of $\vec{v}_{1},\vec{v}_{2},...,\vec{v}_{p}$ with **weights** $c_{1}, c_{2}, ..., c_{p}$.

The vector equation$$x_{1}\vec{a}_{1}, x_{2}\vec{a}_{2}, ..., x_{n}\vec{a}_{n}=\vec{b}$$
is equivalent with the linear system with augmented matrix$$\left[
\begin{array}{*{3}{rC}l}
    \vec{a}_{1} &  &  \vec{a}_{2} & &...& &  \vec{a}_{n} & | &  b 
\end{array}
\right]$$ **Remark**
$\vec{b}$ is a linear combination of $\vec{a}_{1}, \vec{a}_{2},...,\vec{a}_{n}$ if and only if there **exists** a **solution** to the linear system above.

# Matrix-vector product
**Definition**:
The product of a **matrix** A with **n** **columns** and a vector $\vec{x}$ with **n** **entries** is defined by$$A \vec{x}=\left[
\begin{array}{*{3}{rC}l}
    \vec{a}_{1} &  &  \vec{a}_{2} & &...& &  \vec{a}_{n}
\end{array}
\right]
\left[
\begin{array}{*{3}{rC}l}
    x_{1} \\
    x_{2} \\
    . \\
    . \\
    x_{n} 
\end{array}
\right]= x_{1}\vec{a}_{1}, x_{2}\vec{a}_{2}, ..., x_{n}\vec{a}_{n}$$
# Existence of solutions
Theorem:

Let **A** be an **m x n matrix**, then the following statements are **equivalent**:

1.  ﻿﻿﻿For **each** $\vec{b}$ in $ℝ^{m}$, the **equation** $A \vec{x} = \vec{b}$ has a solution.
2.  ﻿﻿﻿**Each** $\vec{b}$ in $ℝ^{m}$ is a linear **combination** of the columns of **A**.
3.  ﻿﻿﻿The columns of **A** span $ℝ^{m}$.
4.  ﻿﻿﻿**A** has a **pivot** position in every **row**.