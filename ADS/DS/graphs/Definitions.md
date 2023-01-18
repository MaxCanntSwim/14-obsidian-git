A [[Graph]] is a tuple (V, E), where:
-   ﻿﻿**V** is a **set** of nodes, called **vertices**
-   ﻿**E** is a **collection** of pairs of vertices, called **edges**
# Labeled graphs
Vertices and/or edges store data
## Example
-   ﻿﻿vertices represent airports, labeled with their city
-   ﻿﻿edges represent distances
![[Screenshot 2023-01-18 at 11.21.22.jpg]]
# Undirected versus directed
* An **undirected graph** is a graph in which all edges are **unordered** pairs
* A **directed graph** is a graph in which all edges are **ordered** pairs
* A **mixed graph** is a graph in which has both edges that are **unordered** pairs and edges that are **ordered** pairs

# Terminology
- **End vertices**  
    The two vertices joined by an **edge**
	-   ﻿﻿Origin/destination (directed)
- **Adjacent vertices**  
    Vertices are **adjacent** if an edge **connects** them
- **Edges incident** on a vertex **v**  
    The edges whose end points include **v**
	- ﻿﻿**incoming** / **outgoing** edges (directed)
- **Parallel edges**  
    Edges that have the same end vertices
- **Self-loop**  
    An edge whose end vertices coincide
- **Degree of a vertex v** (denoted deg (V))  
    The number of incident edges of a vertex
	- indegree / outdegree (directed)
- A **simple graph** is a graph **without** parallel **edges** and **self-loops**, and can be defined as a **tuple** **(V, E)**, where:
	- **V** is a set of nodes, called vertices
	- **E** is a collection set of pairs of vertices, called edge

* ﻿A **path** is a **sequence** of **alternating** vertices and **edges** that:
	- **begins** with a **vertex**,
	- **ends** with a **vertex**,
	- **each** **edge** is incident to its **predecessor** and **successor**
- A **simple** path is a path in which all **vertices** are **distinct**
- A **directed** path is a path such that **all** **edges** are **directed** and are **traversed** **along their direction**

- A **cycle** is a **path** that **starts** and **ends** at the same **vertex**, and that includes **at least one edge**
- A **simple** cycle is a cycle in which all **vertices** and **edges** are **distinct**
- A **directed** cycle is a cycle such that **all edges** are **directed** and are **traversed** along their **direction**

* A **subgraph** **S** of a graph **G** is a graph such that:
	- The **vertices** of **S** are a subset of the **vertices** of **G**
	- The **edges** of **S** are a subset of the **edges** of **G**
- A **spanning subgraph** of a graph **G** is a **subgraph** that contains all the **vertices** of **G**

- Vertex **U** **reaches** vertex **V** if there **exists** a (directed) **path** from **U** to **V**
- A **graph** is **connected** if there is a **path** between every **pair** of **vertices**
- A directed graph is **strongly connected** if there is a **directed** **path** between **every** **pair** of vertices
- The **connected components** are the **maximal** connected **subgraphs** of a **graph**