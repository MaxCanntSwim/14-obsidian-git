A priority queue is a variation on the [[Queue]] consept, where the queue is **Sorted** on the **key** assosiated with an element. 

**Priority Queue**: collection of prioritized elements.
- Insertion at arbitrary positions.
- Removal of element with first priority.
___
Priority:
- Key associated with an element establishes its priority.
- Usually numeric. Any type, as long as keys can be compared.

Priority Queue ADT
* **insert(k, v)** creates an entry with key k and value v, (k, v), in the priority queue
* **min()** returns (does not remove) an entry (k, v) with minimal key (null if empty)
* **removeMin()** removes and returns an entry (k, v) with minimal key (null if empty)
* **size()** returns the number of entries
* **isEmpty()** returns true if empty, false otherwise

| method            | List | sorted list | [[Heap]]       | Adaptable heap | motivation                                                                              |
| ----------------- | ---- | ----------- | -------------- | -------------- | --------------------------------------------------------------------------------------- |
| min()             | O(n) | O(1)        | O(1)           | O(1)           | Root contains minimal key.                                                              |
| removeMin()       | O(n) | O(1)        | O($\log_2(n)$) | O($\log_2(n)$) | Down-heap bubbling performs 0 (log n) swaps.                                            |
| insert(k,v)       | O(1) | O(n)        | O($\log_2(n)$) | O($\log_2(n)$) | Up-heap bubbling performs 0 (logz n) swaps.                                             |
| size()            | O(1) | O(1)        | O(1)           | O(1)           | Size is stored by an instance variable.                                                 |
| isEmpty()         | O(1) | O(1)        | O(1)           | O(1)           | Checks size variable.                                                                   |
| remove(e)         |      |             |                | O($\log_2(n)$) | Removes entry e from the priority queue (error if e is invalid; e.g. not in PQ anymore) |
| replace(e, k)     |      |             |                | O($\log_2(n)$) | Replaces the key of entry e with k (error if e is invalid; e.g. not in PQ anymore)      |
| replaceValue(e,v) |      |             |                | O(1)           | Replaces the value of entry e with v (error if e is invalid; e.g. not in PQ anymore)    |
