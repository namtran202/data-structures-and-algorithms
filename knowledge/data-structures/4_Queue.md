# Queue
### 1. Definition
A queue is a linear data structure that follows the First In, First Out (FIFO) principle. This means the first element added to the queue will be the first one to be removed.

### 2. Basic Operations
- Enqueue: Adds an element to the end of the queue. TC: O(1)
- Dequeue: Removes the front element from the queue. TC: O(1)
- Front: Returns the front element of the queue without removing it. TC: O(1)
- IsEmpty: Checks if the queue is empty. TC: O(1)

### 3. Implementation

```python
class Queue:
    def __init__(self):
        self.queue = deque()
    
    def enqueue(self, value):
        self.queue.append(value)
    
    def dequeue(self):
        if not self.is_empty():
            return self.queue.popleft()
        return None
    
    def front(self):
        if not self.is_empty():
            return self.queue[0]
        return None
    
    def is_empty(self):
        return len(self.queue) == 0
```

### 4. Common use
- Breadth-First Search (BFS): In graphs and trees, BFS uses a queue to explore nodes level by level.
- Task Scheduling: In operating systems for managing processes in a queue (e.g., round-robin scheduling).
- Buffer Management: Used in handling data streams (e.g., IO buffers).

### 5. Advanced algorithm
- [Monotonic queue](../algorithms/4_Monotonic_queue.md)

### 6. LeetCode questions: 
[Queue](https://leetcode.com/tag/queue/)