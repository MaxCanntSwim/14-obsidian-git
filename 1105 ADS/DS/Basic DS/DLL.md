Doubly [[Linked list]]:
Each node contains:
- element;
- next: reference to next node;
- prev: reference to previous node.

Sentinels header and trailer:
* dummy nodes to simplify insertions and deletions (avoid special cases).
Tags: #dataStructure #LL
___

# Create/initialise

Create **header** node:
- **element**: **null**;
- **prev** reference: **null**;
- **next** reference: **null**.

Create **trailer** node:
- **element**: **null**;
- **prev** reference: **header**;
- **next** reference: **null**.

Point **header**'s next to **trailer**.
This has a time and space Complexity of $O(1)$. 

# Insert
```java
private void addBetween (E e, Node<E> pred, Node<E> succ)
```
Create new node:
- element e;
- **prev** point to **pred**;
- **next** point to **succ**.

Set references to new node:
- **pred**'s **next**;
- **succ**'s **prev**
This has a time and space Complexity of $O(1)$. 

# Remove
```java
private E remove (Node<E> node)
```
Get predecessor and successor nodes:
- Set pred as node's prev;
- Set succ as node's next

Link out old node:
- Set pred's next as succ;
- Set succ's prev as pred.
This has a time and space Complexity of $O(1)$. 

# insert/remove at head/tail
```java
public void addFirst(E e) {
	addBetween(e, header, header.getNext ()) ;
}

public void addLast (E e) {
	addBetween(e, trailer.getPrev (), trailer);
}

public E removeFirst() {
	if (isEmpty()) return null;
	else return remove(header.getNext ( ));
}

public E removeLast ( ) {
	if(isEmpty( )) return null;
	else return remove(trailer.getPrev ( ));
}
```
these have a time and space Complexity of $O(1)$. 