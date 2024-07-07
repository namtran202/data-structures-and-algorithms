# Array
### 1. Definition
A linked list is a linear data structure in which elements, known as nodes, are not stored at contiguous memory locations. Instead, each node contains two parts:
- Data: The value or the element.
- Pointer (or Reference): A reference to the next node in the sequence.

### 2. Types of Linked Lists
- Singly Linked List: Each node has a single link to the next node.
    - Implementation:
```python
class Node:
    def __init__(self, val=0, nextNode=None):
        self.val = val
        self.next = nextNode


class SinglyLinkedList:
    def __init__(self):
        self.head = Node(0)  # dummy node
        self.size = 0

    def get(self, index: int) -> int:
        if index >= self.size:  # invalid index
            return -1

        cur = self.head
        for _ in range(index + 1):
            cur = cur.next
        return cur.val

    def addAtHead(self, val: int) -> None:
        self.addAtIndex(0, val)

    def addAtTail(self, val: int) -> None:
        self.addAtIndex(self.size, val)

    def addAtIndex(self, index: int, val: int) -> None:
        if index > self.size:  # invalid index
            return

        prev = self.head
        for _ in range(index):
            prev = prev.next

        # Add newNode between [prev] and [prev.next]
        newNode = Node(val, prev.next)
        prev.next = newNode
        self.size += 1

    def deleteAtIndex(self, index: int) -> None:
        if index >= self.size:  # invalid index
            return

        prev = self.head
        for _ in range(index):
            prev = prev.next

        prev.next = prev.next.next
        self.size -= 1
```
LeetCode questions: [Singly Linked List](https://leetcode.com/tag/linked-list/)

- Doubly Linked List: Each node has two links, one to the next node and one to the previous node.
    - Implementation:
```python
class Node:
    def __init__(self, val = 0, next = None, prev = None):
        self.val = val
        self.next = next
        self.prev = prev


class DoublyLinkedList:
    def __init__(self):
        self.size = 0
        self.head, self.tail = Node(), Node()
        self.head.next = self.tail
        self.tail.prev = self.head
        
    def get(self, index: int) -> int:
        if index >= self.size: # invalid index
            return -1
            
        cur = self.head
        for _ in range(index+1):
            cur = cur.next
        return cur.val

    def addAtHead(self, val: int) -> None:
        self.addAtIndex(0, val)

    def addAtTail(self, val: int) -> None:
        self.addAtIndex(self.size, val)

    def addAtIndex(self, index: int, val: int) -> None:
        if index > self.size:  # invalid index
            return

        prev = self.head
        for _ in range(index):
            prev = prev.next

        # insert `newNode` between `prev` and `prev.next`
        newNode = Node(val, prev.next, prev)
        prev.next.prev = newNode
        prev.next = newNode
        self.size += 1

    def deleteAtIndex(self, index: int) -> None:
        if index >= self.size:  # invalid index
            return

        prev = self.head
        for _ in range(index):
            prev = prev.next

        nxt = prev.next.next
        prev.next = nxt
        nxt.prev = prev
        self.size -= 1
```

LeetCode questions: [Doubly Linked List](https://leetcode.com/tag/doubly-linked-list/)
- Circular Linked List: The last node points back to the first node, forming a circle.

### 3. Common operators and time complexity

| Parameter | Singly Linked list | Doubly Linked list |
|-----------|--------------------|--------------------|
| get | O(n) | O(n) |
| insert | O(n) | O(n) |
| addHead| O(1) | O(1) |
| addTail| O(n) | O(1) |
| deleteAtIndex | O(n) | O(n) |

### 4. Compare Array vs Linked List
| Criteria | Array | Linked List |
|----------|-------|-------------|
| Memory| Arrays have a fixed size allocated at creation. If an array's size is specified to be larger than needed, it wastes memory. (except for dynamic array).<br>  Memory usage is contiguous; the entire array is stored in a single block of memory.| Linked lists are dynamic in size; they grow and shrink as needed. <br> Memory usage is non-contiguous; each node can be stored anywhere in memory. |
| Index access | Direct access: Accessing an element by its index is O(1) because arrays support random access. | Sequential access: Accessing an element by its index is O(n) for a singly linked list because you have to traverse from the head to the desired index. |
| Insertion/Deletion | Inserting or deleting at the beginning or middle requires shifting elements, which is O(n) | nserting or deleting in the middle requires traversal to the point of insertion/deletion, which is O(n). <br> Overall, insertion/deletion can be more efficient in linked lists compared to arrays, especially for large datasets. |
| Cache-friendly | Arrays are cache-friendly because their elements are stored in contiguous memory locations. Accessing sequential elements leads to fewer cache misses. | Linked lists are not cache-friendly because their elements are scattered throughout memory. This can lead to more cache misses and slower performance. |
| Use cases | Suitable for situations where quick access to elements is needed (e.g., accessing elements by index). <br> Ideal for fixed-size collections where the size doesn't change often. | Suitable for scenarios where frequent insertion and deletion are required. <br> Ideal for dynamic collections where the size changes often. |