# Recursion
### 1. Definition
- Recursion is a programming technique where a function calls itself directly or indirectly to solve a problem. 
- A recursive algorithm typically solves a problem by breaking it down into smaller sub-problems of the same type, solving each sub-problem, and then combining the solutions to solve the original problem.

### 2. Steps to design a Recursive algorithm
- Identify the Base Case(s): Determine the simplest instance of the problem that can be solved directly.
- Identify the Recursive Case(s): Determine how to break the problem down into smaller instances of the same problem.
- Combine the Results: If necessary, combine the results of the recursive calls to form the final solution.

### 3. Advanced topics
- Memoization: A technique to optimize recursive algorithms by storing the results of expensive function calls and reusing them when the same inputs occur again. This is particularly useful in dynamic programming.
- Backtracking: A recursive technique for solving constraint satisfaction problems, like solving puzzles or finding all permutations of a set.
- Dynamic Programming

### 4. Example
- [Fibonacci Number](https://leetcode.com/problems/fibonacci-number/description/)
```python
class Solution:
    def __init__(self):
        self.mapping = {}

    def fib(self, n: int) -> int:
        if n in self.mapping:
            return self.mapping[n]
        else:
            if n == 0 or n == 1:
                return n
            self.mapping[n] = self.fib(n-1) + self.fib(n-2)
            return self.mapping[n]
```

### 5. LeetCode questions:
- [Recursion](https://leetcode.com/tag/recursion/)
- [Dynamic Programming](https://leetcode.com/tag/dynamic-programming/)
- [Backtracking](https://leetcode.com/tag/backtracking/)
- [Memoization](https://leetcode.com/tag/memoization/)