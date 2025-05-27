# 05. Stacks

---

## What is a Stack?

A **stack** is a linear data structure that follows the Last-In-First-Out (LIFO) principle. The last element added is the first one to be removed.

---

## Stack Operations

| Operation | Description                | Time Complexity |
|-----------|----------------------------|-----------------|
| push(x)   | Insert element x on top    | O(1)            |
| pop()     | Remove and return top      | O(1)            |
| top()/peek() | Return top without removing | O(1)         |
| isEmpty() | Check if stack is empty    | O(1)            |

---

## Stack Implementation

### Using Array/List (Python)

```python
stack = []
stack.append(1)  # push
stack.append(2)
top = stack[-1]  # peek
elem = stack.pop()  # pop
```

### Using Linked List

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class Stack:
    def __init__(self):
        self.head = None

    def push(self, data):
        node = Node(data)
        node.next = self.head
        self.head = node

    def pop(self):
        if self.head is None:
            raise Exception("Stack is empty")
        data = self.head.data
        self.head = self.head.next
        return data

    def is_empty(self):
        return self.head is None
```

---

## Applications of Stack

- Function call stack (recursion)
- Expression evaluation (postfix, prefix)
- Undo/redo operations
- Syntax parsing
- Backtracking algorithms

---

## Common Algorithms

### 1. Valid Parentheses

```python
def is_valid(s):
    stack = []
    mapping = {")": "(", "}": "{", "]": "["}
    for char in s:
        if char in mapping.values():
            stack.append(char)
        elif char in mapping:
            if not stack or stack.pop() != mapping[char]:
                return False
    return not stack
```

### 2. Reverse a Stack

```python
def reverse_stack(stack):
    if not stack:
        return
    temp = stack.pop()
    reverse_stack(stack)
    insert_at_bottom(stack, temp)

def insert_at_bottom(stack, item):
    if not stack:
        stack.append(item)
    else:
        temp = stack.pop()
        insert_at_bottom(stack, item)
        stack.append(temp)
```

### 3. Next Greater Element

```python
def next_greater(nums):
    res = [-1]*len(nums)
    stack = []
    for i in range(len(nums)):
        while stack and nums[stack[-1]] < nums[i]:
            res[stack.pop()] = nums[i]
        stack.append(i)
    return res
```

---

## Real-World Applications

- Browsers (back/forward navigation)
- Undo feature in editors
- Parsing expressions and syntax trees

---

## Interview Questions

1. Implement a stack using queues.
2. Evaluate a postfix expression.
3. Design a stack that supports getMin() in O(1).
4. Decode an encoded string (e.g., "3[a2[c]]" → "accaccacc").

---

## Best Practices

- Check for stack overflows (fixed size).
- Use dynamic stacks (linked list) for unbounded usage.
- Prefer built-in stack types for reliability.

---

## References

- [GeeksforGeeks: Stack](https://www.geeksforgeeks.org/stack-data-structure/)
- [Wikipedia: Stack (abstract data type)](https://en.wikipedia.org/wiki/Stack_(abstract_data_type))

---

## Exercises

1. Implement a stack using two queues.
2. Check if a given expression is balanced.
3. Sort a stack using recursion.

---

Stacks are everywhere in computing. Mastering them is essential for algorithmic success!
