# 08. Heaps & Priority Queues

---

## What is a Heap?

A **heap** is a specialized binary tree-based data structure that satisfies the heap property.

- **Min heap:** Parent’s value ≤ child’s value.
- **Max heap:** Parent’s value ≥ child’s value.
- Always a complete binary tree.

---

## Heap Operations

| Operation      | Time Complexity |
|----------------|----------------|
| Insert         | O(log n)        |
| Get min/max    | O(1)            |
| Remove min/max | O(log n)        |
| Heapify        | O(n)            |

---

## Heap Implementation (Python)

```python
import heapq
heap = []
heapq.heappush(heap, 4)
heapq.heappush(heap, 1)
heapq.heappush(heap, 3)
min_elem = heapq.heappop(heap)  # 1
```

- For max heap: insert negatives or use custom comparator.

---

## Priority Queue

A **priority queue** is an abstract data type where each element is associated with a priority, and elements are served according to their priority.

- Usually implemented with a heap.
- Used for scheduling, algorithms (Dijkstra, A*), real-time processing.

### Example (Python)

```python
import heapq
pq = []
heapq.heappush(pq, (2, 'task2'))
heapq.heappush(pq, (1, 'task1'))
priority, task = heapq.heappop(pq)  # (1, 'task1')
```

---

## Heap Applications

- Heap sort
- Priority scheduling
- Dijkstra and A* shortest path
- Kth largest/smallest element
- Streaming median

---

## Heapify Algorithm

- Convert array into heap in O(n) time.

```python
import heapq
arr = [3, 1, 4, 1, 5]
heapq.heapify(arr)
```

---

## Building a Heap Manually

```python
def heapify(arr, n, i):
    largest = i
    l = 2*i + 1
    r = 2*i + 2
    if l < n and arr[l] > arr[largest]:
        largest = l
    if r < n and arr[r] > arr[largest]:
        largest = r
    if largest != i:
        arr[i], arr[largest] = arr[largest], arr[i]
        heapify(arr, n, largest)
```

---

## Interview Patterns

- Merge k sorted lists (min heap)
- Top k elements (min or max heap)
- Sliding window maximum (max heap)
- Median maintenance (two heaps)

---

## Real-World Applications

- Event simulation systems
- Operating system schedulers
- Bandwidth management
- Artificial intelligence (A* search)

---

## Common Interview Questions

1. Implement a min/max heap.
2. Find k largest/smallest elements in array.
3. Merge k sorted lists/arrays.
4. Find the median from a data stream.

---

## References

- [GeeksforGeeks: Heap Data Structure](https://www.geeksforgeeks.org/heap-data-structure/)
- [Python heapq module](https://docs.python.org/3/library/heapq.html)
- [Wikipedia: Heap (data structure)](https://en.wikipedia.org/wiki/Heap_(data_structure))

---

## Exercises

1. Implement heap sort.
2. Design a priority queue class.
3. Find k closest points to the origin.

---

Heaps and priority queues are vital for efficient priority management and scheduling—master their use for advanced algorithms!
