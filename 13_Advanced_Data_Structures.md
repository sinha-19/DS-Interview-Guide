# 13. Advanced Data Structures (Segment Tree, Fenwick Tree, etc.)

---

## Segment Tree

A **Segment Tree** is a binary tree that allows efficient range queries (like sum, min, max) and point/range updates in O(log n) time.

### Example (Range Sum Query)

```python
class SegmentTree:
    def __init__(self, arr):
        n = len(arr)
        self.n = n
        self.tree = [0] * (2 * n)
        for i in range(n):
            self.tree[n + i] = arr[i]
        for i in range(n - 1, 0, -1):
            self.tree[i] = self.tree[2 * i] + self.tree[2 * i + 1]

    def update(self, pos, value):
        pos += self.n
        self.tree[pos] = value
        while pos > 1:
            pos //= 2
            self.tree[pos] = self.tree[2 * pos] + self.tree[2 * pos + 1]

    def range_sum(self, l, r):
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

---

## Fenwick Tree (Binary Indexed Tree)

A **Fenwick Tree** efficiently computes prefix sums and handles point updates in O(log n) time.

### Example (Prefix Sum Query)

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

---

## Other Advanced Structures

- **Sparse Table:** For immutable range queries (O(1) query, O(n log n) build)
- **Self-Balancing Trees:** AVL, Red-Black, Treap, Splay

---

## Applications

- Range query problems (sum, min, max)
- Inversion count in arrays
- Dynamic order statistics
- Efficient interval management

---

## References

- [GeeksforGeeks: Segment Tree](https://www.geeksforgeeks.org/segment-tree-data-structure/)
- [GeeksforGeeks: Fenwick Tree](https://www.geeksforgeeks.org/binary-indexed-tree-or-fenwick-tree-2/)
- [Wikipedia: Segment tree](https://en.wikipedia.org/wiki/Segment_tree)
- [Wikipedia: Fenwick tree](https://en.wikipedia.org/wiki/Fenwick_tree)
