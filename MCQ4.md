
### 🧠 **Q1. “MIRROR THE BUNKER” — Reverse an Array Without Using Another**

The security system stores secret codes in an array and flips them in-place before validating. Here's the logic:

```java
int[] arr = {4, 9, 1, 7, 2};
int i = 0, j = arr.length - 1;

while (i < j) {
    arr[i] = arr[i] + arr[j];
    arr[j] = arr[i] - arr[j];
    arr[i] = arr[i] - arr[j];
    i++;
    j--;
}

System.out.print(arr[2]);
```

What will be the output?

**A.** 9

**B.** 1

**C.** 4

**D.** 7

---

### ⚙️ **Q2. “THE INTERLEAVED PUZZLE” — Shuffle Without Collections**

A magician shuffles an array by placing even-indexed elements at front and odd-indexed ones at back of a new array — all  **manually without helper classes** .

```java
int[] a = {5, 6, 7, 8, 9, 10};
int[] temp = new int[6];
int k = 0;

for (int i = 0; i < a.length; i += 2) {
    temp[k++] = a[i];
}
for (int i = 1; i < a.length; i += 2) {
    temp[k++] = a[i];
}
System.out.print(temp[3]);
```

What gets printed?

**A.** 8

**B.** 9

**C.** 6

**D.** 7

### 🕸 **Q3. “THE LOOPED LADDER” — Jump with Custom Logic**

You’re climbing stairs where jump size is dynamically calculated:

```java
int[] steps = {2, 4, 6, 3, 1, 5, 0};
int i = 0, sum = 0;

while (i < steps.length) {
    sum += steps[i];
    i += steps[i];
}
System.out.print(sum);
```

What is the total sum?

**A.** 12

**B.** 6

**C.** 10

**D.** Infinite Loop

---

### 🧩 **Q4. “THE MANUAL BUBBLE TRAP” — Custom Bubble Sort + Early Exit Logic**

```java
int[] arr = {3, 1, 4, 2};
boolean swapped;

for (int i = 0; i < arr.length; i++) {
    swapped = false;
    for (int j = 0; j < arr.length - i - 1; j++) {
        if (arr[j] > arr[j + 1]) {
            int temp = arr[j];
            arr[j] = arr[j + 1];
            arr[j + 1] = temp;
            swapped = true;
        }
    }
    if (!swapped) break;
}
System.out.print(arr[2]);
```

What is the result?

**A.** 4

**B.** 3

**C.** 2

**D.** 1

### 🔐 **Q5. “MANUALLY CHECKING PALINDROME WITHOUT LIBRARY”**

A string is stored in a char array and is checked for palindrome manually:

```java
char[] word = {'r', 'a', 'c', 'e', 'c', 'a', 'r'};
boolean isPal = true;
int i = 0, j = word.length - 1;

while (i < j) {
    if (word[i] != word[j]) {
        isPal = false;
        break;
    }
    i++;
    j--;
}
System.out.print(isPal ? "YES" : "NO");
```

**A.** YES

**B.** NO

**C.** Runtime Error

**D.** Compilation Error


---

### 🌳 **Q6. “THE GHOST NODE” — Binary Tree Left/Right Confusion**

A binary tree is manually built:

```java
class Node {
    int val;
    Node left, right;
    Node(int v) { val = v; }
}

Node root = new Node(1);
root.left = new Node(2);
root.right = new Node(3);
root.left.left = new Node(4);
root.left.right = new Node(5);
root.right.left = new Node(6);
root.left = root.left.right;
```

What is the result of this traversal?

```java
System.out.print(root.left.val);
```

**A.** 2

**B.** 5

**C.** 4

**D.** NullPointerException

---

### 🌐 **Q7. “THE ISOLATED CITY” — Adjacency Matrix Logic**

You are given the following matrix representing 5 cities (0 to 4). An entry of 1 means a direct road.

```java
int[][] graph = {
    {0, 1, 0, 0, 0},
    {1, 0, 1, 0, 0},
    {0, 1, 0, 0, 0},
    {0, 0, 0, 0, 0},
    {0, 0, 0, 0, 0}
};
```

How many **completely isolated cities** are there?

**A.** 0

**B.** 1

**C.** 2

**D.** 3

---

### 🔁 **Q8. “THE SPIRAL TREE” — Custom Tree Traversal**

A tree is built like this:

```java
//            1
//          /   \
//         2     3
//        / \     \
//       4   5     6

class Node {
    int val;
    Node left, right;
    Node(int v) { val = v; }
}
```

You're asked to manually print  **only alternate level nodes** , starting from root:

```java
void spiral(Node root, int level) {
    if (root == null) return;
    if (level % 2 == 0) System.out.print(root.val + " ");
    spiral(root.left, level + 1);
    spiral(root.right, level + 1);
}
```

If `spiral(root, 0)` is called, what will be printed?

**A.** 1 4 5 6

**B.** 1 2 3

**C.** 1

**D.** 1 4 6


---

### 🔄 **Q9. “THE CYCLIC CONFUSION” — Undirected Graph Cycle Trap**

Given the following connections in an undirected graph:

```
0—1
| |
2—3
```

Manually represent as adjacency matrix and count how many **edges** it has.

```java
int[][] adj = new int[4][4];
adj[0][1] = adj[1][0] = 1;
adj[0][2] = adj[2][0] = 1;
adj[1][3] = adj[3][1] = 1;
adj[2][3] = adj[3][2] = 1;

int edges = 0;
for (int i = 0; i < 4; i++) {
    for (int j = 0; j < 4; j++) {
        if (adj[i][j] == 1) edges++;
    }
}
System.out.print(edges / 2);
```

**A.** 2

**B.** 3

**C.** 4

**D.** 6

---

### 🔍 **Q10. “THE DFS TRICK” — Manual Recursive Graph Traversal**

You’re manually visiting all nodes using DFS:

```java
boolean[] visited = new boolean[5];
int[][] graph = {
    {0,1,1,0,0},
    {1,0,0,1,0},
    {1,0,0,1,0},
    {0,1,1,0,1},
    {0,0,0,1,0}
};

void dfs(int v) {
    visited[v] = true;
    for (int i = 0; i < 5; i++) {
        if (graph[v][i] == 1 && !visited[i]) {
            dfs(i);
        }
    }
}
```

If `dfs(0)` is called, how many nodes will be visited?

**A.** 3

**B.** 4

**C.** 5

**D.** Infinite Recursion

---
