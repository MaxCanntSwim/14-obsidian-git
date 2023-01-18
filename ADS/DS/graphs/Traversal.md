A **traversal** is a **systematic** procedure for **exploring** a graph by **examining** all of its **vertices** and **edges**(see [[Definitions]])

**Applications**:
- Computing a path between two vertices, or reporting that no such path exists
- Testing whether a graph is connected
- Computing a spanning tree of a graph
- Computing the connected components of a graph
- Identifying a cycle in a graph, or reporting that cycles exist
___
# Depth-first search(DFS)
```java
public static <V,E> void depthfirst (Graph<V,E> g, Vertex<V> u, Set<Vertex<V>> known) {
	visit (u):
	known.add (u); // u has been discovered
	for (Edge<E> e : g.outgoingEdges (u)) {
		Vertex<V> v = g.opposite (u, e);
		// check whether v has already been discovered
		if (!known.contains (v)) {
			// recursively explore from v
			depthfirst (g, V, known);
		}
	}
}
```

# Breath-first search(BFS)
```java
static <V,E> void breadthfirst (Graph‹V,E> g, Vertex<V> s) {
	// vertices that we have already visited
	Set<Vertex<V>> known = new Set ();
	// breadth first queue
	Queue<Position<E>> g = new Queue () ; q. enqueue (s) ;
	known.add (s);
	while (!g.isEmpty()) {
		Vertex<V> u = q. dequeue () ;
		visit (u);
		for (Edge<E> e : g.outgoingEdges(u)) {
			Vertex‹V> v = g.opposite(u, e) ;
			if (!known.contains(v)){
				q.enqueue(v);
				known.add(v);
			}
		}
	}
}
```

# Counting connected components using DFS
```java
public static int connectedComponents(Graph<V,E> g) {
	Set<Vertex<V>> known = new Set );
	int num = 0;
	for Vertex<V> u : g.vertices ()) {
		if (!known.contains (u)) {
			num++;
			depthfirst (g, u, known);
		}
	}
	return num;
}
```

# Path finding using DFS
```java
public static boolean pathBetween (Graph<V,E> g,
	Vertex<V> ul, Vertex<V> u2,
	Set<Vertex<V>> known) {
	known.add (ul);
	
	if (ul == u2) return true;
	
	for (Edge<E> e : g.outgoingEdges (ul)) {
		Vertex<V> v = g.opposite (ul, e) ;
		if (!known.contains (v)) {
			if (pathBetween (g, v, u2, known))
				return true;
		}
	}
	return false;
}
```

# Time complexity of DFS
Assume we are given a graph G = (V, E) with n vertices and m edges:
- n calls to add
- n calls to outgoingEdges
- $\sum_{v∈V}$ deg(V) calls to opposite
- $\sum_{v∈V}$ deg(v) calls to  
    contains