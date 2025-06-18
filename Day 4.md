### ✅ Graph Code in Java Using Adjacency Matrix

```java
public class Graph {
    private int vertices;
    private int[][] adjMatrix;

    // Constructor
    public Graph(int v) {
        vertices = v;
        adjMatrix = new int[vertices][vertices];
    }

    // Add edge (Undirected)
    public void addEdge(int src, int dest) {
        adjMatrix[src][dest] = 1;
        adjMatrix[dest][src] = 1; // remove this line for directed graph
    }

    // Print the graph (Adjacency Matrix)
    public void printGraph() {
        System.out.println("Adjacency Matrix:");
        for (int i = 0; i < vertices; i++) {
            for (int j = 0; j < vertices; j++) {
                System.out.print(adjMatrix[i][j] + " ");
            }
            System.out.println();
        }
    }

    // Main method to test
    public static void main(String[] args) {
        Graph g = new Graph(5);

        g.addEdge(0, 1);
        g.addEdge(0, 4);
        g.addEdge(1, 2);
        g.addEdge(1, 3);
        g.addEdge(1, 4);
        g.addEdge(2, 3);
        g.addEdge(3, 4);

        g.printGraph();
    }
}
```

---

### 📘 Output:

```
Adjacency Matrix:
0 1 0 0 1
1 0 1 1 1
0 1 0 1 0
0 1 1 0 1
1 1 0 1 0
```

---

### ✅ Java Program: DFS & BFS for Weighted Graph (Adjacency Matrix)

```java
import java.util.*;

public class WeightedGraphTraversal {
    private int vertices;
    private int[][] adjMatrix;

    public WeightedGraphTraversal(int v) {
        vertices = v;
        adjMatrix = new int[v][v];
    }

    // Add edge (undirected with weight)
    public void addEdge(int src, int dest, int weight) {
        adjMatrix[src][dest] = weight;
        adjMatrix[dest][src] = weight; // Remove for directed graph
    }

    // DFS Traversal
    public void DFS(int start) {
        boolean[] visited = new boolean[vertices];
        System.out.print("DFS Traversal: ");
        dfsUtil(start, visited);
        System.out.println();
    }

    private void dfsUtil(int node, boolean[] visited) {
        visited[node] = true;
        System.out.print(node + " ");

        for (int i = 0; i < vertices; i++) {
            if (adjMatrix[node][i] != 0 && !visited[i]) {
                dfsUtil(i, visited);
            }
        }
    }

    // BFS Traversal
    public void BFS(int start) {
        boolean[] visited = new boolean[vertices];
        Queue<Integer> queue = new LinkedList<>();

        visited[start] = true;
        queue.add(start);

        System.out.print("BFS Traversal: ");
        while (!queue.isEmpty()) {
            int node = queue.poll();
            System.out.print(node + " ");

            for (int i = 0; i < vertices; i++) {
                if (adjMatrix[node][i] != 0 && !visited[i]) {
                    visited[i] = true;
                    queue.add(i);
                }
            }
        }
        System.out.println();
    }

    // Print the weighted matrix
    public void printMatrix() {
        System.out.println("Weighted Adjacency Matrix:");
        for (int i = 0; i < vertices; i++) {
            for (int j = 0; j < vertices; j++) {
                System.out.print(adjMatrix[i][j] + " ");
            }
            System.out.println();
        }
    }

    // Main method to test
    public static void main(String[] args) {
        WeightedGraphTraversal g = new WeightedGraphTraversal(5);

        g.addEdge(0, 1, 4);
        g.addEdge(0, 4, 2);
        g.addEdge(1, 2, 3);
        g.addEdge(1, 3, 5);
        g.addEdge(1, 4, 1);
        g.addEdge(2, 3, 7);
        g.addEdge(3, 4, 6);

        g.printMatrix();
        g.DFS(0);
        g.BFS(0);
    }
}
```

---

### 📘 Sample Output:

```
Weighted Adjacency Matrix:
0 4 0 0 2 
4 0 3 5 1 
0 3 0 7 0 
0 5 7 0 6 
2 1 0 6 0 

DFS Traversal: 0 1 2 3 4 
BFS Traversal: 0 1 4 2 3 
```

---
