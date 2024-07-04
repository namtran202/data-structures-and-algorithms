# Two pointers:
- A commonly used approach in problems involving arrays and linked lists
- Involves using two pointers (or indices) to traverse the array (or list) from different directions or at different speeds
    - One slow-runner and the other fast-runner
    - One pointer starts from the beginning while the other pointer starts from the end
- Useful for solving problems related to searching, sorting, and finding pairs or subarrays that meet certain conditions

## Example:
- One slow-runner and the other fast-runner
[Remove Duplicates from Sorted Array](https://leetcode.com/problems/remove-duplicates-from-sorted-array/description/)

```python
class Solution:
    def removeDuplicates(self, nums: List[int]) -> int:
        i = 0
        for j in range(1,len(nums)):
            if nums[j] != nums[i]:
                i+=1
                nums[i] = nums[j]
        return i + 1
```

- One pointer starts from the beginning while the other pointer starts from the end
[Two Sum II - Input Array Is Sorted](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/description/)

```python
class Solution:
    def twoSum(self, numbers: List[int], target: int) -> List[int]:
        l, r = 0, len(numbers) - 1
        while l < r:
            total = numbers[l] + numbers[r]
            if numbers[l] + numbers[r] == target:
                return [l+1, r+1]
            if total > target:
                r-=1
            else:
                l+=1
```

- LeetCode questions: [Two pointers](https://leetcode.com/tag/two-pointers/)