# 14. Backtracking and Recursion

---

## What is Recursion?

**Recursion** is a programming technique where a function calls itself directly or indirectly to solve a problem by breaking it down into subproblems.

- **Base Case:** The condition under which the recursion ends.
- **Recursive Case:** The part where the function calls itself.

---

### Example: Recursive Factorial (Python)

```python
def factorial(n):
    if n == 0:
        return 1
    return n * factorial(n-1)
```

---

## What is Backtracking?

**Backtracking** is an algorithmic technique for solving constraint satisfaction problems by incrementally building a solution and abandoning it ("backtracking") as soon as it determines that the solution cannot possibly be completed.

- Used to find all (or some) solutions to problems that incrementally build candidates for solutions.
- If a partial candidate leads to an invalid solution, the algorithm backtracks and tries a different path.

---

### Key Concepts

- **State Space Tree:** Represents all possible solutions.
- **Pruning:** Abandoning paths that cannot lead to a valid solution.
- **Recursive Exploration:** Backtracking is usually implemented with recursion.

---

## Common Backtracking Problems

- N-Queens problem
- Sudoku solver
- Subset sum and combinations
- Permutations and combinations of a set
- Word search in a grid
- Palindrome partitioning
- Generating valid parentheses

---

### Sample: N-Queens Problem (Python)

```python
def solve_n_queens(n):
    solutions = []
    board = [-1] * n

    def is_safe(row, col):
        for r in range(row):
            if board[r] == col or \
               abs(board[r] - col) == abs(r - row):
                return False
        return True

    def backtrack(row):
        if row == n:
            solutions.append(board[:])
            return
        for col in range(n):
            if is_safe(row, col):
                board[row] = col
                backtrack(row + 1)
                board[row] = -1

    backtrack(0)
    return solutions
```

---

## Steps for Solving Backtracking Problems

1. Define the solution space (what are the choices at each step?).
2. Write a recursive function that explores each choice.
3. Base case: Decision is complete or invalid.
4. If a choice is invalid, backtrack and try the next.
5. Collect or print solutions.

---

## Backtracking vs. Brute Force

- **Brute Force:** Tries all possible combinations, no pruning.
- **Backtracking:** Prunes invalid partial solutions early, much more efficient for constraint problems.

---

## Applications

- Puzzle solving (crossword, sudoku, n-queens)
- Combinatorial optimization
- Generating permutations/combinations
- Parsing and language processing

---

## Common Interview Questions

1. N-Queens and variations
2. Sudoku solver
3. Subsets, combinations, and permutations
4. Word search on a board
5. Palindrome partitioning
6. Generate all valid parentheses

---

## Quick Revision Table

| Technique      | Use Case                  | Implementation  | Typical Complexity      |
|----------------|--------------------------|-----------------|------------------------|
| Recursion      | Divide problem, DP, trees| Function calls  | Varies                 |
| Backtracking   | Constraint satisfaction  | Recursion + undo| Exponential (pruned)   |

---

## References

- [GeeksforGeeks: Backtracking](https://www.geeksforgeeks.org/backtracking-algorithms/)
- [LeetCode Backtracking Problems](https://leetcode.com/tag/backtracking/)
- [Wikipedia: Backtracking](https://en.wikipedia.org/wiki/Backtracking)

---

Happy Coding! 🔄
