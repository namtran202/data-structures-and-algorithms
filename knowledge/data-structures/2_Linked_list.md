# Array
### 1. Definition:
A linked list is a linear data structure in which elements, known as nodes, are not stored at contiguous memory locations. Instead, each node contains two parts:
- Data: The value or the element.
- Pointer (or Reference): A reference to the next node in the sequence.

### 2. Types of Linked Lists:
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
Example: [LeetCode](https://leetcode.com/tag/linked-list/)

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

Example: [LeetCode](https://leetcode.com/tag/doubly-linked-list/)
- Circular Linked List: The last node points back to the first node, forming a circle.