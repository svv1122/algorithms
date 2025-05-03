==============
Insertion Sort
==============
Insertion Sort is a simple, comparison-based sorting algorithm. It works by building the sorted list one element at a time by comparing each new element with the already sorted portion and placing it in its correct position.

The algorithm gets its name because elements are "inserted" into their correct position in the sorted portion of the list.

How It Works
------------
1. Start from the second element (index 1).
2. Compare the current element with the elements before it.
3. Shift all elements greater than the current element one position to the right.
4. Insert the current element into its correct position.
5. Repeat the process for the remaining unsorted elements.

The process continues until the entire list is sorted.

Time and Space Complexity
-------------------------
- **Best Case**: O(n) (when the list is already sorted)
- **Average Case**: O(n²)
- **Worst Case**: O(n²) (when the list is reversed)
- **Space Complexity**: O(1) (in-place)
- **Stable**: Yes
- **In-Place**: Yes

Advantages
----------
- Simple to understand and implement
- Efficient for small or nearly sorted datasets
- Stable sort (does not change the relative order of equal elements)

Disadvantages
-------------
- Inefficient for large datasets
- Poor performance on large unsorted data

Example
-------
Sorting the list `[5, 3, 8, 4, 2]` using insertion sort:

1. Pass 1: `[3, 5, 8, 4, 2]`
2. Pass 2: `[3, 5, 8, 4, 2]`
3. Pass 3: `[3, 4, 5, 8, 2]`
4. Pass 4: `[2, 3, 4, 5, 8]`

The list is now sorted.

Python Implementation
---------------------
::

    def insertion_sort(arr):
        for i in range(1, len(arr)):
            key = arr[i]
            j = i - 1
            while j >= 0 and arr[j] > key:
                arr[j + 1] = arr[j]
                j -= 1
            arr[j + 1] = key

    # Example usage
    data = [5, 3, 8, 4, 2]
    insertion_sort(data)
    print(data)  # Output: [2, 3, 4, 5, 8]
