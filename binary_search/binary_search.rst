=============
Binary Search 
=============
**Binary search** is an efficient algorithm for finding a target value within a sorted array or list. 
It works by repeatedly dividing the search interval in half, significantly reducing the time complexity compared to linear search.

Key Features
------------
- **Works Only on Sorted Data:** Binary search requires the array or list to be sorted beforehand.
- **Divide and Conquer Strategy:** It splits the data set into halves and focuses only on the half where the target could be.
- **Efficient Time Complexity:** Reduces the search time from O(n) to O(log n).

How It Works
------------
1. Set two pointers, typically `low` at the start and `high` at the end of the array.
2. While `low` is less than or equal to `high`:
   - Calculate the middle index: `mid = (low + high) // 2`.
   - Compare the target value with the element at `mid`.
   - If the target equals `arr[mid]`, the search is successful.
   - If the target is less than `arr[mid]`, adjust `high = mid - 1`.
   - If the target is greater than `arr[mid]`, adjust `low = mid + 1`.
3. If the pointers cross without finding the target, the target is not in the array.

Basic Example
-------------
Binary search on a sorted array::

    def binary_search(arr, target):
        low = 0
        high = len(arr) - 1
        while low <= high:
            mid = (low + high) // 2
            if arr[mid] == target:
                return mid
            elif arr[mid] < target:
                low = mid + 1
            else:
                high = mid - 1
        return -1

    array = [1, 3, 5, 7, 9, 11]
    print(binary_search(array, 7))  # Output: 3

Advantages
----------
- Much faster than linear search for large sorted arrays.
- O(log n) time complexity ensures high performance even with large datasets.
- Simple to implement iteratively or recursively.

Disadvantages
-------------
- Only applicable to sorted arrays or lists.
- Requires careful handling of indices to avoid overflow (especially in some languages like C++).

Relative Problems
------------------
- 4. Median of Two Sorted Arrays: `https://leetcode.com/problems/median-of-two-sorted-arrays/`
