# 13. Dynamic Programming (DP)

---

## What is Dynamic Programming?

**Dynamic Programming (DP)** is an algorithmic paradigm for solving complex problems by breaking them down into simpler overlapping subproblems and storing the results of subproblems to avoid redundant computation.

---

## Key Properties

- **Optimal Substructure:** The optimal solution of a problem can be constructed from optimal solutions of its subproblems.
- **Overlapping Subproblems:** The problem can be broken down into subproblems which are reused multiple times.

---

## DP Approaches

| Approach      | Description                                  | Example           |
|---------------|----------------------------------------------|-------------------|
| Top-Down      | Recursion + Memoization (store results)      | Fibonacci, LCS    |
| Bottom-Up     | Iterative, build table from smallest subprobs | Coin change, LIS  |
| Tabulation    | Fill DP table iteratively                    | Knapsack, Edit Distance |

---

## Steps to Solve DP Problems

1. **Identify subproblems** and state recurrence relation.
2. **Decide DP state(s)** (parameters that define a subproblem).
3. **Choose approach:** Top-down (memoization) or bottom-up (tabulation).
4. **Define base cases.**
5. **Implement storage:** Array, 2D array, hash map, etc.
6. **Build up to the original problem.**

---

## Classic Examples

### 1. Fibonacci Numbers

- **Recursion:** O(2ⁿ) (inefficient)
- **DP (Memoization/Tabulation):** O(n)

```python
def fib(n, memo={}):
    if n <= 1:
        return n
    if n not in memo:
        memo[n] = fib(n-1, memo) + fib(n-2, memo)
    return memo[n]
```

### 2. 0/1 Knapsack Problem

- Given weights and values, maximize value without exceeding weight.
- DP State: dp[i][w] = max value using first i items with max weight w.

### 3. Longest Common Subsequence (LCS)

```python
def lcs(X, Y):
    m, n = len(X), len(Y)
    dp = [[0]*(n+1) for _ in range(m+1)]
    for i in range(m):
        for j in range(n):
            if X[i] == Y[j]:
                dp[i+1][j+1] = dp[i][j]+1
            else:
                dp[i+1][j+1] = max(dp[i][j+1], dp[i+1][j])
    return dp[m][n]
```

### 4. Edit Distance (Levenshtein Distance)

---

## Common DP Patterns

- **Fibonacci-type:** Recurrence with previous states (fib, climb stairs).
- **Subsets:** Subset sum, knapsack.
- **Sequences:** Longest increasing, common subsequence.
- **Grids:** Unique paths, minimum path sum.
- **Partition:** Palindrome partitioning, word break.

---

## Applications

- String algorithms (LCS, edit distance)
- Resource allocation (knapsack)
- Game theory (minimax DP)
- Optimization problems (matrix chain multiplication)
- Combinatorics (counting ways, tiling)

---

## Common Interview Questions

1. Coin change (min coins/ways to make amount)
2. House robber (max sum non-adjacent)
3. Longest increasing subsequence
4. Palindrome partitioning
5. Decode ways (like number to alphabet)
6. DP on trees (max path sum)

---

## Quick Revision Table

| Problem Type       | State Example        | Time Complexity   | Space Complexity   |
|--------------------|---------------------|-------------------|--------------------|
| 1D DP              | dp[n]               | O(n)              | O(n)               |
| 2D DP              | dp[i][j]            | O(n*m)            | O(n*m)             |
| Knapsack           | dp[i][w]            | O(nW)             | O(nW)              |
| Memoization        | Recursion + cache   | Varies            | Varies             |

---

## References

- [GeeksforGeeks: Dynamic Programming](https://www.geeksforgeeks.org/dynamic-programming/)
- [LeetCode Patterns: Dynamic Programming](https://leetcode.com/tag/dynamic-programming/)
- [Wikipedia: Dynamic Programming](https://en.wikipedia.org/wiki/Dynamic_programming)

---

Happy Coding! 💡
