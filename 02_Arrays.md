# 2. Arrays

---

## What is an Array?

An **array** is a collection of elements, each identified by their index or position. All elements are stored in contiguous memory locations and are of the same data type.

---

## Key Properties

- **Fixed Size:** Size is defined at the time of declaration (static arrays).
- **Random Access:** Any element can be accessed in O(1) time using its index.
- **Homogeneous:** All elements are of the same type.
- **Contiguous Memory:** Elements are stored in continuous memory blocks.

---

## Basic Operations

| Operation    | Description                     | Time Complexity |
|--------------|---------------------------------|-----------------|
| Access       | Retrieve element by index       | O(1)            |
| Update       | Change value at index           | O(1)            |
| Insert-End   | Add at the end (if space)       | O(1)            |
| Insert-Mid   | Insert at position (shift req.) | O(n)            |
| Delete-End   | Remove last element             | O(1)            |
| Delete-Mid   | Delete at position (shift req.) | O(n)            |
| Search       | Find element                    | O(n) (linear)   |

---

## Types of Arrays

- **1D Array:** Simple linear collection.
- **2D Array:** Array of arrays; used for matrices, grids, etc.
- **Dynamic Array (e.g. Vector in C++, ArrayList in Java, list in Python):** Can resize at runtime.

---

## Advantages

- Fast random access.
- Easy to implement and use.
- Efficient for tasks needing index-based operations.

---

## Disadvantages

- Fixed size (static arrays).
- Insertion/deletion (except at end) is costly due to shifting.
- Inefficient memory usage if size is much larger than required.

---

## Common Interview Questions

1. Reverse an array in-place.
2. Find the largest/smallest element.
3. Move all zeros to the end.
4. Find the missing number in a sequence.
5. Remove duplicates from a sorted/unsorted array.
6. Find pairs with a given sum.

---

## Sample Code: Reverse an Array (Python)

```python
def reverse_array(arr):
    left, right = 0, len(arr) - 1
    while left < right:
        arr[left], arr[right] = arr[right], arr[left]
        left += 1
        right -= 1
```

---

## Applications

- Lookup tables
- Buffers in OS and networking
- Matrices and grids (2D arrays)
- Storing data in contiguous memory for cache efficiency

---

## Quick Revision Table

| Feature           | Static Array       | Dynamic Array    |
|-------------------|-------------------|------------------|
| Size              | Fixed             | Grows/Shrinks    |
| Access            | O(1)              | O(1)             |
| Insert/Delete     | O(n) (except end) | Amortized O(1)   |
| Memory Efficiency | May waste space   | More efficient   |

---

## References

- [GeeksforGeeks: Arrays](https://www.geeksforgeeks.org/array-data-structure/)
- [Wikipedia: Array Data Structure](https://en.wikipedia.org/wiki/Array_data_structure)

---

Happy Coding! 🚀
