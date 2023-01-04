# Depth first
## Pre-order
pre-order, visit Node **before** its children 
```java
public void preorder (Position<E> p) { 
	visit(p); // visit performs some operation at the node, e.g. print its element
	for (Position<E> c : children(p))
		preorder(c);
}
```

## Post-order
Post-order, visit node **after** its children
```java
public void preorder (Position<E> p) { 
	for (Position<E> c : children(p))
		preorder(c);
	visit(p); // visit performs some operation at the node, e.g. print its element
}
```


# Breath first
Visit nodes **per level (depth)**
```java
public void breadthfirst (Position<E> p) {
	Queue<Position<E>> q = new Queue();
	q.enqueue(p);
	while (!q.isEmpty()) {
		Position<E> p = q.dequeue() ;
		visit(p);
		for (Position<E> c: children(p))
			q.enqueue(c) ;
	}
}
```

