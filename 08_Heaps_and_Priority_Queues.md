# 8. Heaps and Priority Queues

---

## What is a Heap?

A **heap** is a specialized, complete binary tree-based data structure that satisfies the heap property:
- **Max-Heap:** The value of each node is greater than or equal to its children (root is maximum).
- **Min-Heap:** The value of each node is less than or equal to its children (root is minimum).

**Complete Binary Tree:** All levels are completely filled except possibly the last, which is filled from left to right.

---

## Heap Operations and Complexity

| Operation      | Description                          | Time Complexity |
|----------------|--------------------------------------|-----------------|
| Insertion      | Add new element and restore heap     | O(log n)        |
| Deletion       | Remove root and restore heap         | O(log n)        |
| Peek/getTop    | Get max/min (root)                   | O(1)            |
| Heapify        | Build heap from array                 | O(n)            |

---

## Implementation

- **Array Representation:** Heaps are usually implemented as arrays.
  - For node at index `i`:
    - Left child: `2*i + 1`
    - Right child: `2*i + 2`
    - Parent: `(i - 1) // 2`

### Example: Min-Heap Insertion (Python)

```python
import heapq
heap = []
heapq.heappush(heap, 10)
heapq.heappush(heap, 5)
heapq.heappush(heap, 20)
min_val = heapq.heappop(heap)  # Removes and returns min element
```

### Max-Heap in Python
Python's `heapq` is a min-heap. For max-heap, insert negative values.

```python
heapq.heappush(heap, -item)  # Use negative values for max-heap
```

---

## What is a Priority Queue?

A **priority queue** is an abstract data type where each element is associated with a priority, and elements with higher priority are served before elements with lower priority.

- **Heap** is the most common and efficient way to implement priority queues.

---

## Applications

- CPU scheduling (priority queues)
- Dijkstra’s shortest path algorithm (min-heap)
- Heap sort (sorting algorithm)
- Event-driven simulation
- Data stream (Top-K elements)
- Median maintenance (two heaps)

---

## Common Interview Questions

1. Implement a min-heap/max-heap.
2. Find the kth largest/smallest element in an array.
3. Merge k sorted arrays/lists.
4. Find median from a data stream.
5. Implement a priority queue with custom comparator.

---

## Sample: Heap Sort (Python)

```python
def heap_sort(arr):
    import heapq
    heapq.heapify(arr)
    sorted_arr = [heapq.heappop(arr) for _ in range(len(arr))]
    return sorted_arr
```

---

## Quick Revision Table

| Structure        | Property                        | Use Cases                   |
|------------------|---------------------------------|-----------------------------|
| Min-Heap         | Parent ≤ Children               | Dijkstra, merge k lists     |
| Max-Heap         | Parent ≥ Children               | Priority queues, Top-K      |
| Priority Queue   | Serves higher priority first    | Scheduling, algorithms      |

---

## References

- [GeeksforGeeks: Heap Data Structure](https://www.geeksforgeeks.org/heap-data-structure/)
- [Wikipedia: Heap (data structure)](https://en.wikipedia.org/wiki/Heap_(data_structure))
- [GeeksforGeeks: Priority Queue](https://www.geeksforgeeks.org/priority-queue-set-1-introduction/)

---

Happy Coding! 🚀
