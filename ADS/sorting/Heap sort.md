# Heap-based
Sorting **n** elements (**non**-decreasing).
**Heap**-based priority queue **P** (min-heap).

**Phase 1**: **insertion** of all elements into **P**.
	The **i**th insertion takes **O(log i)** time, since it performs **upheap** on the heap with **i** entries.
	Takes O($n\log_2(n)$) time for all insertions.
	Can be **O (n)** using **bottom-up** construction.

**Phase 2: removal**
	The **j**th **removeMin** is 0 (log2(n - j+ 1)), since it **downheaps** heap of n - i + 1 entries.
	Takes **O($n\log_2(n)$)** time for all **removals**.

**Heap sort time complexity** O($n\log_2(n)$)
![[Screenshot 2023-01-07 at 14.54.40.jpg]]

# In-place
Idea to achieve **in-place** heap sorting:
**Optimize** space usage!
- Use portion of array for **heap**.
- Remaining portion for **sorted** sequence.

Use **max-heap** instead!
**Comparator** produces reverse outcome of a min-heap, such that:
- **Maximal** key at the root.
- **Parent**'s key **larger** than or **equal** to its **children**'s keys.
![[Screenshot 2023-01-07 at 14.53.12.jpg]]