A **multiway** search tree is like a[[Binary search tree]], but in which:

-   ﻿﻿each internal node has **at least two children**
-   ﻿﻿each internal node with **d** children **contains** an ordered list of **k1, ..., kd-1** keys
-   ﻿﻿all keys **k** in the **i-th** child of an internal node satisfy **ki-1 < k < ki**; where k0 =-∞ and kd=∞
![[Screenshot 2023-01-16 at 15.54.35.jpg]]

# (2,4) Trees
A **(2,4) tree** is a **multiway** search tree that **satisfies** the following **properties**:
- **Size** property: every internal node has **at most four children**
- **Depth** property: all **external** nodes have the **same** **depth**
**Depending** on the **number** of children, an **internal** node of a (2,4) tree is called a
**2**-node, **3**-node or **4**-node

## Insert
Perform multiway **search**, and put the **new entry** at the **parent** of the **leaf** (i.e. parent of the null) where the search **ended**
-   ﻿﻿This **preserves** the **depth** property
-   ﻿﻿This may **break** the **size** property by causing an **overflow**:
-   a node may become a **5-node**
![[Screenshot 2023-01-16 at 16.00.27.jpg]]

## Repairing
Repairing an overflow:
• We perform a **split** of the node that became a **5-node**:![[Screenshot 2023-01-16 at 16.01.56.jpg]]
-   ﻿﻿If the **node** was the **root**, the resulting **top** root is the new **root**
-   ﻿﻿**Otherwise**, we **merge** the resulting **top** node with its **parent**
-   ﻿﻿If the **parent** **overflows**, we proceed **recursively**![[Screenshot 2023-01-16 at 16.04.30.jpg]]

# Remove
Recipe for **removing** an **entry**:
-   ﻿﻿Use multiway **search** to find the **entry** that needs to be **removed**
-   ﻿﻿If the **entry** is **not** a node of **level 1** (i.e. its **children are not null**) then:
	-   ﻿﻿Find the **rightmost** (=maximal) **entry** in the **left** subtree  
	-   **Swap** that entry with the **key** that has to be removed
	-   ﻿﻿**Proceed** with the **rightmost** entry
-   ﻿﻿**Remove** the entry, and '**repair**' the tree while **traversing** upwards

**Removal** may break the **size** property by causing an **underflow**: a node may become a **1-node**. To handle an **underflow**, we consider **two cases** (in given order):
- An **adjacent** sibling is a **3-node** or a **4-node**, we then perform a **transfer**:![[Screenshot 2023-01-16 at 16.10.52.jpg]]
- An adjacent sibling is a **2-node**, we then perform a **fusion**:![[Screenshot 2023-01-16 at 16.11.02.jpg]]
## Examples

![[Screenshot 2023-01-16 at 16.12.12.jpg]]
![[Screenshot 2023-01-16 at 16.13.00.jpg]]

# Complexity
The time-complexity of **get, put and remove** is **O(log n)**
-   ﻿﻿The height of a (2,4) tree of size **n** is **O(log n)** (see proof in the book)
-   ﻿﻿A **split**, **transfer**, or **fusion** take **O(1)** time
-   ﻿﻿A **get, put or remove** visits **O(h)** nodes