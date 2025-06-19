
---

### ⚡ **Q1. Self-modifying recursion — what is the output?**

```java
public class RecTest {
    static int hard(int n, int depth) {
        if (n <= 0) return depth;
        return hard(n - hard(n - 1, depth + 1), depth + 1);
    }

    public static void main(String[] args) {
        System.out.println(hard(5, 0));
    }
}
```

🔹 Options:

A) 3

B) 4

C) 5

D) 6


---

### ⚡ **Q2. Mutual recursion with shifting pattern**

```java
public class RecTest {
    static int f(int n);
    static int g(int n);

    static int f(int n) {
        if (n <= 0) return 0;
        return n - g(f(n - 1));
    }

    static int g(int n) {
        if (n <= 0) return 0;
        return n - f(g(n - 1));
    }

    public static void main(String[] args) {
        System.out.println(f(5));
    }
}
```

🔹 Options:

A) 3

B) 2

C) 1

D) 0


---

### ⚡ **Q3. Recursion with state accumulation**

```java
public class RecTest {
    static int hard(int n, int sum) {
        if (n <= 1) return sum;
        return hard(n - 1, sum + n) + hard(n - 2, sum + n);
    }

    public static void main(String[] args) {
        System.out.println(hard(4, 0));
    }
}
```

🔹 Options:

A) 14

B) 24

C) 18

D) 20


---

### ⚡ **Q4. Parameter evolves non-linearly**

```java
public class RecTest {
    static int evolve(int n) {
        if (n <= 0) return 0;
        return evolve(n / 3) + evolve(n / 2) + 1;
    }

    public static void main(String[] args) {
        System.out.println(evolve(10));
    }
}
```

🔹 Options:

A) 5

B) 6

C) 7

D) 8


---

### ⚡ **Q5. Recursion generates dynamic branching factor**

```java
public class RecTest {
    static int mystery(int n) {
        if (n <= 1) return 1;
        int total = 0;
        for (int i = 1; i < n; i++) {
            total += mystery(i) * mystery(n - i);
        }
        return total;
    }

    public static void main(String[] args) {
        System.out.println(mystery(4));
    }
}
```

🔹 Options:

A) 5

B) 6

C) 8

D) 9

---

# Intermediate Level......

### 🧠 **Q1. What is the output of the following recursive function?**

```java
public class RecTest {
    static int compute(int[] arr, int i) {
        if (i >= arr.length) return 0;
        return arr[i] + compute(arr, i + arr[i]);
    }

    public static void main(String[] args) {
        int[] arr = {2, 1, 3, 2, 1};
        System.out.println(compute(arr, 0));
    }
}
```

🔹 Options:

A) 6

B) 5

C) 7

D) 4


---

### 🧠 **Q2. What does this recursive function return?**

```java
public class RecTest {
    static boolean checkSorted(int[] arr, int i) {
        if (i == arr.length - 1) return true;
        if (arr[i] > arr[i + 1]) return false;
        return checkSorted(arr, i + 1);
    }

    public static void main(String[] args) {
        int[] arr = {1, 2, 4, 3, 5};
        System.out.println(checkSorted(arr, 0));
    }
}
```

🔹 Options:

A) true

B) false

C) Compile error

D) Index out of bounds


---

### 🧠 **Q3. Recursively find sum of only even-indexed elements**

```java
public class RecTest {
    static int sumEvenIdx(int[] arr, int i) {
        if (i >= arr.length) return 0;
        return arr[i] + sumEvenIdx(arr, i + 2);
    }

    public static void main(String[] args) {
        int[] arr = {5, 1, 3, 2, 7};
        System.out.println(sumEvenIdx(arr, 0));
    }
}
```

🔹 Options:

A) 13

B) 15

C) 11

D) 10


---

### 🧠 **Q4. Deep recursion with array mutation**

```java
public class RecTest {
    static void mutate(int[] arr, int i) {
        if (i >= arr.length) return;
        arr[i] += i;
        mutate(arr, i + 1);
        arr[i] *= 2;
    }

    public static void main(String[] args) {
        int[] arr = {1, 1, 1};
        mutate(arr, 0);
        System.out.println(Arrays.toString(arr));
    }
}
```

🔹 Options:

A) [2, 4, 6]

B) [4, 4, 4]

C) [4, 4, 2]

D) [4, 2, 2]


---

### 🧠 **Q5. Recursively reverse an array in-place**

```java
public class RecTest {
    static void reverse(int[] arr, int l, int r) {
        if (l >= r) return;
        int temp = arr[l];
        arr[l] = arr[r];
        arr[r] = temp;
        reverse(arr, l + 1, r - 1);
    }

    public static void main(String[] args) {
        int[] arr = {1, 2, 3, 4, 5};
        reverse(arr, 0, arr.length - 1);
        System.out.println(Arrays.toString(arr));
    }
}
```

🔹 Options:

A) [5, 4, 3, 2, 1]

B) [1, 2, 3, 4, 5]

C) [3, 2, 1, 4, 5]

D) [5, 2, 3, 4, 1]
