# 5. Stacks

---

## What is a Stack?

A **stack** is a linear data structure that follows the Last-In-First-Out (LIFO) principle. The last element added (pushed) to the stack is the first one to be removed (popped).

---

## Key Properties

- **LIFO Order:** Last element in, first out.
- **Operations at One End:** Both insertion and deletion are performed at the "top" of the stack.
- **Abstract Data Type (ADT):** Stack is defined by how it behaves, not how it is implemented.

---

## Basic Operations

| Operation | Description                   | Time Complexity |
|-----------|-------------------------------|-----------------|
| push      | Add element to the top        | O(1)            |
| pop       | Remove and return top element | O(1)            |
| peek/top  | Return top element (no remove)| O(1)            |
| isEmpty   | Check if stack is empty       | O(1)            |
| size      | Number of elements            | O(1)            |

---

## Implementations

- **Array-Based:** Fixed size, simple, but may waste space if not full.
- **Linked List-Based:** Dynamic size, no wasted space.

### Example: Stack using Python List

```python
stack = []
stack.append(10)    # push
top = stack[-1]     # peek
stack.pop()         # pop
```

### Example: Stack using Linked List (Python)

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class Stack:
    def __init__(self):
        self.top = None
    def push(self, data):
        node = Node(data)
        node.next = self.top
        self.top = node
    def pop(self):
        if self.top is None:
            return None
        data = self.top.data
        self.top = self.top.next
        return data
```

---

## Applications

- Function call stack (recursion)
- Expression evaluation (postfix/prefix)
- Undo/Redo operations
- Parenthesis matching
- Backtracking algorithms

---

## Common Interview Questions

1. Implement a stack using arrays/linked lists.
2. Implement two stacks in one array.
3. Check for balanced parentheses in an expression.
4. Evaluate postfix (Reverse Polish) expression.
5. Design a stack that returns the minimum element in O(1) time.

---

## Sample: Balanced Parentheses (Python)

```python
def is_balanced(expr):
    stack = []
    for char in expr:
        if char in "([{":
            stack.append(char)
        elif char in ")]}":
            if not stack:
                return False
            if "([{".index(stack.pop()) != ")]}".index(char):
                return False
    return not stack
```

---

## Quick Revision Table

| Property       | Array Stack  | Linked List Stack |
|----------------|--------------|------------------|
| Size           | Fixed        | Dynamic          |
| Overflow      | Possible     | No (till memory) |
| Underflow     | Yes          | Yes              |
| Memory Use    | May waste    | Efficient        |

---

## References

- [GeeksforGeeks: Stack Data Structure](https://www.geeksforgeeks.org/stack-data-structure/)
- [Wikipedia: Stack](https://en.wikipedia.org/wiki/Stack_(abstract_data_type))

---

Happy Coding! 🚀
