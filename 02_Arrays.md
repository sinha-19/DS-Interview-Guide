# 02. Arrays

---

## What is an Array?

An **array** is a collection of items stored at contiguous memory locations. The idea is to store multiple items of the same type together, allowing easy access via indices.

---

## Features

- **Fixed size:** The size of an array is determined at creation.
- **Zero-based indexing:** The first element has index 0.
- **Homogeneous:** All elements must be of the same data type.
- **Contiguous memory allocation:** Enables fast random access.

---

## Array Declaration & Initialization

### C/C++ Example

```c
int arr[5];          // Declaration
int arr[5] = {1,2,3,4,5}; // Initialization
```

### Python Example

```python
arr = [1, 2, 3, 4, 5]
```

---

## Common Operations and Their Complexities

| Operation        | Time Complexity |
|------------------|----------------|
| Access by index  | O(1)           |
| Update by index  | O(1)           |
| Search (linear)  | O(n)           |
| Insert at end    | O(1) (amortized, dynamic arrays) |
| Insert at index  | O(n)           |
| Delete at index  | O(n)           |

---

## Advantages

- **Fast access:** O(1) time for access and update.
- **Memory efficiency:** Contiguous allocation helps with cache locality.

## Limitations

- **Fixed size:** Cannot grow or shrink after allocation (in static arrays).
- **Costly insertion/deletion:** O(n) time for insert/delete (except at the end).
- **Homogeneous:** Cannot store multiple data types.

---

## Types of Arrays

- **One-dimensional (1D):** Linear arrangement.
- **Multi-dimensional (2D, 3D):** Arrays within arrays, used for matrices, grids, etc.
- **Dynamic arrays:** Arrays that resize (e.g., Python lists, Java ArrayList, C++ vector).

---

## Common Array Algorithms

### 1. Reverse an Array

```python
arr = [1, 2, 3, 4, 5]
arr.reverse()
# or
arr = arr[::-1]
```

### 2. Find the Maximum Element

```python
max_val = arr[0]
for x in arr:
    if x > max_val:
        max_val = x
```

### 3. Rotate Array by k Steps

```python
def rotate(arr, k):
    n = len(arr)
    k %= n
    arr[:] = arr[-k:] + arr[:-k]
```

### 4. Remove Duplicates (Sorted Array)

```python
def remove_duplicates(arr):
    if not arr:
        return 0
    j = 0
    for i in range(1, len(arr)):
        if arr[i] != arr[j]:
            j += 1
            arr[j] = arr[i]
    return j + 1
```

---

## Use Cases

- Store a list of items (numbers, objects, etc.)
- Lookup tables
- Buffers in streaming data
- Matrices and grid-based problems

---

## Multi-dimensional Arrays

### 2D Array Example (Matrix Multiplication)

```python
A = [[1, 2], [3, 4]]
B = [[5, 6], [7, 8]]
result = [[0 for _ in range(2)] for _ in range(2)]
for i in range(2):
    for j in range(2):
        for k in range(2):
            result[i][j] += A[i][k] * B[k][j]
```

---

## Interview Patterns

- **Sliding window:** Find subarrays with given sum/maximum/minimum.
- **Two pointer:** Partition, move zeros, pair sum.
- **Prefix sum:** Fast range sum queries.

---

## Real-World Applications

- Image processing (pixels in 2D arrays)
- Board games (chess, sudoku)
- Scheduling (timetables)
- Data analysis (time series, tabular data)

---

## Common Interview Questions

1. Find the largest/smallest element in an array.
2. Find the "Kth" largest/smallest element.
3. Rotate an array.
4. Search in a rotated sorted array.
5. Implement dynamic array (resize on demand).
6. Remove duplicates from sorted array.

---

## Best Practices

- Use built-in array/list types where possible (Python, Java, etc.).
- Avoid manual resizing; use dynamic arrays if available.
- For large datasets, consider memory usage and cache performance.

---

## References

- [GeeksforGeeks: Arrays](https://www.geeksforgeeks.org/arrays-in-c-cpp/)
- [Wikipedia: Array Data Structure](https://en.wikipedia.org/wiki/Array_data_structure)
- [Python Lists](https://docs.python.org/3/tutorial/datastructures.html#more-on-lists)

---

## Exercises

1. Implement a function to reverse an array in-place.
2. Write code to find the majority element (element appearing more than n/2 times).
3. Given an array, find the maximum sum subarray (Kadane’s Algorithm).

---

## Summary Table

| Operation     | Static Array | Dynamic Array (Python list) |
|---------------|-------------|-----------------------------|
| Access        | O(1)        | O(1)                        |
| Insert End    | O(n)        | O(1) amortized              |
| Insert Middle | O(n)        | O(n)                        |
| Delete       | O(n)        | O(n)                        |
| Search        | O(n)        | O(n)                        |

---

**Arrays are the foundation of many other data structures. Master their use and manipulation to boost your coding skills!**
