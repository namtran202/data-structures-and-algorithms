# Monotonic stack
### 1. Definition
- A monotonic queue is a data structure that maintains its elements in a specific order, either increasing or decreasing, to optimize certain operations. The queue ensures that elements are added and removed in a way that preserves this order.
- Monotonic queues are particularly useful for solving problems involving sliding windows or ranges, where maintaining the order of elements helps in efficiently determining the minimum or maximum values within the window.
- Elements are maintained in an increasing (or decreasing) order. New elements are added to the queue after removing elements from the back that are greater (or less) than the new element.

### 2. Example
- [Sliding Window Maximum](https://leetcode.com/problems/sliding-window-maximum/description/)

```python
class Solution:
    def maxSlidingWindow(self, nums: List[int], k: int) -> List[int]:
        window = deque()
        maxQueue = deque()
        maxWindow = []

        for n in nums:
            window.append(n)
            while maxQueue and maxQueue[-1] < n:
                maxQueue.pop()
            maxQueue.append(n)

            if len(window) > k:
                first = window.popleft()
                if first == maxQueue[0]:
                    maxQueue.popleft()
            
            if len(window) == k:
                maxWindow.append(maxQueue[0])
        
        return maxWindow
```

### 3. LeetCode problems: 
[Monotonic queue](https://leetcode.com/tag/monotonic-queue/)