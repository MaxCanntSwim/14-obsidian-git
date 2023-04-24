Trees can also be [[Data Structures]], the implementation of a tree is very similar to the implementation of a [[Linked list]]. 

[[1105 ADS/DS/Trees/Terminology]] [[Traversals]] 

Tags: #dataStructure #Tree #implementations
___
# Trees
## Linked structure for trees
Tree node represented by object storing:
* Element
* Parent node
* Sequence of children nodes

Node class implements Position ADT.
```java
public class LinkedTree<E>
			implements Tree<E> {
	protected static class Node<E>
			implements Position<E> {
		private E element;
		private Node<E> parent;
		private ?????<Node<E>> children;
	// ...
	}
	protected Node<E> root;
}
```
The ????? can either be:
* [[Array]] if number of children is fixed when a node is created.
- **Dynamic array** or [[Linked list]] if the number of children can change

# Binary Trees
## Linked structure for binary trees
Binary tree node is an object storing
* Element
* Parent node
* Left child node
* Right child node

Node objects implement the Position ADT
```java
public class LinkedBinaryTree<E> implements Tree<E> {
	protected static class Node<E> implements Position<E> {
		private E element;
		private Node<E> parent;
		private Node<E> left;
		private Node<E> right;
		// ...
	}
	protected Node<E> root;
}
```

## Array-based binary trees
Nodes are stored in an array.
Node v is stored at index f (v), given by:
| f(v) = 0            | if v is the root             |
| ------------------- | ---------------------------- |
| f(v) = 2 • f(p) + 1 | if v is the left child of p  |
| f(v) = 2 • f(p) + 2 | if v is the right child of p |

# Linked tree vs. array for binary trees
**Linked tree implementation**
- O (n) space (where n is the size of the tree)
- 0 (1) operations for insertion/removal (see book, or previous lectures)

**Array-based implementation**
- 0(2") / 0 (2 ) space. Exponential!
- Many update operations require changing the entire array.

**In summary**: array-based is only efficient for binary trees of particular shape, where only specific operations are performed (we'll cover an example in the next lecture: heaps).





