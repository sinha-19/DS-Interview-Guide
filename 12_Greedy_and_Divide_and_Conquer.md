# 12. Greedy Algorithms and Divide & Conquer

---

## Greedy Algorithms

### What is a Greedy Algorithm?

A **greedy algorithm** makes a series of choices, each of which simply looks the best at the moment (locally optimal), in hopes that this leads to a globally optimal solution.

---

### Key Properties

- **Greedy Choice Property:** A global optimum can be arrived at by selecting a local optimum.
- **Optimal Substructure:** Optimal solution to the problem contains optimal solutions to subproblems.

---

### Common Applications

- Activity selection problem
- Fractional knapsack
- Huffman coding (compression)
- Dijkstra’s shortest path algorithm (for non-negative weights)
- Minimum spanning tree (Kruskal’s, Prim’s)
- Job sequencing with deadlines
- Coin change (when denominations are canonical)

---

### Sample: Activity Selection (Python)

```python
def activity_selection(activities):
    # activities: list of (start, finish) tuples
    activities.sort(key=lambda x: x[1])
    last_end = -1
    count = 0
    for start, end in activities:
        if start >= last_end:
            count += 1
            last_end = end
    return count
```

---

### Advantages

- Simple and easy to implement
- Often efficient (O(n log n) or O(n))
- Good for problems with proven greedy correctness

### Limitations

- Not all problems can be solved optimally by greedy approach (e.g., 0/1 knapsack, TSP)

---

## Divide and Conquer

### What is Divide and Conquer?

**Divide and conquer** is an algorithmic paradigm that solves a problem by:
1. Dividing it into subproblems,
2. Solving each subproblem recursively,
3. Combining their solutions to solve the original problem.

---

### Steps

1. **Divide:** Break problem into smaller subproblems.
2. **Conquer:** Solve subproblems (recursively).
3. **Combine:** Merge solutions of subproblems.

---

### Common Applications

- Merge Sort
- Quick Sort
- Binary Search
- Closest Pair of Points
- Karatsuba multiplication
- Strassen’s matrix multiplication

---

### Sample: Merge Sort (Python)

```python
def merge_sort(arr):
    if len(arr) > 1:
        mid = len(arr) // 2
        L = arr[:mid]
        R = arr[mid:]
        merge_sort(L)
        merge_sort(R)
        i = j = k = 0
        while i < len(L) and j < len(R):
            if L[i] < R[j]:
                arr[k] = L[i]
                i += 1
            else:
                arr[k] = R[j]
                j += 1
            k += 1
        while i < len(L):
            arr[k] = L[i]
            i += 1
            k += 1
        while j < len(R):
            arr[k] = R[j]
            j += 1
            k += 1
```

---

### Advantages

- Breaks complex problems into manageable subproblems
- Enables efficient algorithms (O(n log n) for sorting)
- Naturally suited for recursion

### Limitations

- May use more memory (e.g., merge sort’s extra arrays)
- Not always more efficient than iterative counterparts for small subproblems

---

## Quick Revision Table

| Paradigm           | Approach             | Examples                        | Complexity (Typical) |
|--------------------|---------------------|---------------------------------|----------------------|
| Greedy             | Local optimum       | Prim, Kruskal, Dijkstra, Huffman| O(n log n)           |
| Divide & Conquer   | Split & merge       | Merge sort, Quick sort, Binary Search | O(n log n)     |

---

## References

- [GeeksforGeeks: Greedy Algorithms](https://www.geeksforgeeks.org/greedy-algorithms/)
- [GeeksforGeeks: Divide and Conquer](https://www.geeksforgeeks.org/divide-and-conquer-algorithm/)
- [Wikipedia: Greedy Algorithm](https://en.wikipedia.org/wiki/Greedy_algorithm)
- [Wikipedia: Divide and Conquer](https://en.wikipedia.org/wiki/Divide-and-conquer_algorithm)

---

Happy Coding! ⚡
