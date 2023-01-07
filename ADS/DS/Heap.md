A heap is a way to implement a [[Priority queue]] using a [[Binary tree]]. 
Heap **t** with hight **h** has to be a complete binary tree:
* All possible levels of **t** must be full exept possibly the last
* the remaining nodes must occupy the **leftmost** position
___

**Heap-order**. For every position **p** except the root, the key at **p** is **greater** than or **equal** to the key at its **parent**.
The hight of a heap T with n entries height h = **the floor of** log2 n.

### Heap opperations
#### insert(k, v)
To preserve completeness:
insert new node with (k, v) at position p:
* just beyond rightmost node at last level
* as leftmost position of a new level

##### Up-heap bubbling
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

#### removeMin
Entry with smallest key is at the **root**.
**Completness**:
**Cannot** delete root node!
To preserve completeness, replace **root** by **last** node.

##### Downheap bubbling
To preserve heap-order:
**Process position p (initially root of T):**

* **One node** If T has one node, heap-order is satisfied.

* **Multiple nodes**
	- If p has no right child, c is left child;
	- Otherwise, c is child with **minimal** key.
- If k**p** =< k**c**, the heap-order is satisfied.
- If K**p** > K**c**, restore heap-order, i.e. swap entries at p and c.

the time complexity for the down-heap bubble is the same as for the up-heap bubbling



### Heap representations
#### Array heap
Arrays are **suited** for complete binary trees, because complete binary trees are neatly "packed" and leave **no empty spaces** inbetween nodes. 
