This [[Data Structures]] is a sequence of positions, each with 1 element. Traversal in both directions.
Elements accessed via positions, no direct access to nodes.
Tags: #dataStructure #secondDegreeImplementation
___

**Accessor methods**
* **getElement()** returns element stored at position
* **first()** returns position of first element (null if empty)
* **last()** returns position of last element (null if empty)
* **before(p)** returns position just before p (null if p is first) A
* **after(p)** returns position just after p (null if p is last)
* **isEmpty()** returns true if list is empty, false otherwise 
* **size()** returns the number of elements in list

**Update methods** 
* **addFirst(e)** inserts e at the front, returns position
* **addLast(e)** inserts e at the back, returns position
* **addBefore(p, e)** inserts e before p addAfter(p, e) inserts e after p
* **set(p, e)** replaces element at position p with e
* **remove(p)** removes and returns element at P


**Define a position (reference to a node) that does not allow access to the rest of the list.**
In Java we can define an abstraction of a node using an interface.
**Position interface allows access to element only!**