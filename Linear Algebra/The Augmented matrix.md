[[System of linear equations]] is completely determined by the **coefficients** and the **numbers** on the **right-hand side**; the choice of the **names** of the variables for the **unknowns** is **not essential**.

Thus this: 
$$\left\{
\begin{array}{*{3}{rC}l}
    x_{1} & + &  5x_{2} & + & 3x_{3} & = & 1 \\
    2x_{1} & + &  x_{2} & + &  15x_{3} & = &  8 \\
    -x_{1} & + &  x_{2} & + & 3x_{3} & = & 1
\end{array}
\right.$$
Can be written as this:
$$
\left[
\begin{array}{*{3}{rC}l}
    1 &  &  5 &  &  3 & | &  1 \\
    2 &  &  1 &  & 15 & | &  8 \\
    -1 &  & 1 &  &  3 & | &  1 
\end{array}
\right]
$$

# Operations
1. one row is replaced by the sum of itself and a multiple of another row
2. 2 rows are interchanged
3. one row is multiplied by a non zero constant
![[Screenshot 2023-02-21 at 15.27.49.jpg]]

# Solutions
## One unique solution
$$\left[
\begin{array}{*{3}{rC}l}
    ■ &  & *  &  &  * & | &  * \\
    0 &  &  ■ &  &  * & | &  * \\
    0 &  &  0 &  &  ■ & | &  * 
\end{array}
\right]$$
## No solution
$$\left[
\begin{array}{*{3}{rC}l}
    ■ &  & *  &  &  * & | &  * \\
    0 &  &  ■ &  &  * & | &  * \\
    0 &  &  0 &  &  0 & | &  ■ 
\end{array}
\right]$$
## Infinite solutions
$$\left[
\begin{array}{*{3}{rC}l}
    ■ &  & *  &  &  * & | &  * \\
    0 &  &  ■ &  &  * & | &  * \\
    0 &  &  0 &  &  0 & | &  0 
\end{array}
\right]$$
# Consistency
Definition: 
A system is called: 
* **consistent** if it has at least one solution
* **inconsistent** if it has no solution at all

If a system is inconsistent then the row reduction algorithm will produce at least one row of the form $$\left[
\begin{array}{*{3}{rC}l}
    0 &  &  0 &  &  0 & | &  c 
\end{array}
\right]$$ With $c≠0$
