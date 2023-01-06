Similerly to a [[Stack]] in a queue you can only interact with the ends of the Data Structures. 
Insertion and deletion follow first-in, first-out principle (FIFO):
* Elements can be inserted at any time, at the back of the queue.
* Only the element that has been the longest in the queue can be removed.
Tags: #dataStructure #secondDegreeImplementation
___
For the queue the methods for a [[SLL]] can be used

| queue method | SLL method    |
| ------------ | ------------- |
| size()       | size()        |
| isEmpty()    | isEmpty       |
| enqueue(e)   | addLast(e)    |
| dequeue()    | removeFirst() |
| first()      | first()       |
Applications:
- Handle calls to a call center.
- Handle printing jobs.

Opperations
* enqueue: enters an element at the start of the queue
* dequeue: removes the oldest element from the queue
* first: returns the oldest element from the queue, but does not remove
* size: returns the number of elements in the que
* isEmpty: return true if the queue is empty, false otherwise

### Deques
pronounced as decks.
This is a queue with access to the both sides of the queue. 
A [[DLL]] can be used to implement this. 