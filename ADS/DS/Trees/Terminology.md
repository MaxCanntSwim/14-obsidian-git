Abstract model of a hierarchical structure.
Tags: #dataStructure #Tree #Terms
___

Examples:
- Tree of languages, tree of life (evolution)
- Inheritance between user-defined classes in Java

A tree comprises **nodes** and **edges**.
Every **edge** denotes a hierarchical, parent-child relation between two **nodes**.
![[Screenshot 2023-01-04 at 15.18.35.jpg]]
Relationships between nodes
- **Parent** of x: node y at the other end of the unique upward edge from x (B is the parent of E).
- **Child** of x: node y at lower end of an edge from x (K is a child of F)
- **Sibling** of x: any node y other than × with same parent of x (G is sibling of H)
- **Ancestor** of x: any node y in the unique upward path from × to the root, including x (ancestors of K: A,B, F, K)
- **Descendant** of x: any node y in a downward path from x to the leaves, including * (descendants of B: B,E, F, I,J, K)
- **Root**: node without parent (A)
- **Internal nodes**: nodes with at least one child (B,C, F)
- **External nodes (leaves)**: without children (D,E, G, H, I,J,K)
- **Depth** of node x: number of ancestors of x other than x itself
```java
public int depth (Position<E> p) {
	if (isRoot(p))
		return 0;
	else
		return 1 + depth (parent (p));
}
```

**Height of tree:**
	maximum depth of all of its nodes, if non-empty tree **or** zero, if tree is empty

```java
public int height (Position<E> p) {
	int h = 0;              // base case (p is leaf)
	for (Position<E> c : children(p))
		h = Math.max (h, 1 + height (c));
	return h;
}
```

**children(p)** visits every node in subtree of p once: O(n) **height(c)** called recursively, only once per node from top to bottom: O(n)