==========
Merge Sort
==========
Merge Sort is a classic, efficient, and stable sorting algorithm based on the **divide and conquer** paradigm. It works by recursively dividing the array into halves, sorting each half, and then merging the sorted halves into a single sorted array.

How It Works
------------
1. If the list has one or no elements, it's already sorted.
2. Divide the list into two approximately equal halves.
3. Recursively apply merge sort to both halves.
4. Merge the two sorted halves into one sorted list.

The merging process involves comparing the smallest elements of each half and building a new sorted array.

Time and Space Complexity
-------------------------
- **Best Case**: O(n log n)
- **Average Case**: O(n log n)
- **Worst Case**: O(n log n)
- **Space Complexity**: O(n) (not in-place)
- **Stable**: Yes
- **In-Place**: No

Advantages
----------
- Predictable and consistent performance (always O(n log n))
- Stable sort (preserves the relative order of equal elements)
- Suitable for sorting linked lists and external sorting
- Naturally parallelizable due to divide-and-conquer nature

Disadvantages
-------------
- Requires additional memory (not in-place)
- Slightly slower than Quick Sort in practical, in-memory use due to more copying

Example
-------
Sorting the list `[38, 27, 43, 3, 9, 82, 10]`:

1. Divide: `[38, 27, 43]`, `[3, 9, 82, 10]`
2. Further divide until single elements
3. Merge step-by-step:
   - `[27, 38, 43]` and `[3, 9, 10, 82]`
   - Final result: `[3, 9, 10, 27, 38, 43, 82]`

Python Implementation
---------------------
::

    def merge_sort(arr):
        if len(arr) <= 1:
            return arr
        mid = len(arr) // 2
        left = merge_sort(arr[:mid])
        right = merge_sort(arr[mid:])
        return merge(left, right)

    def merge(left, right):
        result = []
        i = j = 0
        while i < len(left) and j < len(right):
            if left[i] <= right[j]:
                result.append(left[i])
                i += 1
            else:
                result.append(right[j])
                j += 1
        result.extend(left[i:])
        result.extend(right[j:])
        return result
