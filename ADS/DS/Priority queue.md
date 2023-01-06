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

