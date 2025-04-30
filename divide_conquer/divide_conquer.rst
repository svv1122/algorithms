==================
Divide and Conquer
==================
**Divide and Conquer** is an algorithm design paradigm that solves a problem by recursively breaking it down into smaller subproblems, solving each subproblem independently, and then combining their solutions to solve the original problem.

This approach is especially useful for problems that can be divided into smaller instances of the same problem type.

Key Steps
---------
1. **Divide**: Break the problem into smaller subproblems of the same type.
2. **Conquer**: Solve the subproblems recursively. If the subproblem sizes are small enough, solve them directly.
3. **Combine**: Merge the solutions of the subproblems to form the solution to the original problem.

Example (Merge Sort in Python):
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
            if left[i] < right[j]:
                result.append(left[i])
                i += 1
            else:
                result.append(right[j])
                j += 1
        result.extend(left[i:])
        result.extend(right[j:])
        return result

Advantages
----------
- Often leads to efficient algorithms with good time complexity.
- Breaks complex problems into simpler subparts.
- Naturally suited to recursive implementation.

Common Applications
-------------------
- Sorting algorithms: Merge Sort, Quick Sort
- Searching: Binary Search
- Matrix multiplication: Strassen’s algorithm
- Computational geometry: Closest pair of points, Convex hull
