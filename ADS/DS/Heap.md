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
process position p: 
To preserve **heap-order**:
if p is the root of T, heap-order is satisfied.

Otherwise, compare key at p to that of p's parent, denoted as q:
- If Kp ≥ Kg, heap-order is satisfied.
- If Kp < kg, restore heap-order by swapping.