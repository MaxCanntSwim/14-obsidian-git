# Key-based sorting
Let **S** be a sequence of **n** (key, element) items.
Keys are (**small**) integers in the range **{0, ...,N - 1}**.
**Bucket Sort:**
**No need for comparisons.**
Can use **key** as **index** into an **auxiliary** array:
All entries with key **k** are placed in a "**bucket**" at index **k**.

Application: 
- Sort **string** by first letter.
- Sort **class** list by group.
- Sort **phone** numbers by area code.
- **Subroutine** in a sorting algorithm.
___

**Algorithm** bucketSort(**S**):
**Input**: Sequence **S** of entries w/ **integer** keys in range {0, ...,N - 1}.
**Output**: Sequence **S** sorted in non-decreasing order of **keys**.

Let **B** be an **array** of **N** sequences, each initially **empty**.
**For** each entry **e** in **S** **do**
	Let **k** be the **key** of entry **e**.
	**Remove** entry **e** from **S** and **insert** it at the end of `B[k]`.

**For** i = 0 to N - 1 do
	**For** each entry **e** in sequence `B[i]` **do**
		**Remove** entry **e** from `B[i]` and insert it at the end of **S**.

## Efficiency
Time and space **complexity**: O (n + N). Depending on **implementation**, **space** can be O(N) for buckets.
Efficient **when** range of keys **N** is small **compared** to sequence size **n**: e.g. **N is O(n) or O(n logn)**.

## Properties
**Key type**: keys are used as **indices** into an array, **cannot** be arbitrary **objects**.

**Stable sorting**: **preserves** **the relative order** of any two items with the same key.
	For any two items (ki, vi) and (kj, vj) such that Ki = Kj;
	and (ki, vi) precedes (kj, vj), or i < j, in **S** **before** sorting, 
	**then** (ki, vi) also precedes (kj, vj), or i < j, in **S** **after** sorting.