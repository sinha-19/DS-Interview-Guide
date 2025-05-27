# 7. Trees (Binary, BST, AVL, etc.)

---

## What is a Tree?

A **tree** is a non-linear hierarchical data structure consisting of nodes, with a single node as the root and zero or more child nodes. Each node (except the root) has exactly one parent.

---

## Basic Terminology

- **Node:** Fundamental unit containing data and links.
- **Root:** Topmost node.
- **Parent/Child:** Relationship between nodes.
- **Leaf:** Node with no children.
- **Height/Depth:** Height = longest path to a leaf, Depth = root to node path.
- **Subtree:** Tree formed by a node and its descendants.

---

## Types of Trees

### 1. Binary Tree
Each node has at most two children (left, right).

### 2. Binary Search Tree (BST)
A binary tree where:
- Left child < Parent < Right child (for all nodes)
- Enables fast search, insert, delete (O(log n) average, O(n) worst-case if unbalanced).

### 3. Balanced Binary Trees
- **AVL Tree:** Self-balancing BST. Heights of two subtrees of any node differ by at most one.
- **Red-Black Tree:** BST with additional color property to ensure balance.

### 4. Heap Tree
- **Min Heap:** Parent ≤ children (root is minimum).
- **Max Heap:** Parent ≥ children (root is maximum).

### 5. Other Trees
- **B-Tree, B+ Tree:** Used in databases, multi-way search.
- **Trie (Prefix Tree):** For efficient string search.

---

## Basic Operations and Complexity

| Operation   | Binary Tree | BST (Avg) | AVL/Red-Black (Balanced) |
|-------------|-------------|-----------|--------------------------|
| Search      | O(n)        | O(log n)  | O(log n)                 |
| Insert      | O(n)        | O(log n)  | O(log n)                 |
| Delete      | O(n)        | O(log n)  | O(log n)                 |
| Traversal   | O(n)        | O(n)      | O(n)                     |

---

## Tree Traversals

- **Inorder (LNR):** Left, Node, Right (BST: gives sorted order)
- **Preorder (NLR):** Node, Left, Right
- **Postorder (LRN):** Left, Right, Node
- **Level Order:** BFS using a queue

### Example: Inorder Traversal (Python)

```python
def inorder(root):
    if root:
        inorder(root.left)
        print(root.data)
        inorder(root.right)
```

---

## Common Interview Questions

1. Implement inorder, preorder, postorder traversals.
2. Check if a binary tree is balanced.
3. Find the height/depth of a tree.
4. Lowest Common Ancestor (LCA) of two nodes.
5. Convert binary tree to doubly linked list.
6. Validate if a tree is a BST.
7. Serialize and deserialize a binary tree.

---

## Applications

- Hierarchical data (file systems)
- Expression parsing and evaluation (syntax trees)
- Databases (B-trees, B+ trees)
- Priority queues (heaps)
- Routing algorithms (trie, search trees)

---

## Quick Revision Table

| Tree Type    | Ordering Property           | Balance?      | Use Case               |
|--------------|----------------------------|---------------|------------------------|
| Binary Tree  | No                         | No            | General hierarchy      |
| BST          | Left < Root < Right        | No            | Fast lookup            |
| AVL          | Yes (BST)                  | Strict        | Always balanced        |
| Red-Black    | Yes (BST)                  | Less strict   | Balanced, fast ops     |
| Heap         | Parent ≥/≤ Children        | Yes (heapify) | Priority queue, heap   |
| Trie         | n/a (prefix tree)          | n/a           | String search          |

---

## References

- [GeeksforGeeks: Tree Data Structure](https://www.geeksforgeeks.org/binary-tree-data-structure/)
- [Wikipedia: Tree (data structure)](https://en.wikipedia.org/wiki/Tree_(data_structure))

---

Happy Coding! 🌳
