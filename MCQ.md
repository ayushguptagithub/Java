
### 🧠 **Recursion Output-Based MCQ Test**

---

**Q1. What is the output of the following code?**

```java
static int f(int n) {
    if (n == 0) return 2;
    return f(n - 1) * 2;
}
public static void main(String[] args) {
    System.out.println(f(4));
}
```

a. 16

b. 32

c. 8

d. 2

---

**Q2. What will be printed?**

```java
static int f(int n) {
    if (n == 0) return 1;
    return f(n - 1) + n;
}
public static void main(String[] args) {
    System.out.println(f(5));
}
```

a. 15

b. 10

c. 6

d. 21

---

**Q3. What is the output of this code?**

```java
static int fun(int n) {
    if (n <= 1) return 1;
    return fun(n - 1) + fun(n - 2);
}
public static void main(String[] args) {
    System.out.println(fun(6));
}
```

a. 13

b. 8

c. 21

d. 5

---

**Q4. What does this function print?**

```java
static void print(int n) {
    if (n == 0) return;
    System.out.print(n + " ");
    print(n - 1);
    System.out.print(n + " ");
}
public static void main(String[] args) {
    print(3);
}
```

a. 3 2 1 1 2 3

b. 1 2 3 3 2 1

c. 3 2 1 2 3

d. 3 1 2 3

---

**Q5. What is the result of this function?**

```java
static int sumAlt(int n) {
    if (n == 0) return 0;
    return n - sumAlt(n - 1);
}
public static void main(String[] args) {
    System.out.println(sumAlt(4));
}
```

a. 0

b. 2

c. 1

d. 4

---

**Q6. What is the output for n = 3?**

```java
static int strange(int n) {
    if (n == 0) return 1;
    return strange(n - 1) * n + 1;
}
```

a. 7

b. 10

c. 13

d. 15

---

**Q7. What does this recursive function return?**

```java
static int calc(int n) {
    if (n == 1) return 1;
    return calc(n - 1) + n * n;
}
public static void main(String[] args) {
    System.out.println(calc(3));
}
```

a. 9

b. 14

c. 13

d. 12

---

**Q8. What is printed?**

```java
static void printDown(int n) {
    if (n == 0) return;
    System.out.print(n + " ");
    printDown(n - 2);
}
public static void main(String[] args) {
    printDown(5);
}
```

a. 5 3 1

b. 5 4 3 2 1

c. 1 3 5

d. 5 2

---

**Q9. What value is returned by the function?**

```java
static int fun(int n) {
    if (n == 1) return 1;
    return fun(n / 2) + 1;
}
public static void main(String[] args) {
    System.out.println(fun(8));
}
```

a. 4

b. 3

c. 5

d. 2

---

**Q10. What will this function output?**

```java
static int weird(int n) {
    if (n <= 1) return n;
    return weird(n - 1) * weird(n - 2) + 1;
}
public static void main(String[] args) {
    System.out.println(weird(4));
}
```

a. 5

b. 7

c. 9

d. 10

---
