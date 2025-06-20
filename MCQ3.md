## ⚔️ PART 1: **5 TOUGHEST RECURSION PROBLEMS**

(⚠️ No clue from the function name; logic is disguised)

---

### 🔸 **Q1. What does this return?**

```java
static int alpha(int x) {
    if (x < 2) return 1;
    return alpha(x - 1) + alpha(x - 3);
}

public static void main(String[] args) {
    System.out.println(alpha(6));
}
```

🔹 Options:

A) 7

B) 9

C) 11

D) 13

---

### 🔸 **Q2. What is the result printed?**

```java
static int beta(int x, int y) {
    if (x == 0 || y == 0) return 1;
    return beta(x - 1, y) + beta(x, y - 1);
}

public static void main(String[] args) {
    System.out.println(beta(2, 2));
}
```

🔹 Options:

A) 6

B) 5

C) 4

D) 3

---

### 🔸 **Q3. What's the final value printed?**

```java
static int gamma(int a, int b) {
    if (a <= 0 || b <= 0) return 0;
    return 1 + gamma(a - 2, b - 1);
}

public static void main(String[] args) {
    System.out.println(gamma(5, 4));
}
```

🔹 Options:

A) 2

B) 3

C) 4

D) 5

---

### 🔸 **Q4. What is printed?**

```java
static int delta(int[] a, int i) {
    if (i >= a.length) return 0;
    return a[i] + delta(a, i + a[i]);
}

public static void main(String[] args) {
    int[] a = {2, 1, 3, 2, 1};
    System.out.println(delta(a, 0));
}
```

🔹 Options:

A) 5

B) 6

C) 7

D) 8

---

### 🔸 **Q5. Output?**

```java
static void omega(int x) {
    if (x <= 0) return;
    omega(x / 2);
    System.out.print(x + " ");
}

public static void main(String[] args) {
    omega(20);
}
```

🔹 Options:

A) 1 2 5 10 20

B) 1 2 4 8 16

C) 1 2 3 4 5

D) 2 4 8 16 20

---

## 💡 PART 2: **5 TOUGHEST RANDOM JAVA MCQs**

---

### 🔸 **MCQ 1: Hidden Boxing Trap**

```java
Integer a = 127;
Integer b = 127;
System.out.println(a == b);
```

🔹 Options:

A) true

B) false

C) Compilation error

D) Runtime Exception

---

### 🔸 **MCQ 2: Static Block Surprise**

```java
class Test {
    static {
        System.out.println("Static block");
        System.exit(0);
    }
    public static void main(String[] args) {
        System.out.println("Main method");
    }
}
```

🔹 Options:

A) Static block

B) Main method

C) Both

D) Nothing

---

### 🔸 **MCQ 3: String Pool Confusion**

```java
String x = "hello";
String y = new String("hello");
System.out.println(x == y);
```

🔹 Options:

A) true

B) false

C) Compilation error

D) Depends on JVM

---

### 🔸 **MCQ 4: Over Loading**

```java


---

### 🔸 **Overloading with Type Promotion**

```java
public class OverloadSimple {

    void show(int a) {
        System.out.println("int");
    }

    void show(double a) {
        System.out.println("double");
    }

    public static void main(String[] args) {
        OverloadSimple obj = new OverloadSimple();
        obj.show(10.5f);
    }
}
```

---

### 🔹 Options:

A) int
B) double
C) float
D) Compile-time error
E) Ambiguous


---

### 🔸 **MCQ 5: Tricky Exception Handling**

```java
try {
    System.out.println(10 / 0);
} catch (ArithmeticException e) {
    System.out.println("A");
} finally {
    System.out.println("F");
}
```

🔹 Options:

A) A

B) A F

C) F

D) Runtime Exception

---
