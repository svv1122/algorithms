==========
Shell Sort
==========
**Shell Sort** is an in-place comparison-based sorting algorithm that generalizes insertion sort by allowing comparisons and exchanges of elements far apart.
It improves upon simple quadratic sorts by partially sorting the list using larger intervals (gaps), then progressively reducing the gap until a final insertion sort pass.

Algorithm Steps
---------------
1. Choose an initial gap value (usually `n // 2`), and reduce it on each pass.
2. For each element in the array, perform a gapped insertion sort:
   - Compare the element with others `gap` positions before it.
   - If it is smaller, shift the larger element forward.
3. Repeat the process with smaller gaps until the gap is 1.
4. The final pass is a standard insertion sort, but the array is already partially sorted.

Time and Space Complexity
-------------------------
- **Best Case Time Complexity**: :math:`O(n \log n)` (depends on gap sequence)
- **Average Case Time Complexity**: Between :math:`O(n^{3/2})` and :math:`O(n \log^2 n)`
- **Worst Case Time Complexity**: :math:`O(n^2)` (Shell's original gap sequence)
- **Space Complexity**: :math:`O(1)` (in-place)
- **Stability**: Not stable

Example
-------
Given the list: ``[8, 5, 3, 7, 6, 2, 4]``

Shell Sort with gap sequence `n//2 → n//4 → 1`:

1. Gap = 3 → sort sublists ``[8, 7]``, ``[5, 6]``, ``[3, 2]`` → partial sort
2. Gap = 1 → standard insertion sort on the nearly sorted list

Result: ``[2, 3, 4, 5, 6, 7, 8]``

Use Cases
---------
Shell Sort is useful when:
- You need a simple, fast in-place sort without recursion.
- You work on medium-size arrays where performance matters, but full `O(n log n)` complexity isn't required.
- Minimizing writes is not the highest priority (unlike selection sort).

Python Implementation
---------------------
::

    def shell_sort(arr):
        n = len(arr)
        gap = n // 2
        while gap > 0:
            for i in range(gap, n):
                temp = arr[i]
                j = i
                while j >= gap and arr[j - gap] > temp:
                    arr[j] = arr[j - gap]
                    j -= gap
                arr[j] = temp
            gap //= 2

    # Example usage
    data = [8, 5, 3, 7, 6, 2, 4]
    shell_sort(data)
    print("Sorted array:", data)

    # Output: Sorted array: [2, 3, 4, 5, 6, 7, 8]
