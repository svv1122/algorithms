===================
Dynamic Programming
===================
**Dynamic programming (DP)** is a powerful algorithmic technique used to solve 
problems by breaking them down into simpler subproblems and storing the results 
of these subproblems to avoid redundant computation.

Key Features
------------
- **Optimal Substructure:** A problem exhibits optimal substructure if its 
  optimal solution can be constructed from optimal solutions of its subproblems.
- **Overlapping Subproblems:** The problem can be broken down into subproblems 
  which are reused multiple times.
- **Memoization and Tabulation:** Two strategies to store solutions:
  
  - **Memoization:** Top-down approach that stores results after computing them.
  - **Tabulation:** Bottom-up approach that solves all related subproblems first.

How It Works
------------
1. Identify the structure of the optimal solution.
2. Recursively define the value of the solution.
3. Compute the value of the solution in a bottom-up fashion.
4. Store the solutions of subproblems to avoid redundant calculations.

Common Applications
-------------------
- **Fibonacci Sequence Calculation**
- **Shortest Path Problems** (e.g., Dijkstra's algorithm with simple graphs)
- **Knapsack Problem**
- **Longest Common Subsequence (LCS)**
- **Matrix Chain Multiplication**
- **Coin Change Problem**

Basic Example
-------------
Computing the nth Fibonacci number using dynamic programming::

    def fibonacci(n):
        dp = [0] * (n + 1)
        dp[0] = 0
        dp[1] = 1
        for i in range(2, n + 1):
            dp[i] = dp[i-1] + dp[i-2]
        return dp[n]

    print(fibonacci(6))  # Output: 8

Advantages
----------
- Greatly improves performance for problems with overlapping subproblems.
- Reduces time complexity from exponential to polynomial in many cases.

Disadvantages
-------------
- Higher memory usage due to storage of subproblem results.
- Requires careful problem analysis to correctly identify subproblems.
