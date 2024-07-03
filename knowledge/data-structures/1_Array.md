# Array
### 1. Definition:
An array is a data structure that can hold a number of elements of the same type. 
```python
array = [1, 2, 3] # array of integer elements
array = ["a", "b", "c"] # array of integer elements
```

### 2. Characteristics:
- Homogeneous Elements: All elements in an array must be of the same type.
- Indexed Access: Elements in an array are accessed using an index, with the first element typically starting at index 0.
- Contiguous Memory Allocation: Elements of an array are stored in contiguous memory locations, allowing for efficient access and manipulation.

### 3. Use cases:
- Storing Multiple Values: Arrays are ideal for storing multiple values of the same type, such as a list of test scores, temperatures, or names.
- Iterating Over Elements: Arrays allow for easy iteration over elements using loops, enabling efficient processing of data.
- Sorting and Searching: Arrays are commonly used in algorithms for sorting and searching data.

### 4. Operators and Time complexity:

| Parameter | Linked list | Array | Dynamic array |
|-----------|-------------|-------|---------------|
| Indexing | O(n) | O(1) | O(1) |
| Insertion/deletion at beginning| O(1) | O(n), if array is not full (for shifting the elements) | O(n) |
| Insertion at ending | O(n) | O(1), if array is not full | O(1), if array is not full<br>O(n), if array is full |
| Deletion at ending | O(n) | O(1) | O(n) |
| Insertion in middle | O(n) | O(n), if array is not full (for shifting the elements) | O(n) |
| Deletion in middle | O(n) | O(n), if array is not full (for shifting the elements) | O(n) |
| Wasted space | O(n) (for pointers) | 0 | O(n) |

Note: Deletion/Insertion at end for dynamic arrays is O(1) amortized

### 5. Algorithm:
- [Two pointers](../algorithms/1_Two_pointers.md)
- [Sliding window](../algorithms/2_Sliding_window.md)