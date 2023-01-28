Sorting a sequence **S** with a priority queue.
Algorithm PQ-Sort(**S**, **C**) 
	**Input** sequence **S**, comparator **C** for elements of **S**
	**Output** sequence **S** in non-decreasing order based on **C**
___

# Priority queue
These implemenatations use a [[Priority queue]]. 
## Selection sort
Sorting **n** elements.
Unsorted list priority queue **P**.

Phase 1: **insertion**
	Insertion into priority queue.
	An insertion is O(1), n insertions **O(n)**.
Phase 2: removal
	Repeated **removal** of **minimal** key from P.
	Runtime of each removeMin is proportional to the size of P:
	**O($n^2$)**

## Insertion sort
Sorting **n** elements.
Unsorted list priority queue **P**.

Phase 1: **insertion**
	Repeated **insertions** into priority queue **P**.
	**Entries** inserted at final **sorted** position.
	Runtime of **insert** proportional to size of **P**:
		**O($n^2$)**
Phase 2: **removal**
	**Repeated** removal of **minimal** key from **P**.
	Each removal is **O (1)**, n removals **O(n)**.

## Space complexity
Space complexity:
	Depends on implementation.
## LL
If S is **linked list** whose size is modified by insert/remove.
	The total number of elements in **S** and **P** combined is always equal to the number of e**lements originally** in **S** (given as input).
	Then space is **0(1).**
## AR
If **S** is an array of capacity **n** (or any linked list that **does not shrink**, elements are **overriden**).
	Then we need **O(n)** space for **P**.

# In-place
In-place sort **does not** use an external datastructure. 
**Selection** and **insertion** sort can be implemented in-place.
**In-place** sorting:
	Only **O(1)** space used (in addition to the sequence being sorted).
Only O(1) space used (in addition to the sequence being sorted).
**A portion** of the **input** sequence itself **serves** as the **priority queue** P.

## Insertion sort
In-place **insertion** sort:
Iterate **left to right**, one index **i** at a time (where i = **1** up to i = **n - 1**).
- Iterate backwards within 0, ..., i - 1:
- If element **larger** than the element at index **i**, **shift** a position to the **right**.
- **Insert** element at its **correct** position.
```java
public static void insertionSort(int[] elements) {
	if(elements.length < 2) return;
	for(int i = 1; i < elements.length; i++){
		int j = i - 1;
		int temp = elements[i];
		while(j >= 0&&temp < elements[j]){
			elements[j+1] = elements[j];
			j--;
		}
		elements[j+1] = temp;
	}
}
```

## Selection sort
In-place selection sort:
Iterate **left to right,** one index **i** at a time (where i = **0** up to i = **n - 2**).
- Find index **m** of **minimum** element within **indexes** i, ...,n - 1.
- Swap elements at **i** and **m**.
```java
public static void selectionSort(int[] elements) {
	if(elements.length < 2) return;
	for(int i = 0; i < elements.length;i++){
		int j = i;
		int loc = j;
		while(j < elements.length){
			if(elements[j] < elements[loc]) {
				loc = j;
			}
			j++;
		}
		int temp = elements[loc];
		elements[loc] = elements[i];
		elements[i] = temp;
	}
}
```