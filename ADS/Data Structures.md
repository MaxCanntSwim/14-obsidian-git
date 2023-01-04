A data structure is a specialized format for organizing, processing, retrieving and storing data. There are several basic and advanced types of data structures, all designed to arrange data to suit a specific purpose. Data structures make it easy for users to access and work with the data they need in appropriate ways.
___
|                              | [[Array]] | [[SLL]] | [[CLL]] | [[DLL]] |
| ---------------------------- | --------- | ------- | ------- | ------- |
| Access element by (by index) | O(1)      | O(n)    | O(n)    | O(n)    |
| Search element               | O(n)      | O(n)    | O(n)    | O(n)    |
| Insertion                    |           |         |         |         |
| At head                      | O(n)      | O(1)    | O(1)    | O(1)    |
| At tail                      | O(1)      | O(1)    | O(1)    | O(1)    |
| Deletion                     |           |         |         |         |
| at head                      | O(n)      | O(1)    | O(1)    | O(1)    |
| at tail                      | O(1)      | O(n)    | O(n)    | O(1)    |
| Clone/copy                   | O(n)      | O(n)    | O(n)    | O(n)    |

Array: fixed capacity, wastes space if overdimensioned, costs time if underdimensioned (expansion).
List: grows efficiently.

### Abstract Data Structure (ADT)

Abstraction of a data structure, cannot be instantiated. It specifies:
- Signatures of operations on the data structure;
- May also contain constants, default or static methods, ...