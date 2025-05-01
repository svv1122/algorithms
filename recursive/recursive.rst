=========
Recursive
=========
A recursive algorithm is an approach to solving problems where the solution depends on solutions to smaller instances of the same problem. It solves a problem by calling itself with simpler inputs and combining the results.

Each recursive algorithm has at least two parts:

1. **Base Case**: The simplest, smallest instance of the problem which can be solved directly without recursion.
2. **Recursive Case**: The part of the algorithm where the function calls itself with a modified input that progresses toward the base case.

Key Characteristics
-------------------
- **Self-Referential**: The algorithm defines the solution in terms of itself.
- **Divide and Conquer**: Many recursive algorithms break a problem into subproblems, solve each recursively, and then combine the results.
- **Stack-Based Execution**: Each recursive call is stored on the call stack until the base case is reached.

Applications
------------
Recursive algorithms are commonly used in:

- **Mathematical computations** (e.g., factorial, Fibonacci numbers)
- **Data structures** like trees and graphs
- **Backtracking algorithms** (e.g., solving puzzles, searching)
- **Divide and conquer algorithms** (e.g., merge sort, quicksort)
- **Dynamic programming with memoization**

Advantages
----------
- Natural fit for problems that are recursive in structure
- Code is often simpler and easier to understand
- Useful for problems involving tree traversal and branching

Disadvantages
-------------
- Can lead to excessive memory usage due to call stack growth
- May be less efficient without optimization (e.g., tail recursion, memoization)
- Risk of infinite recursion if the base case is not correctly defined

Example
-------
**Factorial Function**:

The factorial of a non-negative integer `n` is defined as:
::

    def factorial(n):
        if n == 0 or n == 1:
            return 1
        else:
            return n * factorial(n - 1)

In this example, `factorial(n)` calls itself with `n - 1` until it reaches the base case where `n` is 0 or 1.
