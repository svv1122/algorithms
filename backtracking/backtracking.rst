============
Backtracking
============
Backtracking is a general algorithmic technique that builds a solution incrementally and abandons ("backtracks") 
as soon as it determines that the current solution cannot be completed to a valid solution.

Key Characteristics
--------------------
- **Incremental Approach**: Solutions are built step-by-step, one component at a time.
- **Recursive Strategy**: Often implemented using recursion to explore all potential options.
- **Pruning**: If a partial solution is invalid, the algorithm abandons it and backtracks to a previous decision point.
- **Use Cases**:

  - Solving puzzles (e.g., Sudoku, N-Queens problem)
  - Finding paths (e.g., Maze solving)
  - Combinatorial optimization problems (e.g., Subset Sum, Hamiltonian Path)

General Steps
-------------
1. Choose a possible option.
2. Check if it leads to a valid partial solution.
3. If valid, continue to build the solution recursively.
4. If not valid or if the solution cannot be completed, backtrack and try a different option.

Example
-------
Consider solving a simple maze::

    def solve_maze(x, y, maze, solution):
        if (x, y) is the goal:
            return True
        for each direction (up, down, left, right):
            if move is valid:
                mark current cell as part of the solution
                if solve_maze(next_x, next_y, maze, solution):
                    return True
                unmark current cell (backtrack)
        return False

Visualization
--------------
::

    Try -> Check -> Recurse -> (Fail?) -> Backtrack -> Try Again -> (Success?)

Summary
-------
Backtracking systematically searches for a solution by exploring possible choices.
If a choice leads to failure, it retraces steps and tries alternatives, ensuring that 
every potential solution path is explored where necessary.
