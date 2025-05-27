# 01. Introduction to Data Structures

---

## What Are Data Structures?

A **data structure** is a way of organizing and storing data so that it can be accessed and modified efficiently. It provides a means to manage large amounts of data for tasks such as processing, searching, and retrieval.

---

## Why Are Data Structures Important?

- **Efficiency:** The right data structure can drastically improve the speed and memory usage of your programs.
- **Organization:** They help organize data logically and systematically.
- **Scalability:** Good data structures allow programs to handle more data and more users.
- **Problem Solving:** Many algorithmic problems require specific data structures.

---

## Categories of Data Structures

- **Primitive Data Structures:** Built-in types (int, float, char, boolean).
- **Non-Primitive Data Structures:** More complex; includes:
  - **Linear:** Arrays, Lists, Stacks, Queues
  - **Non-Linear:** Trees, Graphs
  - **Hash-based:** Hash Tables, Maps
  - **Specialized:** Heaps, Tries, Disjoint Sets, etc.

---

## Abstract Data Types (ADT)

An **Abstract Data Type** is a model for a data structure, defining its behavior (operations, constraints) but not its implementation.

**Examples:**
- Stack (push, pop, top)
- Queue (enqueue, dequeue, front)
- Set (add, remove, contains)

---

## Key Data Structure Operations

- **Insertion:** Adding a new element.
- **Deletion:** Removing an element.
- **Traversal:** Accessing each element.
- **Search:** Finding an element.
- **Update:** Modifying an element.

---

## Common Data Structures Overview

### 1. Arrays

- Contiguous memory, fixed size, quick access by index.

### 2. Linked Lists

- Each element points to the next; good for frequent insertions/deletions.

### 3. Stacks

- LIFO (Last In, First Out) structure; supports push/pop.

### 4. Queues

- FIFO (First In, First Out) structure; supports enqueue/dequeue.

### 5. Trees

- Hierarchical structure; binary trees, BSTs, heaps, tries.

### 6. Graphs

- Set of nodes (vertices) and edges; directed/undirected.

### 7. Hash Tables

- Key-value pairs with fast lookup using a hash function.

---

## Data Structure Choice Matters

**Example:**
- To store a list of tasks and retrieve the next task quickly → Use a queue.
- To manage browser history (back/forward) → Use two stacks.
- For fast search, insert, delete → Use a hash table or balanced BST.

---

## Space and Time Complexity

Data structure operations are analyzed by:
- **Time Complexity:** How operation time grows with data size.
- **Space Complexity:** How much extra memory is used.

**Big O Notation:** O(1), O(log n), O(n), O(n log n), O(n²), etc.

---

## Real-World Applications

- Social networks (graphs for users/friends)
- Databases (B-trees for indexing)
- Compilers (stacks for parsing)
- Routers (tries for IP routing)
- Games (queues for event handling)

---

## How to Choose the Right Data Structure

1. **Understand the problem’s requirements.**
2. **Analyze the operations needed most frequently.**
3. **Estimate performance constraints (speed, memory).**
4. **Test scalability and edge cases.**

---

## Illustration: Stack vs Queue

- **Stack Example (Backtracking in Maze):**
  - Push each move, pop when backtracking.
- **Queue Example (Breadth-First Search):**
  - Enqueue each node, process in order of arrival.

---

## Sample Interview Questions

- Implement a stack/queue using arrays or linked lists.
- How would you design a data structure for an LRU cache?
- Describe the difference between an array and a linked list.

---

## Further Reading

- [GeeksforGeeks: Data Structures](https://www.geeksforgeeks.org/data-structures/)
- [Wikipedia: Data structure](https://en.wikipedia.org/wiki/Data_structure)
- "Introduction to Algorithms" by Cormen, Leiserson, Rivest, Stein

---

## Exercises

1. List three real-world problems and suggest the best-suited data structure for each.
2. Implement a stack and a queue in your favorite language.
3. Compare the time complexity of searching in an array vs. a linked list.

---

## Summary Table

| Data Structure | Access | Search | Insertion | Deletion | Use Case Example           |
|----------------|--------|--------|-----------|----------|---------------------------|
| Array          | O(1)   | O(n)   | O(n)      | O(n)     | Store fixed-size data      |
| Linked List    | O(n)   | O(n)   | O(1)      | O(1)     | Dynamic memory allocation  |
| Stack          | O(n)   | O(n)   | O(1)      | O(1)     | Undo, parsing, DFS         |
| Queue          | O(n)   | O(n)   | O(1)      | O(1)     | Scheduling, BFS            |
| Hash Table     | N/A    | O(1)   | O(1)      | O(1)     | Fast lookup, dictionaries  |
| Tree           | O(logn)| O(logn)| O(logn)   | O(logn)  | Hierarchical data, indexes |
| Graph          | N/A    | O(V+E) | O(1)      | O(1)     | Networks, relationships    |

---

## Final Thoughts

Understanding data structures lays the groundwork for all algorithmic problem-solving. Choose wisely based on your problem's needs, and practice implementing them from scratch!

---
