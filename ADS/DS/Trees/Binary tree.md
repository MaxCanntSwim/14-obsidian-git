**Binary tree**: a tree with the following properties:
- Each internal node has at most two children (either 1 or 2).
- The children of a node are an ordered pair: left child, right child.
- **Max number of nodes**: ${2}^{h+1}-1$
Tags: #dataStructure #Tree
___

# Terminology
* **Proper binary tree**: tree in which every node has either zero or two children.
* **In-order [[Traversals]]**: the node is visited **after** the left child and **before** the right child
```java
public void inorder (Position<E> p) {
	if(left(p) != null) inorder(left(p));
	visit(p);
	if(right (p) != null) inorder (right (p));
}
```
