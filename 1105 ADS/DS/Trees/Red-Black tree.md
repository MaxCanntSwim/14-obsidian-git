A **red-black tree** is a [[Binary search tree]] with nodes **colored** red and black that **enjoys**:
-   ﻿﻿**Root** property: the root is **black**
-   ﻿﻿**External** property: every **leaf** (i.e. null) is **black**
-   ﻿﻿**Red** property: the **children** of a **red** node are **black**
-   ﻿﻿**Depth** property: all **external** nodes have the **same** **black** depth, **defined** as the **number** of **proper** ancestors that are **black**
![[Screenshot 2023-01-16 at 16.26.04.jpg]]
# Insert
Perform binary **search**, and put the **new red entry** at the **leaf** (i.e. the **null**) where the **search** **ended**, and **add** two **black** leaves to the just created **entry**
-   ﻿﻿This **preserves** the **depth** property
-   ﻿﻿This may **break** the **red** property.
-   **two** red nodes may be **above** each other
![[Screenshot 2023-01-16 at 16.27.43.jpg]]
This **breaks** the **red property**.
## Examples
![[Screenshot 2023-01-16 at 16.28.43.jpg]]![[Screenshot 2023-01-16 at 16.30.25.jpg]]

# Remove
Recipe for **removing** an **entry**:
-   ﻿﻿Use binary **search** to find the **entry** that needs to be **removed**
-   ﻿﻿If the **entry** is **not** a node of **level 1** (i.e. its **children are not null**) then:
	-   ﻿﻿Find the **rightmost** (=maximal) **entry** in the **left** subtree  
	-   **Swap** that entry with the **key** that has to be removed
	-   ﻿﻿**Proceed** with the **rightmost** entry
-   ﻿﻿**Remove** the entry, and '**repair**' the tree while **traversing** upwards
## Examples
![[Screenshot 2023-01-16 at 16.32.49.jpg]]
11 used to be located as the 10 and 10 used to be the left child of 11
![[Screenshot 2023-01-16 at 16.33.59.jpg]]![[Screenshot 2023-01-16 at 16.36.28.jpg]]

# Complexity
The time-complexity of **get, put and remove** is **O(log n)**
-   ﻿﻿The **height** of a red-black tree of size **n** is **O(log n)** (see proof in the book)
-   ﻿﻿**Recoloring** operations take **O (1)** time
-   ﻿﻿A **get, put or remove** visits **O(h)** nodes

# Red-black trees versus AVL trees
Both have **O(log n)** time complexity for **get, put and remove**, so what is the **difference**?
**AVL** trees are better **balanced**, hence:
-   ﻿﻿**get** is **faster** for **AVL** trees
-   ﻿﻿**put** and **remove** of a **red-black tree** is faster, because red-black trees require **less** **re-balancing**

# (2,4) to red-black
![[Screenshot 2023-01-27 at 16.11.25.jpg]]

