# 12. Disjoint Set (Union Find)

---

## Overview

The **Disjoint Set Union (DSU)** data structure (also called Union-Find) efficiently tracks a set of elements partitioned into multiple non-overlapping subsets. It is widely used for grouping, connected components, and cycle detection.

---

## Core Operations

- **Find:** Determine the representative ("parent") of the set containing an element.
- **Union:** Merge two subsets into a single subset.
- **Connected:** Check if two elements are in the same subset.

---

## Optimizations

- **Path Compression:** Flattens the structure of the tree whenever Find is called, making future operations faster.
- **Union by Rank/Size:** Always attach the smaller tree to the root of the larger tree.

---

## Example: Implementation in Python

```python
class DSU:
    def __init__(self, n):
        self.parent = [i for i in range(n)]
        self.rank = [1] * n

    def find(self, x):
        if self.parent[x] != x:
            self.parent[x] = self.find(self.parent[x])  # Path compression
        return self.parent[x]

    def union(self, x, y):
        xr, yr = self.find(x), self.find(y)
        if xr == yr:
            return False
        if self.rank[xr] < self.rank[yr]:
            self.parent[xr] = yr
        elif self.rank[yr] < self.rank[xr]:
            self.parent[yr] = xr
        else:
            self.parent[yr] = xr
            self.rank[xr] += 1
        return True
```

---

## Applications

- Kruskal’s algorithm (Minimum Spanning Tree)
- Connected components in undirected graphs
- Cycle detection in undirected graphs
- Network connectivity
- Image processing (e.g., finding connected regions)

---

## Interview Questions

1. Find the number of connected components in a graph.
2. Given a list of equations (a==b), check if all are satisfiable.
3. Given a grid, count the number of islands (connected regions).
4. Implement union-find with path compression and union by size.

---

## References

- [GeeksforGeeks: Disjoint Set Data Structures](https://www.geeksforgeeks.org/disjoint-set-data-structures/)
- [Wikipedia: Disjoint-set data structure](https://en.wikipedia.org/wiki/Disjoint-set_data_structure)
- [LeetCode Union Find Problems](https://leetcode.com/tag/union-find/)

---
