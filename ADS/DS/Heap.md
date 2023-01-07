A heap is a way to implement a [[Priority queue]] using a [[Binary tree]]. 
Heap **t** with hight **h** has to be a complete binary tree:
* All possible levels of **t** must be full exept possibly the last
* the remaining nodes must occupy the **leftmost** position
___

**Heap-order**. For every position **p** except the root, the key at **p** is **greater** than or **equal** to the key at its **parent**.
The hight of a heap T with n entries height h = **the floor of** log2 n.

# Opperations
## insert(k, v)
To preserve completeness:
insert new node with (k, v) at position p:
* just beyond rightmost node at last level
* as leftmost position of a new level

### Up-heap bubbling
**Starts at the bottom.**
Each **pairwise swap** between a node and its parent either:
- **Reestablishes** heap-order
- **Propagates** the issue one level up

Worst-case:
- Entry (or key) moves all the way up to root.
- Number of moves is proportional to the height h of heap (recall that h = floor of log2 n).
- $O(log_2n)$

process position **p**: 
To preserve **heap-order**:
if **p** is the root of **T**, heap-order is **satisfied**.

Otherwise, compare key at **p** to that of **p**'s parent, denoted as **q**:
- If K**p** ≥ K**q**, heap-order is **satisfied**.
- If K**p** < k**q**, restore heap-order by **swapping**.

## removeMin
Entry with smallest key is at the **root**.
**Completness**:
**Cannot** delete root node!
To preserve completeness, replace **root** by **last** node.

### Downheap bubbling
To preserve heap-order:
**Process position p (initially root of T):**

* **One node** If T has one node, heap-order is satisfied.

* **Multiple nodes**
	- If p has no right child, c is left child;
	- Otherwise, c is child with **minimal** key.
- If k**p** =< k**c**, the heap-order is satisfied.
- If K**p** > K**c**, restore heap-order, i.e. swap entries at p and c.

the time complexity for the down-heap bubble is the same as for the up-heap bubbling



# Representations
## Array heap
Arrays are **suited** for complete binary trees, because complete binary trees are neatly "packed" and leave **no empty spaces** inbetween nodes. 
For a tree of size **n**, elements have **contiguous** indices in the range (0, ...,**n - 1**}.
The tree traversel using the **indexes** is a breadth-first. 

Accessing **parent** or **chidren**:
For position with index **p**:
* Left child index 2**p** + 1
* Right child index 2**p** + 2

Additional properties:
Levels are kept together.
Internal nodes leftmost
{${0,...,\left \lceil{\frac{n-1}{2}}\right\rceil-1}$}
Leaf nodes rightmost
{${\left \lfloor{\frac{n-1}{2}}\right\rfloor,...,n-1}$}

## Linked tree
the linked tree implementation is almost the same as the implementation for [[Binary tree]]. 

# Comparison array LT
Methods **insert** and **removeMin** relv on:
- locating the **last** position;
- **local** **swapping** between parent and child

**Local swapping:** 0(1) per **swap**, O(log n) in **total** (both array and linked tree).
**Accessing last position**: 
* In **array**, always index n - 1, thus access is **0(1)**.
* In **linked tree**, requires traversal in **0(log n)**.

## Linked-tree: access last position
Solutions to access last position:
**Extra** reference + updating 
*(creativity: try book exercise C-9.30)
- Keep extra reference to **last** node.
- **Update** reference after operations **insert** / **remove** in **0(log n)** time.

**No** reference, find last **on-demand** 
*(creativity: book exercise C-9.32)
- Find **last** node when needed using an **0(logz n)** time algorithm.

### Finding the last nodes using passes
If index is encoded in 16-bit integer (Java short):
00000000 00000**101**

Index of **last** node:
$$n-2^{\left \lfloor{log_2n}\right\rfloor}$$
Path: take $\left \lfloor{log_2n}\right\rfloor$ rightmost bits
00000000 00000**101**

Index of a new node: 
$$n+1-2^{\left \lfloor{log_2n}\right\rfloor}$$
Path of **new** node:
${\left \lfloor{log_2(n+1)}\right\rfloor}$ **rightmost** bits
00000000 00000**110**

Path of **parent**:
${\left \lfloor{log_2(n+1)}\right\rfloor}$ rightmost but **one** bits
00000000 00000**11**0

# Construction
## Keys not known
Building a heap with **n** keys.
Keys **not** known in advance:
- Start with **empty** heap.
- Call **insert** method for every new key.  
			 0(n $\log_2n$)

## Keys known
### LT heap
**Bottom-up heap merging** (idea)
(merging idea as prelude **for construction only**)
**Input**: two heaps and new key **k**.
Create **new** heap:
- Root node storing **k**.
- Two given heaps as **subtrees**.
**Down-heap bubbling to restore heap-order property.**

Building a heap with **n** keys.
Keys **known** beforehand:
Build heap using **bottom-up** approach.
* At iteration **i**, pairs of heaps with $2^i - 1$
* keys are **merged** into heaps with $2^{i+1} - 1$.

Bottom-up heap construction takes **0(n)** time.
**Faster** than construction by entry insertion in O($\log_2(n+1)$ time.
	**Bottom up heap construction only works on linked tree heaps**

```java
Java code 9.10, page 350

/**
* Constructor of array-based heap with keys ks and values vs.
*/
public HeapPriorityQueue (K[] ks, V[] vs) {
	super ();   // initialize array variable heap
	for (int j = 0; j < Math.min(ks.length, vs.length); j++) // iterate over keys and values
		heap. add (new PQEntry<>(keys[j], values [j]));   //add all entries to the heap
	heapify();   // call heapify to bottom-up restore heap-order
}
/**
*    Heapify: Restores heap-order property in a bottom-up fashion.
*    Starting from the parent of the rightmost position (last level doesn't need
**   down-heap bubbling), and traverses backwards through all indices up to 0 (root).
**   For each node, performs down-heap bubbling to restore the heap-order property.
**/
protected void heapify() {
	int startIndex = parent(size ( )-1);
	for (int j = startIndex; j >= 0; j--)
		downheap (j);
}
```