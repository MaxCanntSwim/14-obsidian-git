Stack (or pile of elements) is a different variation on Data Structures where you only have access to the first element in the data structure.
We can only access/modify the top of the stack.
___


A possible implementation of a stack you can use the [[SLL]]. 
| stack method | SLL method    |
| ------------ | ------------- |
| size()       | size()        |
| isEmpty()    | isEmpty       |
| push(e)      | addFirst(e)   |
| pop()        | removeFirst() |
| top()        | first()              |

Last-in, first-out principle (LIFO):
- elements can be inserted at any time;
- only the last inserted element (top of the stack) can be accessed or deleted.

Applications:
- Candy dispenser.
- Text editor undo: most recent change undone first.

Operations:
- **push**: insert element onto the stack;
- **pop**: remove element at the top of the stack;
- **top**/**peek**: access top element, without removing.
- **size**: returns the **size** of the stack
- **isEmpty**: checkes if there are elements in the stack
- These have a time and space Complexity of $O(1)$. 