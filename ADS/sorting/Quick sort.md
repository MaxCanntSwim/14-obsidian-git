Quick sort uses divide-and-conquer to sort a sequence S with n elements.

In quick sort the hard work is mostly done before the recursive calls.

1. **Divide**:  
    **Base** case 
	    If **S** has **less** than **2** elements), return (**nothing** to do).  
    **Recurrence**
	    If **S** has at least **2** elements), select a **specific** element from **S**, called the **pivot**. E.g. **choose** pivot as the **last** element in **S** (other choices possible: e.g. **middle**).  
	    **Remove** all elements from **S** and **split** them into **3** sequences:  
		    **Sequence L:** elements from S that are **smaller** than pivot.  
		    **Sequence E:** elements from S that are **equal** to pivot. (If all elements in S are unique, then **only** the pivot)  
		    **Sequence R**: elements from S that are **larger** than pivot.
2. **Conquer**: Recursively **sort** sequences **L** and **R**.
3. **Combine**: Put elements back into **S** as follows: **first** all elements of **L**, **then** elements of **E**, **finally** elements of **R**.

At each recursive call, we **recur** on **2** partitions, L and R. 
	In **merge sort**, the two partitions are always **roughly** half of the size of the **original** one.
	In **quick** sort, the size of the **partitions** depends on the choice of **pivot** and the elements in **sequence** **S**.
This will influence the **height** of the recursion tree and **sizes** of subproblem.

# Good case
**Good case**: when **pivot** choice leads to **nearly** **equally** sized partitions.
When the height **h** of the **quick** sort tree is O($\log_2(n)$).
Overall amount or work done at level **i** is **O(n)**:
- **Partition** and combine $2^i$ sequences size $\frac{n}{2^i}$
- Make $2^{i+1}$ recursive calls.

**Good** case **running** time of quick sort isO($n\log_2(n)$). 
**Space** in stack for **recursion** tree is O(log2 n).

# Worst case
If **S** is **sorted**, **last** as **pivot** leads to **unbalanced** partition sizes!
Then the **height** of the quick sort tree is **O(n)**.
The work per level i is proportional to size of largest sequence, **n - i**.
**Worst-case** running **time** of quick sort is **O($n^2$)**. **Space** is **O(n)**.

# Randomized
To guarantee that quick sort is **efficient**, partitions should be **balanced**.
**Deterministic** choice of pivot can lead to **worst-case performance** for certain distributions of the input.
**Randomized** quick sort
	Introduces **randomization** when choosing the **pivot**:
	Instead of always picking the **first, last, or any other fixed element** of S, we choose an element at **random**.

**Time** complexity **analysis**
	The **running** time of quick sort is **proportional** to the number of **comparisons**.
	In each **recursive** call: divide **compares** each element to the **pivot**, so it can **partition** the input sequence into 3.
	How do we **calculate** the total number of comparisons performed by quick sort?
	To count the number of **comparisons**, **either** focus on the **pivot** or the **non-pivot** elements (not both, so we don't count the same comparison twice).

**Non-pivot** elements: per level, a non-pivot element is only compared once to the pivot, or not at all.
**Specifically**, an element **×** is involved as a **non-pivot** in only **one** comparison per level until it either:
- becomes the **pivot** (example: element 31)
- becomes the **only** element (example: 24)
![[Screenshot 2023-01-07 at 15.54.42.jpg]]

# In-Place
Uses element **swapping**, **no subsequences** are created.
A **subsequence** of the input is represented **implicitly** by the **range** given by indices **a and b**.
**Divide** step scans the array simultaneously:
- **forward**, using index **l**, and
- **backward**, using index **r**.
When **I** and **r** cross, division is **complete**, and the algorithm **recurs** on the two subsequences.
**No explicit combine needed.**


a is the start index of the range that is to be sorted
b is the end index of the range that is to be sorted
```java 
/** Sort the subarray S[a..b] inclusive. */
private static <K> void quickSortinPlace(K[ ] S, Comparator <K> comp, int a, int b) {
	if (a >= b) return; //subarray is trivially sorted
	int left = a;
	int right = b-1;
	K pivot = S[b];
	K temp; //temp object used for swapping
	while (left <= right) {
	//scan until reaching value equal or larger than pivot (or right marker) 
		while (left <= right && comp.compare(S[left], pivot) < 0) left++; //scan until reaching value equal or smaller than pivot (or left marker) 
		while (left <= right && comp.compare(S[right], pivot) > 0) right--;
		if (left <= right) {  //indices did not strictly cross
			//so swap values and shrink range
			temp = S[left]; S[left] = S[right]; S(right] = temp;
			left++; right--;
		}
	}
	// put pivot into its final place (currently marked by left index)
	temp = S[left]; S[left] = S[b]; S[b] = temp;
	//make recursive calls
	quickSortInPlace(S, comp, a, left - 1);
	quickSortInPlace(S, comp, left + 1, b);
}
```