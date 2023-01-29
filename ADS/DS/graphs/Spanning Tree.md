A Tree is an undirected graph G such that:
- G is connected
- G has no cycles
A spanning tree is a spanning subgraph that is a tree
A **spanning subgraph** of a graph **G** is a **subgraph** that contains all the **vertices** of **G** and a **subset** of the edges. 
# minimum spanning tree(MST)
**Given** an **undirected**, **weighted** graph **G**, we are interested in finding a spanning tree **T** of **G** that **minimises** the **sum**. 

# Kruskal's algorithm
Idea:

-   ﻿﻿Maintain a **partition** of the **vertices** into clusters
	-   ﻿﻿**Initially**, each vertex forms a **single** **cluster**
	-   ﻿﻿**Each** cluster contains a minimum spanning tree **(MST)**
-   ﻿﻿**Pick** an **edge(u, v)** with **smallest** weight that is **not** part of the **MST** yet
	-   ﻿﻿**If** the clusters of **u** and **v** are **different**: **merge** both using the **edge (u, v)**
	-   ﻿﻿**Otherwise**: remove the edge
-   ﻿﻿**Repeat** until we have obtained a **single** cluster

**Implemented** using a **priority** queue that **stores** the edges **outside** clusters
-   ﻿﻿Keys: **weights**
-   ﻿﻿Elements: **edges**