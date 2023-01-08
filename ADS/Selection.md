Selection problem.
**Select** the **k**th **smallest** element from an **unsorted** collection of **n** **comparable** elements. Also called **order statistics** *(selecting an element with a given rank)*.
For instance:
	1st smallest (minimum)    rank 1
	n/2 th smallest (median)  n/2
	nth smallest (maximum)   rank n
Solutions? Complexity?

**Solution 1**: use [[Sorting algorithms]], **pick** element at index **k - 1** in sorted sequence. Takes **O(n log n)** time.

**Solution 2**: Build [[Heap]] with **n** elements in **0(n)** time, **remove** **k** elements. Takes **O(n + k log n)** time.

**Slow**, since we can b the selection problem for **k = 1, k = n, and other values of k in 0 (n) time**.

Can we **achieve** **O(n)** running time **for all** values of **k**?

**For instance**, finding the median, where k = n/2.

# Randomized quick-select
Algorithm quickSelect(S, k)
	**Input**: Sequence **S** of **n** elements, and an **integer** k € {1, ..., n}
	**Output**: The **k**th smallest element of **S** 
	**If** n == 1 **then**
		**return** the (**first**) element of **S**
	Pick a **random** (**pivot**) element **x** of **S** and divide **S** into **three** sequences:
		**L**, storing the elements in **S** less than **x**
		**E**, storing the elements in **S** equal to **x**
		**R**, storing the elements in **S** greater than **x**
	**If** k < |L| **then**
		**return** quickSelect(L, k) 
		**else** **if** k ≤ |L| + |E| **then**
			**return** x
		**else** 
			**return** quickSelect(R, k - |L| - |E|)

## In-place
```java
public static int selectInPlace (int[] array, int k) {
	return selectInPlace (array, 0, array.length-1, k-1);
}

private static int selectInPlace (int[] array, int left, int right, int i) { //i index of k-th
	if (left == right)
		return array[left]; // if there's only one element, return that element
	
	// select random pivot index between left and right (same as quick sort)
	int pivotIdx = randomPivot (left, right);
	// swap pivot with last element, partition, assign updated pivot index (same as quick sort)
	pivotIdx = partition (array, left, right, pivotIdx);

	if (i == pivotIdx)
		return array il;          // k-th element is the pivot
	else if (i < pivotIdx)
		return selectInPlace(array, left, pivotIdx - 1, i); // k-th element is the pivot
	else
		return selectInPlace (array, pivotId + 1, right, i); // k-th element is >= pivot
}
```

## complexity
**Best case:**
**Pivot** choice always results in **equally** sized partitions (sizes of approximately **1/2 each)**. **time** complexity is **0 (n)**. **Space** is **0(log2 n)** if in-place, since we need space for the **stack frames** (given by height of recursion tree).

**Worst-case:**
**Pivot** choice always results in **one** partition of size **0**, and one partition of size **n - 1.** Number of comparisons is n + (n - 1) + (n - 2)+.. + 1. **Gauss**' sum, so **time** complexity is 0 ($n^2$). **Space** is **O(n),** since we need space for the stack frames and height of recursion tree is proportional to **n**.

Expected time: **O(n)**