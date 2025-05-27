# 10. Graphs

---

## What is a Graph?

A **graph** is a non-linear data structure consisting of a set of nodes (vertices) and a set of edges connecting pairs of nodes. Graphs are used to model relationships and connections in various domains.

---

## Types of Graphs

- **Directed vs. Undirected:**  
  - Directed: Edges have direction (A → B).
  - Undirected: Edges have no direction (A — B).
- **Weighted vs. Unweighted:**  
  - Weighted: Edges have associated weights/costs.
  - Unweighted: All edges are equal.
- **Cyclic vs. Acyclic:**  
  - Cyclic: Contains cycles (paths that start and end at the same node).
  - Acyclic: No cycles (e.g., DAG: Directed Acyclic Graph).
- **Connected vs. Disconnected:**  
  - Connected: There is a path between every pair of vertices (for undirected graphs).
  - Disconnected: At least one pair of vertices has no connecting path.

---

## Graph Representations

| Representation    | Description                                             | Space Complexity |
|-------------------|--------------------------------------------------------|------------------|
| Adjacency Matrix  | 2D array, cell[i][j] = 1 if edge from i to j exists    | O(V^2)           |
| Adjacency List    | Array of lists, list for each vertex of neighbors      | O(V + E)         |
| Edge List         | List of (from, to, weight) triples                     | O(E)             |

---

## Basic Operations and Complexity

| Operation             | Adjacency Matrix | Adjacency List |
|-----------------------|------------------|----------------|
| Add edge              | O(1)             | O(1)           |
| Remove edge           | O(1)             | O(E/V)         |
| Check edge existence  | O(1)             | O(E/V)         |
| Enumerate neighbors   | O(V)             | O(degree)      |

---

## Graph Traversal Algorithms

### 1. Breadth-First Search (BFS)
- Explores neighbors level by level.
- Uses a queue.
- O(V + E) time.

### 2. Depth-First Search (DFS)
- Explores as far as possible along each branch before backtracking.
- Uses a stack (often implemented recursively).
- O(V + E) time.

#### Example: BFS (Python)

```python
from collections import deque
def bfs(graph, start):
    visited = set()
    queue = deque([start])
    while queue:
        node = queue.popleft()
        if node not in visited:
            visited.add(node)
            for neighbor in graph[node]:
                queue.append(neighbor)
```

---

## Common Graph Algorithms

- **Shortest Path:** Dijkstra, Bellman-Ford
- **Minimum Spanning Tree:** Prim's, Kruskal's
- **Cycle Detection:** DFS/BFS, Union Find
- **Topological Sort:** For DAGs
- **Connected Components:** DFS/BFS
- **Network Flow:** Ford-Fulkerson

---

## Applications

- Social networks (users and friendships)
- Maps and navigation (cities and roads)
- Scheduling (dependencies as DAGs)
- Web crawling (pages and links)
- Network routing (routers and connections)

---

## Common Interview Questions

1. Implement BFS/DFS.
2. Detect a cycle in a graph.
3. Find shortest path between nodes.
4. Count connected components.
5. Topological sort of a DAG.
6. Clone a graph.

---

## Quick Revision Table

| Algorithm      | Best For           | Time Complexity |
|----------------|--------------------|-----------------|
| BFS            | Shortest path (unweighted), connected components | O(V+E) |
| DFS            | Cycle detection, path finding, connected components | O(V+E) |
| Dijkstra       | Shortest path (weighted, no negative weights) | O((V+E) log V) with heap |
| Kruskal/Prim   | Minimum spanning tree | O(E log V) |
| Topological Sort| Ordering DAG nodes | O(V+E) |

---

## References

- [GeeksforGeeks: Graph Data Structure](https://www.geeksforgeeks.org/graph-data-structure-and-algorithms/)
- [Wikipedia: Graph (abstract data type)](https://en.wikipedia.org/wiki/Graph_(abstract_data_type))

---

Happy Coding! 🌐
