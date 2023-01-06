Circularly [[Linked list]]:
- Singly linked list (SLL) with tail's next pointing to head node, rather than null (no explicit head).
- Operations: addFirst(e), addLast(e), removeFirst ( ) as in SLL + update method rotate().

**Advantages of a CLL**: efficient expansion, natural representation of cyclic data.

**Disadvantages**: access to elements requires traversal, cannot easily remove tail or in the middle.
Tags: #dataStructure #LL
____
### Rotate
**Rotete method**: updates the tail by following its next reference (implicit head).
This has a time and space Complexity of $O(1)$. 

### Insert at head
1. Create new node, next reference pointiong at tail's next reference. 
2. update tail's next to point to new node
This has a time and space Complexity of $O(1)$. 

### Insert at tail
1. call the insert at head mehode
2. call the rotate method, to point to the new tail. 
This has a time and space Complexity of $O(1)$. 

### Remove head
Get explicit pointer to head. 
	If: identical to tail, there's only one node: set tail to null.
	else: Set tail's next to head's next.
