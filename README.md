## Project Description: Graph Traversal and Topological Sort Implementation

This lab project, conducted by Group 17, focuses on the implementation and comparison of two fundamental graph traversal algorithms: Breadth-First Search (BFS) and Topological Sort. The primary objective is to gain a practical understanding of these algorithms and analyze the trade-offs associated with different graph representations, specifically adjacency matrices and adjacency lists.

The project involves the following key aspects:

* **Graph Representation:** Implementing graphs using two common data structures:
    * **Adjacency Matrix:** A 2D array where the entry at row `i` and column `j` indicates the presence (or weight) of an edge between vertex `i` and vertex `j`. This representation is straightforward for checking the existence of an edge but can be space-inefficient for sparse graphs.
    * **Adjacency List:** An array of lists, where each list `i` stores the neighbors of vertex `i`. This representation is more space-efficient for sparse graphs as it only stores the existing edges.

* **Breadth-First Search (BFS):** Implementing the BFS algorithm using the adjacency matrix representation. BFS is a graph traversal algorithm that explores all the neighbor nodes at the present depth prior to moving on to the nodes at the next depth level. It is commonly used for finding the shortest path in an unweighted graph.

* **Topological Sort:** Implementing the Topological Sort algorithm using the adjacency list representation. Topological sort is a linear ordering of vertices such that for every directed edge from vertex `u` to vertex `v`, vertex `u` comes before vertex `v` in the ordering. This algorithm is applicable to Directed Acyclic Graphs (DAGs) and is used in scheduling, dependency resolution, and task ordering.

* **Comparison of Graph Representations:** Analyzing the space complexity and performance implications of using adjacency matrices versus adjacency lists for graph representation in the context of BFS and Topological Sort.

* **Practical Application:** Understanding the significance of BFS and Topological Sort in addressing real-world problems related to graph theory.

## Algorithms Used:

### 1. Breadth-First Search (BFS)

**Data Structure:** Adjacency Matrix

**Algorithm:**

1.  Initialize a boolean array `visited` of size equal to the number of vertices, marking all vertices as not visited.
2.  Create a queue and enqueue the starting vertex.
3.  Mark the starting vertex as visited.
4.  While the queue is not empty:
    a.  Dequeue a vertex `u`.
    b.  For each neighbor `v` of `u` (determined by checking the adjacency matrix):
        i.  If `v` has not been visited:
            * Mark `v` as visited.
            * Enqueue `v`.
            * Record the path or distance if required.

**Implementation Details (Based on Snippets):**

The provided code snippet demonstrates the creation of an adjacency matrix (`AdjMatrix M`) and the addition of edges. The `M.BFS(0)` call indicates the execution of the BFS algorithm starting from vertex 0 (labeled as "PIEAS"). The output section suggests that the BFS traversal calculates and prints the path from the source node (0) to every other reachable node.

### 2. Topological Sort

**Data Structure:** Adjacency List

**Algorithm:**

1.  Calculate the in-degree of each vertex (the number of incoming edges).
2.  Create a queue and enqueue all vertices with an in-degree of 0.
3.  Initialize an empty list to store the sorted elements.
4.  While the queue is not empty:
    a.  Dequeue a vertex `u`.
    b.  Add `u` to the sorted list.
    c.  For each neighbor `v` of `u` (in the adjacency list):
        i.  Decrement the in-degree of `v` by 1.
        ii. If the in-degree of `v` becomes 0, enqueue `v`.
5.  If the size of the sorted list is equal to the number of vertices, then the graph has a topological ordering. Otherwise, the graph contains a cycle and a topological sort is not possible.

**Implementation Details (Based on Snippets):**

The code snippet shows the creation of an adjacency list (`AdjList G`) and the addition of directed edges. The `G.TopologicalSort()` call executes the topological sort algorithm on the graph represented by the adjacency list. The output section is labeled "Path Found By Topological Sort," which likely displays the topologically sorted order of the vertices in the graph.

**Note:** The lab report mentions "BFS Traversing the graph for Node '0' (PIEAS) using BFS algorithm" twice, once after the adjacency matrix implementation and again before the topological sort. This might be a slight redundancy in the output description, as BFS is associated with the adjacency matrix implementation in the provided snippets, while Topological Sort is performed on the graph represented by the adjacency list.
