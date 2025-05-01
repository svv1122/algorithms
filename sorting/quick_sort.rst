==========
Quick Sort
==========
**Quick Sort** is a highly efficient divide-and-conquer sorting algorithm. It works by selecting a 'pivot' element from the array and partitioning the other elements into two sub-arrays: one with elements less than the pivot and one with elements greater than the pivot. The sub-arrays are then sorted recursively.

Algorithm Steps
---------------
1. Choose a pivot element from the array.
2. Partition the array such that elements less than the pivot go to the left, and elements greater go to the right.
3. Recursively apply the above steps to the sub-arrays.

Time and Space Complexity
-------------------------
- **Best Case Time Complexity**: :math:`O(n \log n)`
- **Average Case Time Complexity**: :math:`O(n \log n)`
- **Worst Case Time Complexity**: :math:`O(n^2)` (rare, occurs with poor pivot choices)
- **Space Complexity**: :math:`O(\log n)` (due to recursion stack)
- **Stability**: Not stable

Example
-------
Given the list: ``[10, 7, 8, 9, 1, 5]``

Quick Sort might do the following:

1. Choose 5 as pivot.
2. Partition: [1] [5] [10, 7, 8, 9]
3. Recurse on [1] and [10, 7, 8, 9], and continue sorting recursively.

Python Implementation
----------------------
::

    def quick_sort(arr):
        def _quick_sort(items, low, high):
            if low < high:
                # Partition the array
                pi = partition(items, low, high)
                # Recursively sort elements before and after partition
                _quick_sort(items, low, pi - 1)
                _quick_sort(items, pi + 1, high)

        def partition(items, low, high):
            pivot = items[high]
            i = low - 1
            for j in range(low, high):
                if items[j] <= pivot:
                    i += 1
                    items[i], items[j] = items[j], items[i]
            items[i + 1], items[high] = items[high], items[i + 1]
            return i + 1

        _quick_sort(arr, 0, len(arr) - 1)

    # Example usage
    data = [10, 7, 8, 9, 1, 5]
    quick_sort(data)
    print("Sorted array:", data)

    # Output: Sorted array: [1, 5, 7, 8, 9, 10]
