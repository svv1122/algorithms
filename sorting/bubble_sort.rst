===========
Bubble Sort
===========
Bubble Sort is a simple, comparison-based sorting algorithm. It works by repeatedly stepping through the list, comparing adjacent elements, and swapping them if they are in the wrong order. This process is repeated until the list is sorted.

The algorithm gets its name because smaller elements "bubble" to the top (beginning of the list) while larger elements sink to the bottom with each pass.

How It Works
------------
1. Start from the beginning of the list.
2. Compare the current element with the next one.
3. If the current element is greater than the next, swap them.
4. Repeat steps 2–3 for all adjacent pairs.
5. After each full pass, the largest element is at the end.
6. Repeat the process for the remaining unsorted portion.

The process continues until no more swaps are needed, which means the list is sorted.

Time and Space Complexity
-------------------------
- **Best Case**: O(n) (when the list is already sorted, with an optimized version that checks for swaps)
- **Average Case**: O(n²)
- **Worst Case**: O(n²)
- **Space Complexity**: O(1) (in-place)
- **Stable**: Yes
- **In-Place**: Yes

Advantages
----------
- Simple and easy to understand
- Good for small or nearly sorted datasets
- Stable sort (does not change the relative order of equal elements)

Disadvantages
-------------
- Very inefficient on large datasets
- Performance degrades quickly as the number of items increases

Example
-------
Sorting the list `[5, 3, 8, 4, 2]` using bubble sort:

1. Pass 1: `[3, 5, 4, 2, 8]`
2. Pass 2: `[3, 4, 2, 5, 8]`
3. Pass 3: `[3, 2, 4, 5, 8]`
4. Pass 4: `[2, 3, 4, 5, 8]`

The list is now sorted.

Python Implementation
---------------------
::

    def bubble_sort(arr):
        n = len(arr)
        for i in range(n):
            swapped = False
            for j in range(0, n - i - 1):
                if arr[j] > arr[j + 1]:
                    arr[j], arr[j + 1] = arr[j + 1], arr[j]
                    swapped = True
            if not swapped:
                break

