# 04. Linked Lists

---

## What is a Linked List?

A **linked list** is a linear data structure where each element (node) contains data and a reference (pointer) to the next node in the sequence.

---

## Types of Linked Lists

- **Singly Linked List:** Each node points to the next node.
- **Doubly Linked List:** Each node points to both the next and previous node.
- **Circular Linked List:** Last node points back to the head.

---

## Linked List Structure

### Node Class (Python Example)

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
```

### Linked List Class (Partial)

```python
class LinkedList:
    def __init__(self):
        self.head = None

    def append(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
            return
        last = self.head
        while last.next:
            last = last.next
        last.next = new_node
```

---

## Operations and Complexity

| Operation     | Singly | Doubly |
|---------------|--------|--------|
| Insert Front  | O(1)   | O(1)   |
| Insert End    | O(n)   | O(n)   |
| Delete Front  | O(1)   | O(1)   |
| Delete End    | O(n)   | O(n)   |
| Search        | O(n)   | O(n)   |
| Reverse       | O(n)   | O(n)   |

---

## Advantages

- Dynamic size, easy to grow/shrink.
- Efficient insert/delete at the beginning or middle.
- No memory waste due to fixed size.

## Limitations

- No random access (must traverse nodes).
- Extra memory for pointers.
- Cache locality poorer than arrays.

---

## Common Algorithms

### 1. Reverse a Linked List

```python
def reverse_list(head):
    prev = None
    curr = head
    while curr:
        next = curr.next
        curr.next = prev
        prev = curr
        curr = next
    return prev
```

### 2. Detect Cycle (Floyd's Tortoise and Hare)

```python
def has_cycle(head):
    slow = fast = head
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
        if slow == fast:
            return True
    return False
```

### 3. Merge Two Sorted Linked Lists

```python
def merge_lists(l1, l2):
    dummy = Node(0)
    tail = dummy
    while l1 and l2:
        if l1.data < l2.data:
            tail.next, l1 = l1, l1.next
        else:
            tail.next, l2 = l2, l2.next
        tail = tail.next
    tail.next = l1 or l2
    return dummy.next
```

---

## Use Cases

- Implementing stacks, queues
- Undo functionality in editors
- Adjacency lists in graphs
- Memory management

---

## Doubly Linked Lists

- Each node has `next` and `prev` pointers.
- Enables reverse traversal.
- Used in LRU cache, browser history, etc.

---

## Circular Linked List

- Last node points back to the head.
- Useful for round-robin scheduling, buffering.

---

## Real-World Applications

- Music/playlist navigation
- Task scheduling (round robin)
- Undo/redo stacks in software

---

## Common Interview Questions

1. Reverse a linked list (iterative/recursive)
2. Detect a cycle in a linked list
3. Merge two sorted lists
4. Find the middle of the linked list
5. Remove the nth node from end
6. Partition list around a value

---

## Best Practices

- Use dummy nodes to simplify edge cases.
- Always check for null pointers.
- For large data, consider memory overhead.

---

## References

- [GeeksforGeeks: Linked List](https://www.geeksforgeeks.org/data-structures/linked-list/)
- [Wikipedia: Linked List](https://en.wikipedia.org/wiki/Linked_list)

---

## Exercises

1. Implement a singly and doubly linked list.
2. Write a function to find and remove duplicates from a linked list.
3. Implement a function to find the intersection of two linked lists.

---

Linked lists are versatile building blocks. Practice traversing, inserting, deleting, and manipulating them!
