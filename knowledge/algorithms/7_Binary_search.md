# Binary Search
### 1. Definition
- Binary search is an efficient algorithm for finding an item from a sorted list of items. 
- It works by repeatedly dividing the portion of the list that could contain the item in half until you've narrowed the possible locations to just one.

### 2. Key Characteristics
- Sorted Input: Binary search requires the input array to be sorted.
- Divide and Conquer: It repeatedly divides the search interval in half.
- Efficiency: Its time complexity is O(logn), making it much more efficient than linear search O(n) for large datasets.
![TimeComplexity](../../img/TimeComplexity.png)

### 3. Use Cases
- Finding an Element: Quickly locating an element in a sorted array.
- Bounds Checking: Finding the first or last position of an element (variant: lower_bound, upper_bound).
- Search Problems: Problems involving the search of a sorted space, such as finding the peak element, finding the minimum in rotated sorted arrays, etc.

### 4. Advanced Knowledge
- Variations of Binary Search:
    - Lower Bound (bisect_left in Python): Finding the smallest element that is greater than or equal to the target.
    ```python
    def lowerBound(nums, target):
    left = 0
    right = len(nums) - 1
    ans = len(nums)
    while left <= right:
        mid = (left + right) // 2
        if nums[mid] >= target:
            ans = mid  # update the best result so far
            right = mid - 1  # search better result on the left side
        else:
            left = mid + 1  # search result on the right side
    return ans
    ```
    - Upper Bound (bisect_right in Python): Finding the smallest element that is greater than the target.
    ```python
    def upperBound(nums, target):
        left = 0
        right = len(nums) - 1
        ans = len(nums)
        while left <= right:
            mid = (left + right) // 2
            if nums[mid] > target:  
                ans = mid  # update the best result so far
                right = mid - 1  # search better result on the left side
            else:
                left = mid + 1  # search result on the right side
        return ans
    
    ```

- Binary Search on Answer:
    - Used in optimization problems where you binary search over possible answers rather than array indices. Examples include finding the maximum feasible distance between elements, minimum maximum pages allocation, etc.

- Applications in Data Structures:
    - Binary Search Trees: Self-balancing trees like AVL or Red-Black trees use binary search properties.
    - Heaps: Finding elements or bounds in priority queues.
    - Segment Trees and Binary Indexed Trees: Used in range query problems.

- Performance Considerations:
    - Binary search has a logarithmic time complexity O(logn) but requires a sorted array.
    - When insertion and deletion are frequent, maintaining a sorted array can be expensive. Data structures like balanced trees can offer better performance in such cases.

### 5. Example
- [Binary Search](https://leetcode.com/problems/binary-search/description/)
```python
def search(self, nums: List[int], target: int) -> int:
    left, right = 0, len(nums) - 1
    while left <= right:
        mid = (left + right) // 2
        if nums[mid] == target:
            return mid
        elif nums[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    return -1
```

- [Find First and Last Position of Element in Sorted Array](https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/description/)
```python
def searchRange(self, nums: List[int], target: int) -> List[int]:
    if target not in nums:
        return [-1,-1]
    start = bisect_left(nums, target)
    end = bisect_right(nums, target)
    return [start, end-1]
```