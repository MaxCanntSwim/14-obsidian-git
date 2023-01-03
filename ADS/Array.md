Arrays contain data in a defined size and order structure with direct acces to all elements in the array using indexes. 
___

### Opperations
Inserting and removing elements with an array takes $O(n)$ time and $O(1)$ space. 

### Insertion sort
```
InsertionSort(a)
	for k from 1 to n-1 do
	insert a[k] at its proper location within a[0], a[1], ..., a[k-1]
```
In-place algorithm: modifies the array directly (no new array to store result).
Implicit output: array is passed by reference, no need for explicit return.
![[Screenshot 2023-01-03 at 13.46.30.jpg]]
The time complexity is $O(n^2)$ and the space is $O(1)$. 

### Equality
| Tests for equality                                                      | What is compared?          | Result?          | Time? |
| ----------------------------------------------------------------------- | -------------------------- | ---------------- | ----- |
| scores1 == scores2                                                      | array variable (reference) | false            | 0(1)  |
| scores1.equals (scores2 )                                               | array variable (reference) | false            | 0(1)  |
| (defined for Object, compares\ with == by default; should be overriden) |                            |                  |       |
| java.utils.Arrays.equals (scores1, scores2)                             | array's elements           | true |0(n)|
|(loops over k to compare a[k] against b[k]: uses a[k] == b[k] for primitives, calls a[k].equals(b[k]) for objects)|                            |                  |       |

### Clone
