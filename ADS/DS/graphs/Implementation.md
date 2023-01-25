See [[Definitions]]

# Topological sorting
```java
topologicalSort (Graph G = (V,E) )
	List<Vertex> topo = new list
	Stack<Vertex> ready = new stack
	Map<Vertex, Integer> inCount = new map
	
	for Vertex v : V)
		inCount.put (v, v. inDegree ()) if (inCount.get (v) == 0)
		ready.push (v)
		
	while (!ready is not empty)
		Vertex u = ready. pop ()
		topo.add (u)
		for (Edge e in u.outgoingEdges ())
			Vertex v = u.opposite (e)
			inCount. put (v, inCount. get (v) -1)
			if(inCount.get (v) == 0)
				ready.push (v)
return topo
```

# Interface for graph
```java
interface Vertex<V> {
	public V getElement ();
}

interface Edge<E> {
	public E getElement();
}
```

```java
interface Graph<V,E> {
	public int numVertices ();
	public Iterable<Vertex<V›> vertices ();
	
	public int numEdges ();
	public Iterable<Edge<E>> edges ();
	
	public Edge<E> getEdge (Vertex<V> u, Vertex<V> v);
	public Vertex‹V> opposite (Vertex‹V> v, Edge<E> e);
	
	// for an undirected graph, both return the same
	public Iterable<Edge<E>> outgoingEdges (Vertex<V> v);
	public Iterable<Edge<E>> incomingEdges (Vertex<V> v);
	
	public Vertex<V> insertVertex (V x);
	public Edge<E> insertEdge (Vertex<V> u, Vertex<V> v, E x) ;
	public void removeVertex (Vertex<V> v);
	public void removeEdge (Edge<E> e);
}
```

# Edge list
```java
class EdgeList<V, E> implements Graph‹V, E> {
	class InnerVertex<V> implements Vertex<V> {
		private V elem;
		private Position <InnerVertex<V>> pos;
	}
	
	class InnerEdge<V, E> implements Edge<E> {
		private E elem;
		private InnerVertex<V> begin;
		private InnerVertex<V> end;
		private Position <InnerEdge<V,E›> pos;
	}
	
	private LinkedPositionalList<InnerVertex<V›>vertices;
	private LinkedPositionalList <InnerEdge<V,E>> edges;
	
	//...
}
```
![[Screenshot 2023-01-18 at 12.03.43.jpg]]

# Adjacency list structure
```java
class AdjacencyList<V, E> implements Graph<V, E> {
	class InnerVertex‹V> implements Vertex‹V> {
	private V elem;
	private Position <InnerVertex<V›> pos;
	private LinkedPositionalList
		<InnerEdge<V,E›› outgoing, incoming;
	}
	
	class InnerEdge<V,E> implements Edge<E> {
		private E elem;
		private InnerVertex<V> begin;
		private InnerVertex<V> end;
		private Position <InnerEdge<V,E>> pos;
	}
	
	private LinkedPositionalList <InnerVertex<V›> vertices;
	private LinkedPositionalList <InnerEdge<V,E>> edges;
	//...
}
```
![[Screenshot 2023-01-18 at 12.05.21.jpg]]

# Adiacency map structure
```java
class AdjacencyMap<V,E> implements Graph<V, E> {
	class InnerVertex‹V> implements Vertex‹v> {
		private V elem;
		private Position <InnerVertex<V>> pos;
		private Map
			<Vertex<V>, InnerEdge<V,E›› outgoing, incoming;
	}
	
	class InnerEdge<V,E› implements Edge<E> {
		private E elem;
		private InnerVertex<V> begin;
		private InnerVertex<V> end;
		private Position <InnerEdge<V,E>> pos;
	}
	
	private LinkedPositionalList <InnerVertex<V›> vertices;
	private LinkedPositionalList ‹InnerEdge<V,E>> edges;
	
	//...
}
```
![[Screenshot 2023-01-18 at 12.08.37.jpg]]

# Adiacency matrix structure
```java
class AdjacencyMatrix<V,E> implements Graph<V, E> {
	// ...
	
	private InnerEdge<V, E> [] [] matrix;
	// ...
}
```
![[Screenshot 2023-01-18 at 12.12.06.jpg]]