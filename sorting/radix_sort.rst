==========
Radix Sort
==========
Radix Sort is a non-comparative sorting algorithm that sorts numbers (or strings) by processing individual digits. It works by sorting the elements based on each digit, starting from the least significant digit (LSD) to the most significant digit (MSD), or vice versa depending on the implementation.

It's especially efficient when dealing with integers or fixed-length strings.

How It Works
------------
1. Find the maximum number to determine the number of digits.
2. Starting from the least significant digit (LSD), group the numbers into buckets (0–9) based on that digit.
3. Concatenate the buckets in order.
4. Repeat the process for each digit moving toward the most significant digit.
5. After processing all digits, the list is sorted.

Radix Sort typically uses a stable sub-sorting algorithm like Counting Sort for each digit level.

Time and Space Complexity
-------------------------
- **Best Case**: O(nk)
- **Average Case**: O(nk)
- **Worst Case**: O(nk)
  - *n*: number of elements
  - *k*: number of digits in the largest number
- **Space Complexity**: O(n + k)
- **Stable**: Yes
- **In-Place**: No (uses extra buckets)

Advantages
----------
- Very efficient for sorting integers or strings of fixed length
- Linear time complexity when *k* is small
- Stable sort

Disadvantages
-------------
- Not comparison-based, so it's less versatile
- Requires additional memory for buckets
- Performance may degrade for very large numbers or variable-length data

Example
-------
Sorting the list `[170, 45, 75, 90, 802, 24, 2, 66]` using radix sort:

1. After sorting by LSD (1s place): `[170, 90, 802, 2, 24, 45, 75, 66]`
2. After sorting by 10s place: `[802, 2, 24, 45, 66, 170, 75, 90]`
3. After sorting by 100s place: `[2, 24, 45, 66, 75, 90, 170, 802]`

The list is now sorted.

Python Implementation
---------------------
::

    def counting_sort_for_radix(arr, exp):
        n = len(arr)
        output = [0] * n
        count = [0] * 10

        for i in range(n):
            index = (arr[i] // exp) % 10
            count[index] += 1

        for i in range(1, 10):
            count[i] += count[i - 1]

        i = n - 1
        while i >= 0:
            index = (arr[i] // exp) % 10
            output[count[index] - 1] = arr[i]
            count[index] -= 1
            i -= 1

        for i in range(n):
            arr[i] = output[i]

    def radix_sort(arr):
        if len(arr) == 0:
            return

        max_num = max(arr)
        exp = 1
        while max_num // exp > 0:
            counting_sort_for_radix(arr, exp)
            exp *= 10
