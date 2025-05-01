==============
Selection Sort
==============
**Selection Sort** is a simple comparison-based sorting algorithm. It works by repeatedly selecting the smallest (or largest, depending on sorting order) element from the unsorted portion of the list and moving it to the beginning.

Algorithm Steps
---------------
1. Start with the first element as the minimum.
2. Compare this minimum with the rest of the array to find the true minimum.
3. Swap the found minimum with the first element.
4. Move the boundary of the sorted and unsorted subarrays one element forward.
5. Repeat the above steps for the remaining unsorted elements.

Time and Space Complexity
-------------------------
- **Best Case Time Complexity**: :math:`O(n^2)`
- **Average Case Time Complexity**: :math:`O(n^2)`
- **Worst Case Time Complexity**: :math:`O(n^2)`
- **Space Complexity**: :math:`O(1)` (in-place)
- **Stability**: Not stable

Example
-------
Given the list: ``[64, 25, 12, 22, 11]``

Selection Sort will perform the following steps:

1. Find the minimum element (11) and swap with 64 → ``[11, 25, 12, 22, 64]``
2. Find the next minimum (12) and swap with 25 → ``[11, 12, 25, 22, 64]``
3. Find the next minimum (22) and swap with 25 → ``[11, 12, 22, 25, 64]``
4. The array is now sorted.

Use Cases
---------
Selection sort is generally not suitable for large datasets due to its quadratic time complexity, but it is useful for educational purposes and small arrays where memory writes are costly (as it does fewer swaps compared to other simple sorts).

Python Implementation
--------------
::

    def selection_sort(arr):
        n = len(arr)
        for i in range(n):
            # Assume the current position is the minimum
            min_idx = i
            for j in range(i + 1, n):
                if arr[j] < arr[min_idx]:
                    min_idx = j
            # Swap the found minimum element with the first element
            arr[i], arr[min_idx] = arr[min_idx], arr[i]

    # Example usage
    data = [64, 25, 12, 22, 11]
    selection_sort(data)
    print("Sorted array:", data)

    # Output: Sorted array: [11, 12, 22, 25, 64]
