# 13. Advanced Data Structures (Segment Tree, Fenwick Tree, etc.)

---

## Introduction

Advanced data structures enable efficient solutions to complex problems involving queries and updates on arrays, intervals, and sequences. This module covers Segment Trees, Fenwick Trees (Binary Indexed Trees), Sparse Tables, and a brief overview of other advanced trees.

---

## 1. Segment Tree

### What is a Segment Tree?

A **Segment Tree** is a binary tree data structure that allows efficient range queries and updates on arrays, such as finding the sum, minimum, or maximum in a subarray.

- Supports queries and updates in O(log n) time.
- Common operations: range sum, range minimum/maximum, range gcd, range xor, etc.

### Construction

- The tree is built recursively by dividing the array into halves.
- Each node represents a segment (interval) of the array.

```python
class SegmentTree:
    def __init__(self, arr):
        self.n = len(arr)
        self.tree = [0] * (2 * self.n)
        for i in range(self.n):
            self.tree[self.n + i] = arr[i]
        for i in range(self.n - 1, 0, -1):
            self.tree[i] = self.tree[2 * i] + self.tree[2 * i + 1]

    def update(self, index, value):
        i = index + self.n
        self.tree[i] = value
        while i > 1:
            i //= 2
            self.tree[i] = self.tree[2 * i] + self.tree[2 * i + 1]

    def range_query(self, l, r):
        l += self.n
        r += self.n
        res = 0
        while l < r:
            if l % 2:
                res += self.tree[l]
                l += 1
            if r % 2:
                r -= 1
                res += self.tree[r]
            l //= 2
            r //= 2
        return res
```

### Applications

- Range sum/min/max/gcd queries
- Interval updates and queries
- Counting inversions

---

## 2. Fenwick Tree (Binary Indexed Tree, BIT)

### What is a Fenwick Tree?

A **Fenwick Tree** is a data structure that provides efficient methods for prefix sum queries and point updates.

- Supports point updates and prefix/range queries in O(log n) time.
- More space-efficient and simpler to implement than segment trees for prefix sums.

```python
class FenwickTree:
    def __init__(self, n):
        self.tree = [0] * (n + 1)

    def update(self, i, delta):
        while i < len(self.tree):
            self.tree[i] += delta
            i += (i & -i)

    def query(self, i):
        res = 0
        while i > 0:
            res += self.tree[i]
            i -= (i & -i)
        return res
```

### Applications

- Prefix/range sum queries
- Inversion count in arrays
- Frequency tables

---

## 3. Sparse Table

### What is a Sparse Table?

A **Sparse Table** is a data structure used for answering range queries (like minimum or maximum) on immutable arrays in O(1) time, after O(n log n) preprocessing.

- Efficient for static data (no updates).
- Often used for range minimum queries (RMQ).

```python
import math
def build_sparse_table(arr):
    n = len(arr)
    k = math.floor(math.log2(n)) + 1
    st = [[0]*n for _ in range(k)]
    for i in range(n):
        st[0][i] = arr[i]
    j = 1
    while (1 << j) <= n:
        i = 0
        while i + (1 << j) <= n:
            st[j][i] = min(st[j-1][i], st[j-1][i + (1 << (j-1))])
            i += 1
        j += 1
    return st
```

### Applications

- Range minimum/maximum queries in static arrays
- Lowest Common Ancestor (LCA) in trees

---

## 4. Self-Balancing Binary Search Trees

### AVL Tree

- Maintains height balance after insertions/deletions.
- Guarantees O(log n) time for search, insert, and delete.

### Red-Black Tree

- Each node is either red or black; rebalances using rotations and color flips.
- Used in many library implementations (e.g., C++ std::map, Java TreeMap).

---

## 5. Treap

A **Treap** is a randomized balanced BST, combining the properties of binary search trees and heaps.

- Maintains BST property by key and heap property by priority.
- Good for randomized balancing and fast expected O(log n) operations.

---

## 6. Other Advanced Structures

- **Splay Tree:** Self-adjusting BST with amortized O(log n) operations.
- **Interval Tree:** For overlapping interval queries.
- **Segment Tree with Lazy Propagation:** For efficient range updates.

---

## Comparison Table

| Structure       | Update | Query Range | Space  | Use Cases                        |
|-----------------|--------|-------------|--------|----------------------------------|
| Segment Tree    | O(logn)| O(logn)     | O(n)   | Dynamic range queries/updates    |
| Fenwick Tree    | O(logn)| O(logn)     | O(n)   | Prefix sums, frequency tables    |
| Sparse Table    | N/A    | O(1)        | O(nlogn)| Static range queries            |
| AVL/Red-Black   | O(logn)| O(logn)     | O(n)   | Ordered data, dynamic sets/maps  |

---

## Real-World Applications

- Database query engines
- Competitive programming (range query/update problems)
- Computational geometry
- Text editors (undo/redo, interval management)
- Event processing systems

---

## References

- [GeeksforGeeks: Segment Tree](https://www.geeksforgeeks.org/segment-tree-data-structure/)
- [GeeksforGeeks: Fenwick Tree](https://www.geeksforgeeks.org/binary-indexed-tree-or-fenwick-tree-2/)
- [GeeksforGeeks: Sparse Table](https://www.geeksforgeeks.org/sparse-table/)
- [Wikipedia: Segment tree](https://en.wikipedia.org/wiki/Segment_tree)
- [Wikipedia: Fenwick tree](https://en.wikipedia.org/wiki/Fenwick_tree)
- [Wikipedia: AVL tree](https://en.wikipedia.org/wiki/AVL_tree)
- [Wikipedia: Red–black tree](https://en.wikipedia.org/wiki/Red%E2%80%93black_tree)

---

## Exercises

1. Implement a segment tree for range minimum queries and updates.
2. Use a Fenwick Tree to find the number of inversions in an array.
3. Build a sparse table and answer range minimum queries.
4. Implement an AVL tree and test insertion and deletion.
5. Compare the performance of segment tree and Fenwick tree for sum queries.

---

Advanced data structures are essential for efficient problem-solving in high-performance and real-time systems. Practice implementing and applying them to master their power!
