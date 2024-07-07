# Stack
### 1. Definition:
A stack is a linear data structure that follows the Last In, First Out (LIFO) principle. This means the last element added to the stack will be the first one to be removed.

### 2. Basic Operations:
- Push: Adds an element to the top of the stack.
- Pop: Removes the top element from the stack.
- Peek/Top: Returns the top element of the stack without removing it.
- IsEmpty: Checks if the stack is empty.

### 3. Implementation

```python
class Stack:
    def __init__(self):
        self.stack = []
    
    def push(self, value):
        self.stack.append(value)
    
    def pop(self):
        if not self.is_empty():
            return self.stack.pop()
        return None
    
    def peek(self):
        if not self.is_empty():
            return self.stack[-1]
        return None
    
    def is_empty(self):
        return len(self.stack) == 0
```