**Shortest** path problem: given a **weighted** graph(see [[Definitions]]) and **vertices** **u** and **v**, we want to find a **path** of **minimum** weight between **u** and **v**
The **weight** of a path is the **sum** of the **weights** of its **edges**

**Applications**: internet packet routing, flight reservations, route planners
![[Screenshot 2023-01-18 at 11.21.22.jpg]]
The **weight** of the path **HNL, LAX, ORD, PVD** is **5147**

# Dijkstra's algorithm
**Input**: a **weighted** graph and a **starting** vertex **s**
**Output**: a map $D[v]$ that gives the **weight** of the **shortest** path between **s** and any **vertex** **V**
**Idea** of the **algorithm**:
- **For** each vertex **v**, keep **track** of:
- a **Boolean** that **describes** whether **v** has been **visited** or not
- a **label** $D[v]$ that **contains** the **weight** of the **best** path we have found **so far**
- **Initially** **no node** has been **visited**, and $D[s] = 0,\,\, D[v] = \infty$ for each v ≠ s
- **Repeat** until **all** vertices have been **visited**:  
	- pick **unvisited** vertex with **least** $D[v]$, and **mark** it **visited**
	- **'relax'** $D[v]$ for **each** edge **(u, v)** **with** weight **w(u, v)** as **follows**:$$D[v]=\{_{d[v] \,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,\,otherwise}^{D[u]+w(u,v)\,\,\,if\,\,D[u]+w(u,v)<D[u]}$$
___
With the **algorithm** **above** we only obtain the **length** of the **path** but not the path **itself**, a **solution** is to keep **track** of the **parent**. 
# Implementation

```java
/* The edges are integers that represent the weight. For simplicity, we assume that the vertices are integers 'O,..., n-1', so that we can use them as indexes into an array. A version with hashmaps is in the book.*/

public static int [ dijkstra (Graph‹Integer, Integer› g, Vertex<Integer› src) {
	int [] res = new int[g.numVertices()];  // the weight of the best path so far
	boolean [] visited = new boolean[g.numVertices()];// Keep track of whether we have visited a vertex

	AdaptablePriorityQueue<Integer, Vertex<Integer>> pq = new HeapAdaptablePriorityQueue<>(); // a PQ with weights as keys, and vertices as values
	Entry<Integer, Vertex<Integer>>[] pqTokens = new Entry<Integer, Vertex<Integer›>[g.numVertices()]; // the locator of each vertex in the PQ
	
	for (Vertex<Integer> v : g.vertices()) {
		res[v.getElement()] = V == src ? O : Integer.MAX VALUE;
		pqTokens[v] = pq.insert(res[v.getElement ()], v);// save entry for edge relaxation
	}
	while(!pg.isEmpty()) {
		Vertex<Integer> u = pq.removeMin().getValue () ;
		visited[u] = true;
		for(Edge<E> e : g.outgoingEdges(u)) {
			Vertex<Integer> v = g.opposite(u, e);
			if (!visited[v] && res[u] + e.getElement() < res [v]) {
				res[v] = res[u] + e.getElement() ;
				pq.replaceKey(pqTokens[v], res[v]) ;
			}
		}
	}
	return res;
}
```
