The determinant can tell us if a matrix is actually invertible. $$A=\left[
\begin{array}{*{3}{rC}l}
    a &  &  b  \\
    c &  &  d   
\end{array}
\right]\,\,\,\,\,detA=ad-bc$$
The **geometrical meaning** of the determinant is: if you apply the **linear transformation** of a **matrix** to a certain figure in the x,y-plane than you end up with a figure that is **det A** as **large**

If the determinant is negative, that means that the figure is flipped. ![[Screenshot 2023-03-13 at 12.19.56.jpg]]
# Cofactor expansion
**Theorem**
The determinant of an n x n matrix A can be computed by a cofactor expansion across a row or down a column

Cofactor expansion across row i:$$detA=a_{i1}C_{i1}+a_{i2}C_{i2}+...+a_{in}C_{in}$$
Cofactor expansion down column j:$$det A=a_{1j}C_{1j}+a_{2j}C_{2j}+...+a_{nj}C_{nj}$$

## Examples
h=2$$A=\left[
\begin{array}{*{3}{rC}l}
    a_{11} &  &  a_{12} \\
    a_{21} &  &  a_{22} 
\end{array}
\right]\,\,\,\,\,\,\,\,\,\,\,\,det\,A=a_{11}C_{11}+a_{12}C_{12}$$
$$C_{11}=(-1)^{1+1}*det\,\,A_{11}=det[a_{22}]=a_{22}$$
$$C_{12}=(-1)^{1+2}*det\,\,A_{12}=-det[a_{21}]=-a_{21}$$
$$det\,A=a_{11}C_{11}+a_{12}C_{12}=a_{11}*a_{22}-a_{12}*a_{21}$$

h=3
$$A=\left[
\begin{array}{*{3}{rC}l}
    a_{11} &  &  a_{12} &  &  a_{13} \\
    a_{21} &  &  a_{22} &  &  a_{23} \\
    a_{31} &  &  a_{32} &  &  a_{33} 
\end{array}
\right]\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,det\,\,A=a_{11}C_{11}+a_{12}C_{12}+a_{13}C_{13}$$
$$C_{11}=(-1)^{2}detA_{11}=det \left[
\begin{array}{*{3}{rC}l}
    a_{22} &  &  a_{23} \\
    a_{32} &  &  a_{33} 
\end{array}
\right]
=a_{22}a_{33}-a_{23}a_{32}
$$
$$C_{12}=(-1)^{1+2}*det\,\,A_{12}=-det 
\left[
\begin{array}{*{3}{rC}l}
    a_{21} &  &  a_{23} \\
    a_{31} &  &  a_{33} 
\end{array}
\right]=
-(a_{21}a_{33}-a_{23}a_{31})$$
$$C_{13}=(-1)^{2}det\,\,A_{13}=det \left[
\begin{array}{*{3}{rC}l}
    a_{21} &  &  a_{22} \\
    a_{31} &  &  a_{32} 
\end{array}
\right]
=a_{21}a_{32}-a_{22}a_{31}$$
$$det\,\,A=a_{11}(a_{22}a_{33}-a_{23}a_{32})-a_{12}(a_{21}a_{33}-a_{23}a_{31})+a_{13}(a_{21}a_{32}-a_{22}a_{31})$$
# Determinants of triangular matrices
**Theorem**
If A is an n x n triangular matrix, then det A is the product of the entries on the main diagonal of A:$$det\,\,A=a_{11}a_{22}a_{33}...a_{nn}$$
# Row operations and determinants
**Theorem**
Let B be a matrix obtained by performing one elementary row operation on square matrix A
1. interchange two rows                                   ⇒ det B=-det A
2. multiply one row by a constant k                ⇒ det B= k det A
3. Add a multiple of a row to another row      ⇒ det B = det A

# Properties
**Theorem**
A square matrix A is invertible if and only if det A≠0
**Theorem**
if A is an n x n matrix, then $det\,\,A^{T}=det\,\,A$
**Theorem**
If A and B are n x n matrices, then det AB=(det A)(det B)
**Theorem**
If A is an invertible matrix, then det $A^{-1}=\frac{1}{det\,\,A}$
