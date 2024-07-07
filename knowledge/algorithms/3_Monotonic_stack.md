# Monotonic stack
### 1. Definition
- A monotonic stack is a data structure that maintains its elements in a specific order, either increasing (monotonically increasing stack) or decreasing (monotonically decreasing stack)
- Elements are maintained in an increasing (or decreasing) order. As you push new elements onto the stack, you remove elements from the stack that are greater (or less) than the new element.

### 2. Example
- [Next Greater Element II](https://leetcode.com/problems/next-greater-element-ii/description/)

```python
class Solution:
    def nextGreaterElements(self, nums: List[int]) -> List[int]:
        stack = [] 
        nums.extend(nums)
        res = [-1] * len(nums)
        for i, num in enumerate(nums):              
            while stack and nums[stack[-1]] < num:
                res[stack.pop()] = num
            stack.append(i)
        return res[:len(nums)//2]
```

- LeetCode problems: [Monotonic stack](https://leetcode.com/tag/monotonic-stack/)