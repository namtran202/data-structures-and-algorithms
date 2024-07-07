# Sliding window
### 1. Definition
- Approach for solving problems that involve finding a subarray or substring that meets certain criteria
- Maintaining a window that slides over the array or string, expanding or contracting as needed to find the desired result
- Useful for problems related to sums, averages, and conditions within subarrays or substrings
- Reduce Time complexity from O(n<sup>2</sup>) to O(n)

### 2. Example

- [Minimum Size Subarray Sum](https://leetcode.com/problems/minimum-size-subarray-sum/description/)

```python
class Solution:
    def minSubArrayLen(self, target: int, nums: List[int]) -> int:
        n = len(nums)
        windowSum, l, ans = 0, 0, n+1
        for r in range(n):
            windowSum += nums[r]
            while windowSum >= target:
                ans = min(ans, r-l+1)
                windowSum -= nums[l]
                l+=1
        return ans if ans != n+1 else 0
```

- [Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/description/)

```python
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        longest = 0
        frequency = defaultdict(int)

        left, right = 0, 0
        while right < len(s):
            frequency[s[right]] += 1
            if frequency[s[right]] > 1:
                longest = max(longest, right - left)
                while frequency[s[right]] > 1:
                    frequency[s[left]] -= 1
                    left += 1
                
            right += 1
        
        return max(longest, right - left)
```

- LeetCode questions: [Sliding window](https://leetcode.com/tag/sliding-window/)