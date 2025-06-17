
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
