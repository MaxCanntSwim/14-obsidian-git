**Invented** by: **A**delson-**V**elski and **L**andis
AVL Trees are the updated version of [[Binary search tree]], with a balancing condition implemented. 

**AVL Balance condition**: the **heights** of the **children** of each node differ by **at most 1**
![[Screenshot 2023-01-16 at 15.34.06.jpg]]
**Note**: we consider **null** references as **leaves** when counting **heights**
___

# Balance
## Search and Repair
-   ﻿﻿use 'ordinary' binary tree **insertion**
-   ﻿﻿this **may** create **unbalanced** nodes, but **only** along the **path** to the **inserted** node  
-    "**search** and **repair**" while **traversing** to the **root**
-   ﻿﻿by "**fixing**" unbalanced **nodes** using "**tri-node restructuring**" along the way
![[Screenshot 2023-01-16 at 15.40.42.jpg]]
# Complexity
The time-complexity of get, put and remove is **O(log n)**
-   ﻿﻿A **tri-node** restructuring takes **O(1)** time
-   ﻿﻿A **get**, **put** or **remove** visits **O(h)** **nodes** and performs **O(h)** **tri-node** restructurings
-   ﻿﻿The **height** of an **AVL** tree of size **n** is **O(log n)**

# Comparison with Hash Tables

Hash tables seem great with **0(1)** (expected) **operations**? Why not use them
always **instead** of **balanced** search trees?

Possible **reasons** **not** to use **hash** tables:
-   ﻿﻿They are **unordered**, they do not support fast operations for taking the **minimal** or **maximal** element, for **in-order traversal**, ...
-   ﻿﻿**Lookup/insert/remove** become **O(n)** with **poor** **hash-functions**
-   ﻿﻿**Periodic** rehashing can be **problematic** in **real-time systems**

Possible **reasons** to use **AVL/red-black** trees:
-   ﻿﻿**Lookup/insert /remove** with **O(log n)** worst case
-   ﻿﻿They are **ordered**, they do support fast operations for taking the **minimal** or **maximal** element, for **in-order traversa**l![[Screenshot 2023-01-16 at 16.20.53.jpg]]