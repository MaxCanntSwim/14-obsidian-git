A **binary search tree** is a [[Binary tree]] in which each **node** with key **k** satisfies the following **properties**:
-   ﻿﻿**Keys** stored in the **left** **subtree** are **less** than **k**
-   ﻿﻿**Keys** stored in the **right subtree** are **greater** than **k**
___

# Search/get
**Binary search**: starting from the **root**, **compare** search key with **key** at node
-   ﻿﻿**smaller**: search **left**
-   ﻿﻿**equal**: success
-   ﻿﻿**greater**: search **right**

Example: search for **40**:![[Screenshot 2023-01-16 at 15.09.33.jpg]]

# Put/insert


Use find to find the position to insert:
-   ﻿﻿**not null**: key is **already** in the tree
-   ﻿﻿**null**: **expand** to actual node

# Remove
**Easy case**: **one** of the children of the node is **null**
- **remove** node and **replace** it by the **child**

The **difficult** **case**: both children of the node are **not** **null**
- find the **maximum** node in the **left** **child**
- **replace** the to be **removed** node by the **maximum** node
- **recursively** proceed to **remove** the **maximum** node

# Complexity
since we are traversing the tree and doing something on every level **h**, the time complexity of the binaty search is **O(h)**. the best case is where the height **h**=**log(n)**, but if the inserted sequenve was sorted or inversel sorted, this will lead to a tree where the height **h**=**n**.  ![[Screenshot 2023-01-16 at 15.24.47.jpg]]

require a **balance** **condition** that:
-   ﻿﻿**ensures** the depth is **O(log n)**
-   ﻿﻿can be **maintained** in O(log n) **time** for each **put** and **remove**

