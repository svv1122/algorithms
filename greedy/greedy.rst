======
Greedy
======
A greedy algorithm is a problem-solving approach that makes the locally optimal choice at each step with the hope of finding a global optimum. It builds up a solution piece by piece, always choosing the option that offers the most immediate benefit.

Key Characteristics
-------------------
- **Greedy Choice Property**: A global optimum can be arrived at by choosing the local optimum.
- **Optimal Substructure**: A problem has an optimal substructure if an optimal solution to the problem contains the optimal solutions to subproblems.

Applications
------------
Greedy algorithms are commonly used in:

- **Activity Selection Problem**
- **Fractional Knapsack Problem**
- **Huffman Coding**
- **Dijkstra's Algorithm**
- **Prim's Minimum Spanning Tree Algorithm**

Advantages
----------
- Simple to implement
- Often more efficient than other algorithms like dynamic programming

Disadvantages
-------------
- Does not always produce the optimal solution
- Problem must meet specific properties (greedy-choice and optimal substructure)

Example
-------
The **Fractional Knapsack Problem**:

Given items with weights and values, and a maximum weight capacity, the goal is to maximize the total value in the knapsack. The greedy approach sorts items by value-to-weight ratio and picks the highest first, possibly taking fractions of items.

