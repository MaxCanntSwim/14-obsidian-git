**Execution** of merge sort depicted by its **recursion** tree.
Each node represents a **recursive** call of merge sort with:
- **unsorted** sequence before the execution and its partition (**left**);
- **sorted** sequence at the end of the execution (**right**).
**Root** contains initial call, and **final** result.
**Leaves** are calls on sequences of size **1**.
![[Screenshot 2023-01-07 at 15.06.31.jpg]]

The height h of the merge sort recursion tree is 0 (log2 n).
• At each call, divide, make 2 recursive calls: recursion tree is a complete binary tree.
The total amount or work done by all the calls at level i is always 0 (n):
- Partition and merge $2^i$ sequences of approximately size $\frac{n}{2^i}$
- Make $2^{i+1}$ recursive calls.
Total running time of merge sort is O($n\log_2(n)$).

```java
// Merge contents of arrays S1 and S2 into properly sized array S.

public static <K> void merge (K[] S1, K[] S2, K[] S, Comparator<K> comp) {
	int i = 0, j = 0;
	while (i + j < s.length) {
		// if no more elements in S2, or still elements in S1 and next element in S1 smaller than next element in S2
		if (j == s2.length i < si.length && comp.compare(Sl[i], S2[jj) < 0))
			S[i+jl = S1[i++];  // copy ith element of S1 into S and increment i
		else
			S[i+jl = S2[j++];  // copy jth element of S2 into S and increment j
  }
}
// Merge sort elements in array S.
public static <K> void mergeSort (K[] S, Comparator<K> comp) {
	int n = S.length;
	if (n < 2) return; // base case, array is trivially sorted
	// divide
	int mid = n/2;
	K[J S1 = Arrays. copyOfRange (S, 0, mid);  // copy of first half
	K[J S2 = Arrays. copyOfRange (S, mid, n);  // copy of second half
	// conquer (with recursion)
	mergeSort (S1, comp); 
	mergeSort ( S2, comp);
	// merge results
	merge (Sl, S2, S, comp); // merge sorted halves back into original
}
```