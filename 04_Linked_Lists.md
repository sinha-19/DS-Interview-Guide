# 4. Linked Lists

---

## What is a Linked List?

A **linked list** is a linear data structure where elements (nodes) are stored in non-contiguous memory locations. Each node contains data and a reference (pointer) to the next node in the sequence.

---

## Types of Linked Lists

- **Singly Linked List:** Each node points to the next node.
- **Doubly Linked List:** Each node points to both the next and previous node.
- **Circular Linked List:** Last node points back to the first node (can be singly or doubly).

---

## Basic Structure (Singly Linked List Example in Python)

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
```

---

## Key Operations & Complexity

| Operation      | Description                         | Time Complexity |
|----------------|-------------------------------------|-----------------|
| Insertion      | At head: O(1), At tail: O(n)        |                 |
| Deletion       | Given node: O(1), By value: O(n)    |                 |
| Search         | Find an element                     | O(n)            |
| Traversal      | Visit all elements                  | O(n)            |
| Reverse        | Reverse the list                    | O(n)            |

---

## Advantages

- Dynamic size (no need to define size at creation).
- Easy insertion and deletion (especially at the head).
- Efficient memory utilization (no wasted space as with arrays).

---

## Disadvantages

- No random access (must traverse from head to access an element).
- Extra memory for pointers.
- More complex to implement than arrays.

---

## Common Interview Questions

1. Reverse a linked list.
2. Detect a cycle in a linked list (Floyd’s algorithm).
3. Find the middle of a linked list.
4. Merge two sorted linked lists.
5. Remove nth node from the end.
6. Check if the linked list is a palindrome.

---

## Sample: Reverse a Linked List (Python)

```python
def reverse_linked_list(head):
    prev = None
    curr = head
    while curr:
        next_node = curr.next
        curr.next = prev
        prev = curr
        curr = next_node
    return prev
```

---

## Applications

- Implementation of stacks and queues.
- Undo/redo functionality in applications.
- Dynamic memory management (free lists).
- Hash table chaining.

---

## Quick Revision Table

| Type             | Next Pointer | Prev Pointer | Circular? | Use Cases                   |
|------------------|--------------|--------------|-----------|-----------------------------|
| Singly Linked    | Yes          | No           | No        | Basic list, stack, queue    |
| Doubly Linked    | Yes          | Yes          | No        | Browser history, undo/redo  |
| Circular (any)   | Yes          | Optional     | Yes       | Round-robin scheduling      |

---

## References

- [GeeksforGeeks: Linked List](https://www.geeksforgeeks.org/data-structures/linked-list/)
- [Wikipedia: Linked List](https://en.wikipedia.org/wiki/Linked_list)

---

Happy Coding! 🚀
