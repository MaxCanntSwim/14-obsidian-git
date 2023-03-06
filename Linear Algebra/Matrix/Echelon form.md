**Definition**
A matrix is in **echelon form** if it has the following **three** **properties**.

1.  ﻿﻿﻿**All** **nonzero** rows are **above** any **row** of all **zeros**.
2.  ﻿﻿﻿Each leading entry (**pivot**) is in a **column** to the right of the leading entry in the **previous** row.
3.  ﻿﻿﻿All entries **below** a **leading** entry are **zero**.
# Examples 

$$\left[
\begin{array}{*{3}{rC}l}
    ■ &  & *  &  &  * & | &  * \\
    0 &  &  ■ &  &  * & | &  * \\
    0 &  &  0 &  &  0 & | &  0 \\ 
    0 &  &  0 &  &  0 & | &  0
\end{array}
\right]$$
$$\left[
\begin{array}{*{3}{rC}l}
    0 &  & ■  &  &  * & & *  &  &  * & & *  &  &  * & & * &| &  * \\
    0 &  &  0 &  &  0 & & ■  &  &  * & & *  &  &  * & & * &| &  * \\
    0 &  &  0 &   &  0 & & 0  &  &  ■ & & *  &  &  * & & * &| &  * \\ 
    0 &  &  0 &   &  0 & & 0  &  &  0 & & 0  &  &  0 & & ■ &| &  *
\end{array}
\right]$$

# Reduced echelon form
Definition:
A matrix is in **reduced echelon** form if it has the following **three** properties:
1.  ﻿﻿﻿It is in **echelon** form.
2.  ﻿﻿﻿The **pivot** of each **nonzero** row is **1**.
3.  ﻿﻿﻿Each **leading** 1 is the **only** **nonzero** entry in its **column**.

$$\left[
\begin{array}{*{3}{rC}l}
    1 &  & 0  &  &  * & | &  * \\
    0 &  &  1 &  &  * & | &  * \\
    0 &  &  0 &  &  0 & | &  0 \\ 
    0 &  &  0 &  &  0 & | &  0
\end{array}
\right]$$
$$\left[
\begin{array}{*{3}{rC}l}
    0 &  & 1  &  &  * & & 0  &  &  0 & & *  &  &  * & & 0 &| &  * \\
    0 &  &  0 &  &  0 & & 1  &  &  0 & & *  &  &  * & & 0 &| &  * \\
    0 &  &  0 &   &  0 & & 0  &  &  1 & & *  &  &  * & & 0 &| &  * \\ 
    0 &  &  0 &   &  0 & & 0  &  &  0 & & 0  &  &  0 & & 1 &| &  *
\end{array}
\right]$$
