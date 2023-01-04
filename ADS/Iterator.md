Abstracts the process of scanning through a sequence, one element at a time.

Java.til.Iterator 
* **hasNext()**  returns true if there's at least one additional element in the sequence
* **next()**  returns the next element in the sequence (or NoSuchElementException)
* **remove()** optional method, removes the element returned by the most recent call to next()

**Provides a single pass through a collection. No way to reset the iterator.**
Some iterators have previous() method, which can be used to go back. But going all the way back is 0(n). To reset, it's better to just create new iterator (which is O(1) for iterator operating on the original data structure).

### Snapshot iterator
- Maintains own private copy of the collection, constructed at creation.
- Unaffected by changes to the primary collection.
- Requires O(n) space and O(n) time upon construction (copy and keep collection of n elements).

### Lazy iterator
* Does not make a copy, directly traverses the primary data structure.
* Affected by changes to the primary collection.
- Requires 0(1) space and 0(1) construction time.
- 'fail-fast' behavior invalidates an iterator if its underlying collection is modified unexpectedly.