The **domain** of a m x n matrix is $ℝ^{n}$ and the **codomain** is $ℝ^{m}$
A matrix of size m x n defines a **transformation** T : $ℝ^{n}\toℝ^{m}$, defined by $T( \vec{x})=A \vec{x}$

# Linear transformations
**Definition**:
A transformation T : $ℝ^{n}\toℝ^{m}$ is called a linear transformation if: 
1. $T( \vec{u}+\vec{v})=T( \vec{u})+T(\vec{v})$ for all vectors **u, v** in $ℝ^{n}$
2. $T(c \vec{u})=cT(\vec{u})$ of all scalars c in ℝ and vectors **u** in $ℝ^{n}$

**Remark**:
if T is a linear transformation, then:
1. $T(\vec{0})=\vec{0}$
2. $T(c_{1}\vec{v}_{1}+...+c_{p}\vec{v}_{p})=c_{1}T(\vec{v}_{1})+...+c_{p}T(\vec{v}_{p})$ for all scalars $c_{1}, c_{2}, ..., c_{p}$ and all vectors $\vec{v}_{1},\vec{v}_{2},...,\vec{v}_{p}$ in $ℝ^{n}$

# Standard matrix
**Rotation theorem**:
A **rotation** in the **plane** about the **origin** through an angle **𝜑** is a **linear** **transformation**, with **standard matrix**:$$\left[
\begin{array}{*{3}{rC}l}
    \cos𝜑 &  &  -\sin𝜑 \\
    \sin𝜑 &  &  cos𝜑 
\end{array}
\right]$$

# Composition of linear transformations
**Theorem**:
Given two linear transformations $T:ℝ^{p}\to ℝ^{n}\,\,\,and\,\,\,S:ℝ^{n}\toℝ^{m}$, then the composition $S∘T:ℝ^{p}\toℝ^{m}$, defined by $$(S∘T)(\vec{x})=S(T(\vec{x}))$$ is also a linear transformation. 
