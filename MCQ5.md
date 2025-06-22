# All The Best

---

## 🔥 **MCQ 1 – Linked List: Reverse Recursively**

```java
Node reverse(Node curr, Node prev) {
    if (curr == null) return prev;
    Node next = curr.next;
    curr.next = prev;
    return reverse(next, curr);
}
```

Initial list: `1 → 2 → 3 → 4 → null`

After `reverse(head, null)`, what’s the new head value?

🔸 Options:

A) 1

B) 2

C) 3

D) 4

---

## 🌳 **MCQ 2 – Tree Height Confusion**

```java
int fun(Node root) {
    if (root == null) return 0;
    return 1 + Math.max(fun(root.left), fun(root.right));
}
```

Tree:

```
      1
     /
    2
   /
  3
```

What will `fun(root)` return?

🔸 Options:

A) 2

B) 3

C) 1

D) 0

---

## 🧩 **MCQ 3 – Recursive Insertion in BST**

```java
Node insert(Node root, int val) {
    if (root == null) return new Node(val);
    if (val < root.data)
        root.left = insert(root.left, val);
    else
        root.right = insert(root.right, val);
    return root;
}
```

Insert values in this order: `10, 5, 15, 12`

What is `root.right.left.data`?

🔸 Options:

A) null

B) 12

C) 15

D) 10

---

## 🔄 **MCQ 4 – Count Leaf Nodes Recursively**

```java
int countLeaves(Node root) {
    if (root == null) return 0;
    if (root.left == null && root.right == null) return 1;
    return countLeaves(root.left) + countLeaves(root.right);
}
```

Given tree:

```
      5
     / \
    3   8
   /   / \
  1   6   9
```

What is returned?

🔸 Options:

A) 2

B) 3

C) 4

D) 5

---

## 🧭 **MCQ 5 – Recursive DFS Visit Count**

```java
int dfs(int u, boolean[] vis, List<List<Integer>> adj) {
    vis[u] = true;
    int count = 1;
    for (int v : adj.get(u)) {
        if (!vis[v])
            count += dfs(v, vis, adj);
    }
    return count;
}
```

Graph: `0—1—2`, `adj = [[1],[0,2],[1]]`

Call: `dfs(0, vis, adj)`

What is returned?

🔸 Options:

A) 1

B) 2

C) 3

D) Infinite loop

---
