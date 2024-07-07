# Stack
### 1. Definition:
A stack is a linear data structure that follows the Last In, First Out (LIFO) principle. This means the last element added to the stack will be the first one to be removed.

### 2. Basic Operations:
- Push: Adds an element to the top of the stack. TC: O(1)
- Pop: Removes the top element from the stack. TC: O(1)
- Peek/Top: Returns the top element of the stack without removing it. TC: O(1)
- IsEmpty: Checks if the stack is empty. O(1)

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

### 4. Common use
- Expression Evaluation and Syntax Parsing: Used in evaluating expressions (e.g., converting infix to postfix expressions) and parsing syntax.
- Backtracking Algorithms: Such as Depth-First Search (DFS) in graphs and trees.
- Function Call Management: Manages function calls and local variables (call stack) in programming languages.

### 5. Advanced algorithm
- Monotonic stack