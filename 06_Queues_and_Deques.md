# 6. Queues and Deques

---

## What is a Queue?

A **queue** is a linear data structure that follows the First-In-First-Out (FIFO) principle.  
The first element added to the queue will be the first one to be removed.

---

## Key Properties

- **FIFO Order:** First element in, first element out.
- **Operations at Both Ends:** In a basic queue, insertion (enqueue) is at the rear, and deletion (dequeue) is at the front.

---

## Basic Queue Operations

| Operation   | Description                     | Time Complexity |
|-------------|---------------------------------|-----------------|
| enqueue     | Add element to rear             | O(1)            |
| dequeue     | Remove and return front element | O(1)            |
| front/peek  | Return front element            | O(1)            |
| isEmpty     | Check if queue is empty         | O(1)            |
| size        | Number of elements              | O(1)            |

---

## Implementations

- **Array-Based:** Simple but can waste space if not circular.
- **Circular Queue:** Uses array in a circular manner to efficiently utilize space.
- **Linked List-Based:** Dynamic size, easy to expand.

### Example: Queue using Python List

```python
from collections import deque
q = deque()
q.append(10)    # enqueue
front = q[0]    # peek/front
q.popleft()     # dequeue
```

### Example: Queue using Linked List (Python)

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class Queue:
    def __init__(self):
        self.front = self.rear = None
    def enqueue(self, data):
        node = Node(data)
        if self.rear is None:
            self.front = self.rear = node
        else:
            self.rear.next = node
            self.rear = node
    def dequeue(self):
        if self.front is None:
            return None
        data = self.front.data
        self.front = self.front.next
        if self.front is None:
            self.rear = None
        return data
```

---

## Applications

- Scheduling (CPU, printers)
- BFS (Breadth-First Search) in graphs/trees
- Handling requests in web servers
- Buffering (IO buffers)

---

## What is a Deque?

A **deque** (double-ended queue) is a generalized version of a queue that allows insertion and deletion at both ends.

---

## Basic Deque Operations

| Operation    | Description                        | Time Complexity |
|--------------|------------------------------------|-----------------|
| addFront     | Insert at front                    | O(1)            |
| addRear      | Insert at rear                     | O(1)            |
| removeFront  | Remove from front                  | O(1)            |
| removeRear   | Remove from rear                   | O(1)            |
| peekFront    | Get front element                  | O(1)            |
| peekRear     | Get rear element                   | O(1)            |

### Example: Deque in Python

```python
from collections import deque
d = deque()
d.append(1)       # add to rear
d.appendleft(2)   # add to front
d.pop()           # remove from rear
d.popleft()       # remove from front
```

---

## Applications of Deques

- Implementing both stacks and queues
- Sliding window problems
- Palindrome checking
- Undo/redo functionality in software

---

## Common Interview Questions

1. Implement a queue using two stacks.
2. Implement a stack using two queues.
3. Design a circular queue.
4. Sliding window maximum/minimum using deque.
5. Check if a sequence is a palindrome using deque.

---

## Quick Revision Table

| Structure | Insert Front | Insert Rear | Delete Front | Delete Rear | Use Cases               |
|-----------|--------------|-------------|--------------|-------------|-------------------------|
| Queue     | No           | Yes         | Yes          | No          | BFS, scheduling         |
| Deque     | Yes          | Yes         | Yes          | Yes         | Sliding window, undo    |

---

## References

- [GeeksforGeeks: Queue Data Structure](https://www.geeksforgeeks.org/queue-data-structure/)
- [GeeksforGeeks: Deque Data Structure](https://www.geeksforgeeks.org/deque-set-1-introduction-applications/)
- [Wikipedia: Queue](https://en.wikipedia.org/wiki/Queue_(abstract_data_type))
- [Wikipedia: Deque](https://en.wikipedia.org/wiki/Double-ended_queue)

---

Happy Coding! 🚀
