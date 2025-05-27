# 9. Hashing & Hash Tables

---

## What is Hashing?

**Hashing** is a technique that maps data of arbitrary size to a fixed-size value (hash code) using a hash function.  
Hashing enables efficient data lookup, insertion, and deletion.

---

## What is a Hash Table?

A **hash table** is a data structure that uses a hash function to compute an index (the hash code) into an array of buckets or slots, from which the desired value can be found.

---

## Key Properties

- **Key-Value Pair Storage:** Stores data as key-value pairs.
- **Fast Operations:** Average O(1) time for insert, delete, and search.
- **Hash Function:** Maps keys to array indices.
- **Collision Handling:** Multiple keys may map to the same index (collision).

---

## Hash Functions

- Should distribute keys uniformly across the table.
- Examples: Division method (`key % table_size`), Multiplication method, Cryptographic hash functions (SHA, MD5 for security, not for hash tables).

---

## Collision Resolution Methods

| Method               | Description                                              |
|----------------------|---------------------------------------------------------|
| **Chaining**         | Each bucket holds a linked list of entries              |
| **Open Addressing**  | Find another open slot (e.g., linear probing, quadratic probing, double hashing) |

---

## Basic Operations and Complexity

| Operation | Average Time | Worst Case Time |
|-----------|-------------|-----------------|
| Insert    | O(1)        | O(n)            |
| Delete    | O(1)        | O(n)            |
| Search    | O(1)        | O(n)            |

Worst case (all keys collide) is rare if hash function and table size are good.

---

## Load Factor

- **Definition:** `load_factor = (number of elements) / (table size)`
- As load factor increases, performance degrades.
- **Rehashing:** When load factor exceeds a threshold (e.g., 0.7), increase table size and rehash all keys.

---

## Common Interview Questions

1. Implement a hash map from scratch.
2. Find the first non-repeating character in a string.
3. Check if two arrays are disjoint.
4. Count pairs with a given sum.
5. Longest consecutive sequence in an array.
6. Group anagrams together.

---

## Sample: Python Dictionary

```python
# Hash table in Python (dictionary)
my_map = {}
my_map['apple'] = 1
print(my_map['apple'])  # 1
del my_map['apple']
```

---

## Applications

- Caching (LRU cache)
- Databases (indexing)
- Implementing sets, dictionaries
- Counting frequencies
- Detecting duplicates

---

## Quick Revision Table

| Feature               | Hash Table      | BST Map       |
|-----------------------|----------------|---------------|
| Lookup                | O(1) avg       | O(log n)      |
| Ordered?              | No             | Yes           |
| Collision Handling    | Yes            | N/A           |
| Space Efficiency      | May waste      | Tight         |

---

## References

- [GeeksforGeeks: Hashing](https://www.geeksforgeeks.org/hashing-data-structure/)
- [Wikipedia: Hash Table](https://en.wikipedia.org/wiki/Hash_table)

---

Happy Coding! 🔑
