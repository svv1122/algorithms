==============
Sliding Window
==============
The sliding window technique is a powerful algorithmic approach used for solving problems involving arrays, lists, or strings. It involves creating a "window" which can either be fixed-size or variable-size and moving it across the data structure to examine a subset of elements at a time.

This approach is especially useful in scenarios that require examining contiguous elements or computing aggregates like sums, averages, or maximums over a range.

Core Concept
------------
Instead of using nested loops to evaluate all possible subarrays or substrings (which may lead to high time complexity), the sliding window method optimizes performance by reusing previous computations as the window moves forward.

Variants
--------
- **Fixed-size window**: The size of the window remains constant throughout the algorithm.
- **Dynamic-size window**: The window expands or contracts based on certain conditions (often used in substring and pattern-matching problems).

Use Cases
---------
- **Maximum sum of subarray of size `k`**
- **Longest substring without repeating characters**
- **Minimum window substring**
- **Stream processing and time series analysis**

Benefits
--------
- Reduces time complexity from O(n²) to O(n) in many cases
- Simple and intuitive to implement
- Saves memory by avoiding unnecessary storage of intermediate results

Limitations
-----------
- Best suited for linear data structures
- May not work if elements outside the current window affect the result in nontrivial ways

Example
-------
**Find the maximum sum of a subarray of length `k`**:

Given an array and an integer `k`, the goal is to compute the maximum sum of any contiguous subarray of size `k`. The sliding window technique calculates the sum of the initial window and then slides the window forward one element at a time, adjusting the sum efficiently by adding the incoming element and subtracting the outgoing one.
