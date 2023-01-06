A Singly [[Linked list]] is a sequence of nodes starting from a head pointer:
* tail: last node of the list; its next reference is null; 
* traversal: moving through the list following nodes' next references.
Tags: #dataStructure #LL
____
A node contains a reference to the element it contains and a reference to the next node. 

### Inserting at the head
1. Create new node
2. insert new node, have it point to the old head
3. update the head, have it point to the inserted node. 
This has a time and space Complexity of $O(1)$. 

### Inserting at the Tail
1. Create new node
2. insert new node, have the tail's next reference point to the new node
3. update the tail, have it point to the inserted node. 
This has a time and space Complexity of $O(1)$. 

### Remove head
1. update head, point to the current head's next reference. 
2. return the old head
This has a time and space Complexity of $O(1)$. 

### Remove tail
To remove the tail, set the next reference of the node before the tail to null and make that node the new tail. 
1. first traverse the list to find the last but one node
2. update the tail to point to that node
3. update the new tail's next reference to null
4. return the old tail. 
This has a time Complexity of $O(n)$ and a space complexity of $O(1)$. 