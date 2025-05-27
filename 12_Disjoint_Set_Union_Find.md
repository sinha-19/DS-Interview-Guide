# 12. Disjoint Set (Union Find)

---

## Introduction

A **Disjoint Set** (also known as **Union Find** or **Disjoint Set Union, DSU**) is a data structure that keeps track of a set of elements partitioned into a number of non-overlapping (disjoint) subsets. It is mainly used to answer queries of the form "are these two elements in the same set?" and to merge sets efficiently.

---

## Why Is It Important?

Disjoint Set is fundamental in solving problems related to connectivity, grouping, and partitioning. It is widely used in algorithms like Kruskal's Minimum Spanning Tree, network connectivity, image processing, and more.

---

## Basic Operations

1. **MakeSet(x):** Create a set with a single element x.
2. **Find(x):** Determine the "representative" of the set containing x.
3. **Union(x, y):** Merge the sets containing x and y.

The primary goal is to make both `Find` and `Union` operations efficient.

---

## Data Structure

Each set is typically represented by a rooted tree, where each node points to its parent. The root of the tree is the representative of the set.

### Naive Implementation

```python
parent = [i for i in range(n)]  # Initially, each element is its own parent

def find(x):
    if parent[x] == x:
        return x
    return find(parent[x])

def union(x, y):
    x_root = find(x)
    y_root = find(y)
    if x_root != y_root:
        parent[x_root] = y_root
```

---

## Optimizations

### 1. Path Compression

During `Find`, make each node on the path point directly to the root. This flattens the structure, speeding up subsequent operations.

```python
def find(x):
    if parent[x] != x:
        parent[x] = find(parent[x])  # Path compression
    return parent[x]
```

### 2. Union by Rank / Size

Always attach the smaller tree under the root of the larger tree. This keeps the trees shallow.

```python
rank = [0] * n

def union(x, y):
    x_root = find(x)
    y_root = find(y)
    if x_root == y_root:
        return
    if rank[x_root] < rank[y_root]:
        parent[x_root] = y_root
    else:
        parent[y_root] = x_root
        if rank[x_root] == rank[y_root]:
            rank[x_root] += 1
```

---

## Time Complexity

- Naive approach: Nearly O(n) per operation in worst case.
- With path compression and union by rank/size: **Amortized O(α(n))** per operation, where α(n) is the extremely slow-growing inverse Ackermann function (practically constant).

---

## Applications

- **Kruskal's Algorithm:** Build Minimum Spanning Trees by merging components.
- **Connected Components:** Count or identify connected groups in a graph.
- **Cycle Detection:** Detect cycles in undirected graphs.
- **Network Connectivity:** Check if two nodes are in the same network.
- **Image Processing:** Label connected regions.
- **Percolation Theory:** Model connectivity in physics and materials science.

---

## Example: Kruskal’s Algorithm

1. Sort all edges by weight.
2. For each edge, if the nodes are in different sets, add the edge and union their sets.
3. Stop when all nodes are connected.

---

## Example: Connected Components in a Graph

```python
def count_components(n, edges):
    parent = [i for i in range(n)]
    def find(x):
        if parent[x] != x:
            parent[x] = find(parent[x])
        return parent[x]
    def union(x, y):
        parent[find(x)] = find(y)
    for u, v in edges:
        union(u, v)
    return len(set(find(x) for x in range(n)))
```

---

## Real-World Problems

- Social network clusters (friend groups)
- Dynamic connectivity queries
- Maze and puzzle solving (grouping cells)
- Image segmentation

---

## Practice Questions

1. Number of connected components in a graph.
2. Friend circles problem (LeetCode 547).
3. Redundant connection (cycle detection in a graph).
4. Similar string groups (LeetCode 839).

---

## Comparison with Other Structures

| Feature              | Disjoint Set | Hash Set | Tree Set (BST) |
|----------------------|-------------|----------|----------------|
| Fast union/find      | Yes         | No       | No             |
| Fast insert/delete   | Yes         | Yes      | Yes            |
| Maintains order      | No          | No       | Yes            |
| Use for grouping     | Yes         | No       | No             |

---

## Best Practices

- Always use path compression and union by rank/size in competitive programming.
- For static graphs, preprocess unions before answering queries.
- For dynamic groups, DSU is almost always the best choice.

---

## References

- [GeeksforGeeks: Disjoint Set (Union-Find)](https://www.geeksforgeeks.org/disjoint-set-data-structures/)
- [Wikipedia: Disjoint-set data structure](https://en.wikipedia.org/wiki/Disjoint-set_data_structure)
- [LeetCode DSU Problems](https://leetcode.com/tag/union-find/)

---

## Exercises

1. Implement a DSU class with path compression and union by rank.
2. Given a list of friendships, count the number of friend circles.
3. Detect if adding an edge creates a cycle in an undirected graph.
4. Implement Kruskal’s algorithm for Minimum Spanning Tree.

---

Disjoint Set Union is a powerful and efficient structure for partitioning, grouping, and connectivity problems—master it for advanced graph algorithms and real-world applications!
