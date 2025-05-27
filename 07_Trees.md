# 07. Trees (Binary, BST, AVL, etc.)

---

## What is a Tree?

A **tree** is a non-linear hierarchical data structure consisting of nodes with parent-child relationships.

---

## Basic Terminology

- **Root:** Top node (no parent).
- **Leaf:** Node with no children.
- **Height:** Longest path from root to a leaf.
- **Depth:** Number of edges from root to node.
- **Subtree:** Any node and its descendants.

---

## Types of Trees

### 1. Binary Tree

- Each node has at most two children (left, right).

### 2. Binary Search Tree (BST)

- Left child < parent < right child.
- Enables fast search, insert, delete (O(log n) average).

### 3. Balanced Trees

- **AVL Tree:** Height-balanced via rotations.
- **Red-Black Tree:** Balanced via color properties.

### 4. Heap

- Complete binary tree with max/min at the root.

### 5. Trie

- Prefix tree for strings.

---

## Tree Node (Python)

```python
class TreeNode:
    def __init__(self, val):
        self.val = val
        self.left = None
        self.right = None
```

---

## Traversal Techniques

- **Preorder:** Root, Left, Right
- **Inorder:** Left, Root, Right (sorted for BST)
- **Postorder:** Left, Right, Root
- **Level Order:** Level by level (BFS)

### Example: Inorder Traversal

```python
def inorder(root):
    if root:
        inorder(root.left)
        print(root.val)
        inorder(root.right)
```

---

## BST Operations

- **Insert:** Recursively insert at correct position.
- **Delete:** Three cases (leaf, one child, two children).
- **Search:** Traverse left/right based on value.

---

## AVL Trees

- Maintains balance after insert/delete using rotations.
- Balance factor: height(left) - height(right) ∈ {-1,0,1}

---

## Applications of Trees

- Hierarchical data (file systems, org charts)
- Expression parsing/evaluation
- Databases (B-trees for indexing)
- Network routing (trie)

---

## Heaps

- **Min Heap:** Parent <= children (priority queue)
- **Max Heap:** Parent >= children

### Example: Heapify in Python

```python
import heapq
arr = [3,1,4,1,5]
heapq.heapify(arr)  # Min heap
```

---

## Interview Patterns

- Depth-first and breadth-first traversal
- Lowest Common Ancestor
- Serialize/deserialize binary tree

---

## Real-World Applications

- Auto-complete (trie)
- Memory management (heap)
- Expression evaluators (parse tree)

---

## Common Interview Questions

1. Validate if a tree is a BST.
2. Find the height or depth of a tree.
3. Print level order traversal.
4. Convert sorted array to BST.
5. Find kth smallest/largest in BST.

---

## Best Practices

- Use recursion for natural tree problems.
- Watch for stack overflow in deep trees.
- Use iterative or queue-based traversals for large trees.

---

## References

- [GeeksforGeeks: Tree Data Structure](https://www.geeksforgeeks.org/binary-tree-data-structure/)
- [Wikipedia: Tree (data structure)](https://en.wikipedia.org/wiki/Tree_(data_structure))

---

## Exercises

1. Implement preorder, inorder, and postorder traversal.
2. Write a function to check if a tree is balanced.
3. Serialize and deserialize a binary tree.

---

Trees are essential for hierarchical and sorted data—master their traversals and manipulations!
