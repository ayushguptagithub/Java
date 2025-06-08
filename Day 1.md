
---

# 🟡 Java – A Complete Note

## 📌 Introduction to Java

Java is a high-level, object-oriented, class-based programming language developed by **James Gosling** at **Sun Microsystems** in  **1995** . It is widely used for building platform-independent applications.

**Motto:** *Write Once, Run Anywhere (WORA)*

---

## ⚙️ Features of Java

1. **Simple** – Easy to learn, similar to C/C++ but with fewer complexities.
2. **Object-Oriented** – Everything in Java is an object.
3. **Platform Independent** – Java code runs on JVM, not on OS directly.
4. **Secure** – No explicit pointer; runs in sandbox environment.
5. **Robust** – Strong memory management and exception handling.
6. **Multithreaded** – Supports multiple threads for concurrent execution.
7. **Architecture Neutral** – Compiled code is executable on many platforms.
8. **High Performance** – Just-In-Time (JIT) compiler increases speed.
9. **Distributed** – Supports networking and RMI.
10. **Dynamic** – Can adapt to an evolving environment with dynamic classes.

---

## 📂 Java Editions

1. **Java SE** – Standard Edition (Desktop and server applications)
2. **Java EE / Jakarta EE** – Enterprise Edition (Web & Enterprise apps)
3. **Java ME** – Micro Edition (Mobile and embedded devices)
4. **JavaFX** – For building rich GUI apps

---

## 🔁 Java Program Lifecycle

```
Source Code (.java)
        ↓
Compilation → Bytecode (.class)
        ↓
JVM Execution (Java Virtual Machine)
```

---

## 💻 Sample Java Program

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

---

## 🧱 Core Concepts of Java

### 1. **Data Types**

* **Primitive:** int, float, double, char, boolean, byte, short, long
* **Non-primitive:** String, Arrays, Classes, Interfaces

### 2. **Control Statements**

* Conditional: `if`, `else`, `switch`
* Looping: `for`, `while`, `do-while`
* Jump: `break`, `continue`, `return`

### 3. **Object-Oriented Principles**

* **Class** – Blueprint of an object
* **Object** – Instance of a class
* **Encapsulation** – Binding data with code
* **Inheritance** – Reusing code from parent class
* **Polymorphism** – One task many forms (method overloading/overriding)
* **Abstraction** – Hiding internal details (abstract class/interface)

### 4. **Modifiers**

* Access: `public`, `private`, `protected`, `default`
* Non-access: `static`, `final`, `abstract`, `synchronized`

### 5. **Exception Handling**

```java
try {
   // risky code
} catch (Exception e) {
   // handle error
} finally {
   // always executed
}
```

---

## 📦 Java Packages

* Used to group related classes and interfaces
* Syntax: `package mypackage;`
* Built-in: `java.util`, `java.io`, `java.lang`, etc.

---

## 📚 Important Libraries & APIs

* `java.lang` – Core classes
* `java.util` – Collections, Date, etc.
* `java.io` – File handling
* `java.net` – Networking
* `javax.swing` – GUI components
* `java.sql` – Database connectivity (JDBC)

---

## 📊 Diagram: Java Execution Flow

```
┌────────────┐     ┌────────────┐     ┌───────────────┐
│ .java File │ --> │ javac.exe  │ --> │ .class (Byte) │
└────────────┘     └────────────┘     └───────────────┘
                                           │
                                           ↓
                                   ┌──────────────┐
                                   │ JVM (Runtime)│
                                   └──────────────┘
```

---

## 🔐 Java and Security

* Bytecode verification
* No pointers
* Security Manager & Class Loader

---

## 🌐 Java vs Other Languages

| Feature       | Java     | C++     | Python      |
| ------------- | -------- | ------- | ----------- |
| Memory Safety | High     | Low     | High        |
| Compilation   | Bytecode | Machine | Interpreted |
| OOP Support   | Strong   | Partial | Optional    |
| Speed         | Medium   | Fast    | Slower      |

---

## 🧠 Applications of Java

* Desktop Applications (Swing, JavaFX)
* Web Applications (Servlets, JSP)
* Enterprise Applications (Spring, Hibernate)
* Mobile Apps (Android using Java)
* Embedded Systems
* Game Development

---


# 🟡 Java Data Types – Notes with Code Examples

## 📌 What are Data Types?

In Java,  **data types specify the size and type of values that can be stored in a variable** . Java is a  **strongly typed language** , so every variable must be declared with a data type.

---

## 🔹 Types of Data Types in Java

```
                ┌─────────────┐
                │  Data Types │
                └─────┬───────┘
                      │
        ┌─────────────┴─────────────┐
        │                           │
  Primitive Types              Non-Primitive Types
        │                           │
┌───────┬───────┬───────┬──────┐    └───────> Arrays, String, Class, Interface
│ int   │ float │ char  │ etc. │
└───────┴───────┴───────┴──────┘
```

---

## 🔸 1. Primitive Data Types

Java has  **8 primitive data types** , divided as follows:

### 🔹 Integer Types

| Type  | Size    | Range             |
| ----- | ------- | ----------------- |
| byte  | 1 byte  | -128 to 127       |
| short | 2 bytes | -32,768 to 32,767 |
| int   | 4 bytes | -2^31 to 2^31 - 1 |
| long  | 8 bytes | -2^63 to 2^63 - 1 |

```java
public class IntegerTypes {
    public static void main(String[] args) {
        byte b = 100;
        short s = 30000;
        int i = 123456789;
        long l = 9876543210L;

        System.out.println("byte: " + b);
        System.out.println("short: " + s);
        System.out.println("int: " + i);
        System.out.println("long: " + l);
    }
}
```

---

### 🔹 Floating Point Types

| Type   | Size    | Precision          |
| ------ | ------- | ------------------ |
| float  | 4 bytes | 6-7 decimal digits |
| double | 8 bytes | 15 decimal digits  |

```java
public class FloatingTypes {
    public static void main(String[] args) {
        float pi = 3.14f;
        double bigPi = 3.14159265359;

        System.out.println("float: " + pi);
        System.out.println("double: " + bigPi);
    }
}
```

---

### 🔹 Character Type

| Type | Size    | Stores              |
| ---- | ------- | ------------------- |
| char | 2 bytes | Single Unicode char |

```java
public class CharType {
    public static void main(String[] args) {
        char letter = 'A';
        char unicodeChar = '\u263A';  // ☺

        System.out.println("Char: " + letter);
        System.out.println("Unicode Char: " + unicodeChar);
    }
}
```

---

### 🔹 Boolean Type

| Type    | Values      |
| ------- | ----------- |
| boolean | true, false |

```java
public class BooleanType {
    public static void main(String[] args) {
        boolean isJavaFun = true;
        boolean isFishTasty = false;

        System.out.println("Is Java Fun? " + isJavaFun);
        System.out.println("Is Fish Tasty? " + isFishTasty);
    }
}
```

---

## 🔸 2. Non-Primitive Data Types

These are **not predefined** like primitive types and can store  **multiple values** .

### 🔹 String

Stores a sequence of characters.

```java
public class StringExample {
    public static void main(String[] args) {
        String name = "Ayush";
        System.out.println("Name: " + name);
    }
}
```

---

### 🔹 Array

Stores multiple values of the same type.

```java
public class ArrayExample {
    public static void main(String[] args) {
        int[] numbers = {10, 20, 30, 40};

        for (int num : numbers) {
            System.out.println("Element: " + num);
        }
    }
}
```

---

### 🔹 Class & Object

A class is a blueprint for objects.

```java
class Car {
    String color = "Red";
}

public class ObjectExample {
    public static void main(String[] args) {
        Car myCar = new Car();
        System.out.println("Car color: " + myCar.color);
    }
}
```

---

## 📘 Type Conversion in Java

### 🔹 Implicit (Widening)

```java
int a = 10;
double b = a;  // automatically converts int to double
```

### 🔹 Explicit (Narrowing)

```java
double x = 9.78;
int y = (int) x;  // Manual casting: double to int
```

---

## 🔚 Summary Table

| Category       | Type      | Example                |
| -------------- | --------- | ---------------------- |
| Integer        | byte, int | `int x = 100;`       |
| Floating Point | float     | `float y = 5.5f;`    |
| Character      | char      | `char z = 'A';`      |
| Boolean        | boolean   | `boolean b = true;`  |
| String         | String    | `String s = "Hi"`    |
| Array          | int[]     | `int[] arr = {1,2}`  |
| Class/Object   | Custom    | `Car c = new Car();` |

---

## ✅ 1. **Program To Print Hello World**

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

---

## ✅ 2. **Perform Arithmetic Operations on Two Numbers**

```java
public class Arithmetic {
    public static void main(String[] args) {
        int a = 10, b = 5;
        System.out.println("Addition: " + (a + b));
        System.out.println("Subtraction: " + (a - b));
        System.out.println("Multiplication: " + (a * b));
        System.out.println("Division: " + (a / b));
        System.out.println("Modulus: " + (a % b));
    }
}
```

---

## ✅ 3. **Accept Values from User and Display Them**

```java
import java.util.Scanner;

public class AcceptDisplay {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a number: ");
        int num = sc.nextInt();

        System.out.print("Enter your name: ");
        String name = sc.next();  // Use nextLine() for full name with spaces

        System.out.println("Number: " + num);
        System.out.println("Name: " + name);
    }
}
```

---

## ✅ 4. **Accept 5 Subjects Marks, Calculate Total and Average**

```java
import java.util.Scanner;

public class MarksAverage {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter marks of Subject 1: ");
        int m1 = sc.nextInt();
        System.out.print("Enter marks of Subject 2: ");
        int m2 = sc.nextInt();
        System.out.print("Enter marks of Subject 3: ");
        int m3 = sc.nextInt();
        System.out.print("Enter marks of Subject 4: ");
        int m4 = sc.nextInt();
        System.out.print("Enter marks of Subject 5: ");
        int m5 = sc.nextInt();

        int total = m1 + m2 + m3 + m4 + m5;
        float average = total / 5f;

        System.out.println("Total Marks = " + total);
        System.out.println("Average Marks = " + average);
    }
}
```

---

## ✅ 5. **Calculate Area of Rectangle, Circle, Triangle, Square**

```java
import java.util.Scanner;

public class AreaShapes {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        // Rectangle
        System.out.print("Enter length and breadth of rectangle: ");
        float length = sc.nextFloat();
        float breadth = sc.nextFloat();
        float areaRect = length * breadth;
        System.out.println("Area of Rectangle = " + areaRect);

        // Circle
        System.out.print("Enter radius of circle: ");
        float radius = sc.nextFloat();
        float areaCircle = 3.14f * radius * radius;
        System.out.println("Area of Circle = " + areaCircle);

        // Triangle
        System.out.print("Enter base and height of triangle: ");
        float base = sc.nextFloat();
        float height = sc.nextFloat();
        float areaTriangle = 0.5f * base * height;
        System.out.println("Area of Triangle = " + areaTriangle);

        // Square
        System.out.print("Enter side of square: ");
        float side = sc.nextFloat();
        float areaSquare = side * side;
        System.out.println("Area of Square = " + areaSquare);
    }
}
```

---

## ✅ 6. **Calculate Square and Square Root of a Number**

```java
import java.util.Scanner;

public class SquareRoot {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a number: ");
        double num = sc.nextDouble();

        double square = num * num;
        double sqrt = Math.sqrt(num);

        System.out.println("Square: " + square);
        System.out.println("Square Root: " + sqrt);
    }
}
```

---

## ✅ 7. **Swap 2 Numbers With Temporary Variable**

```java
public class SwapWithTemp {
    public static void main(String[] args) {
        int a = 10, b = 20;
        System.out.println("Before Swap: a = " + a + ", b = " + b);

        int temp = a;
        a = b;
        b = temp;

        System.out.println("After Swap: a = " + a + ", b = " + b);
    }
}
```

---

## ✅ 8. **Swap 2 Numbers Without Temporary Variable**

```java
public class SwapWithoutTemp {
    public static void main(String[] args) {
        int a = 10, b = 20;
        System.out.println("Before Swap: a = " + a + ", b = " + b);

        a = a + b;  // a = 30
        b = a - b;  // b = 10
        a = a - b;  // a = 20

        System.out.println("After Swap: a = " + a + ", b = " + b);
    }
}
```

---

# IF - Else

## ✅ 1. **Check Whether the Number Is Positive or Negative**

```java
import java.util.Scanner;

public class PositiveNegative {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a number: ");
        int num = sc.nextInt();

        if (num > 0)
            System.out.println("The number is Positive.");
        else if (num < 0)
            System.out.println("The number is Negative.");
        else
            System.out.println("The number is Zero.");
    }
}
```

---

## ✅ 2. **Check Whether the Number Is Even or Odd**

```java
import java.util.Scanner;

public class EvenOdd {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a number: ");
        int num = sc.nextInt();

        if (num % 2 == 0)
            System.out.println("The number is Even.");
        else
            System.out.println("The number is Odd.");
    }
}
```

---

## ✅ 3. **Find the Greater of Two Numbers**

```java
import java.util.Scanner;

public class GreaterNumber {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter first number: ");
        int a = sc.nextInt();

        System.out.print("Enter second number: ");
        int b = sc.nextInt();

        if (a > b)
            System.out.println("Greater number is: " + a);
        else if (b > a)
            System.out.println("Greater number is: " + b);
        else
            System.out.println("Both numbers are equal.");
    }
}
```

---

## ✅ 4. **Check Whether the Entered Year Is a Leap Year**

```java
import java.util.Scanner;

public class LeapYear {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a year: ");
        int year = sc.nextInt();

        if ((year % 4 == 0 && year % 100 != 0) || (year % 400 == 0))
            System.out.println("It is a Leap Year.");
        else
            System.out.println("It is Not a Leap Year.");
    }
}
```

---

## ✅ 5. **Check Whether the Student Is Pass or Fail**

```java
import java.util.Scanner;

public class PassFail {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter marks: ");
        int marks = sc.nextInt();

        if (marks >= 35)
            System.out.println("Student is Pass.");
        else
            System.out.println("Student is Fail.");
    }
}
```

---

# If - else if - else

## ✅ 1. **Greatest of Three Numbers**

```java
import java.util.Scanner;

public class GreatestOfThree {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter three numbers: ");
        int a = sc.nextInt(), b = sc.nextInt(), c = sc.nextInt();

        if (a > b && a > c)
            System.out.println("Greatest is: " + a);
        else if (b > c)
            System.out.println("Greatest is: " + b);
        else
            System.out.println("Greatest is: " + c);
    }
}
```

---

## ✅ 2. **Usage of Comparison Operators**

```java
public class ComparisonOperators {
    public static void main(String[] args) {
        int a = 10, b = 20;

        System.out.println("a == b : " + (a == b));
        System.out.println("a != b : " + (a != b));
        System.out.println("a > b  : " + (a > b));
        System.out.println("a < b  : " + (a < b));
        System.out.println("a >= b : " + (a >= b));
        System.out.println("a <= b : " + (a <= b));
    }
}
```

---

## ✅ 3. **Display Day of the Week**

```java
import java.util.Scanner;

public class DayOfWeek {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter number (1 to 7): ");
        int day = sc.nextInt();

        if (day == 1)
            System.out.println("Monday");
        else if (day == 2)
            System.out.println("Tuesday");
        else if (day == 3)
            System.out.println("Wednesday");
        else if (day == 4)
            System.out.println("Thursday");
        else if (day == 5)
            System.out.println("Friday");
        else if (day == 6)
            System.out.println("Saturday");
        else if (day == 7)
            System.out.println("Sunday");
        else
            System.out.println("Invalid input");
    }
}
```

---

## ✅ 4. **Display Month of the Year**

```java
import java.util.Scanner;

public class MonthOfYear {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter number (1 to 12): ");
        int month = sc.nextInt();

        if (month == 1)
            System.out.println("January");
        else if (month == 2)
            System.out.println("February");
        else if (month == 3)
            System.out.println("March");
        else if (month == 4)
            System.out.println("April");
        else if (month == 5)
            System.out.println("May");
        else if (month == 6)
            System.out.println("June");
        else if (month == 7)
            System.out.println("July");
        else if (month == 8)
            System.out.println("August");
        else if (month == 9)
            System.out.println("September");
        else if (month == 10)
            System.out.println("October");
        else if (month == 11)
            System.out.println("November");
        else if (month == 12)
            System.out.println("December");
        else
            System.out.println("Invalid input");
    }
}
```

---

## ✅ 5. **Positive, Zero, or Negative**

```java
import java.util.Scanner;

public class PosZeroNeg {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int num = sc.nextInt();

        if (num > 0)
            System.out.println("Positive number");
        else if (num < 0)
            System.out.println("Negative number");
        else
            System.out.println("Zero");
    }
}
```

---

## ✅ 6. **Grade Assignment Based on Percentage**

```java
import java.util.Scanner;

public class GradeCalculator {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter total marks out of 500: ");
        int total = sc.nextInt();

        float percent = (total / 500f) * 100;

        if (percent >= 90)
            System.out.println("Grade: A+");
        else if (percent >= 75)
            System.out.println("Grade: A");
        else if (percent >= 60)
            System.out.println("Grade: B");
        else if (percent >= 50)
            System.out.println("Grade: C");
        else if (percent >= 35)
            System.out.println("Grade: D");
        else
            System.out.println("Grade: F (Fail)");
    }
}
```

---

## ✅ 7. **Simple Calculator**

```java
import java.util.Scanner;

public class SimpleCalculator {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter first number: ");
        float a = sc.nextFloat();

        System.out.print("Enter second number: ");
        float b = sc.nextFloat();

        System.out.print("Enter operator (+, -, *, /): ");
        char op = sc.next().charAt(0);

        if (op == '+')
            System.out.println("Result: " + (a + b));
        else if (op == '-')
            System.out.println("Result: " + (a - b));
        else if (op == '*')
            System.out.println("Result: " + (a * b));
        else if (op == '/')
            System.out.println("Result: " + (a / b));
        else
            System.out.println("Invalid operator.");
    }
}
```

---

## ✅ 8. **Triangle Type Checker**

```java
import java.util.Scanner;

public class TriangleCheck {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter three sides of triangle: ");
        int a = sc.nextInt(), b = sc.nextInt(), c = sc.nextInt();

        if (a + b > c && b + c > a && a + c > b) {
            System.out.println("Valid Triangle");
            if (a == b && b == c)
                System.out.println("Equilateral Triangle");
            else if (a == b || b == c || a == c)
                System.out.println("Isosceles Triangle");
            else
                System.out.println("Scalene Triangle");
        } else {
            System.out.println("Invalid Triangle");
        }
    }
}
```

---

## ✅ 9. **Discount Calculation**

```java
import java.util.Scanner;

public class DiscountCalc {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter purchase amount: ");
        float amount = sc.nextFloat();

        System.out.print("Are you a member? (yes/no): ");
        String member = sc.next();

        float discount = 0;

        if (amount > 1000) {
            if (member.equalsIgnoreCase("yes"))
                discount = amount * 0.20f;
            else
                discount = amount * 0.10f;
        } else {
            if (member.equalsIgnoreCase("yes"))
                discount = amount * 0.05f;
        }

        System.out.println("Discount: $" + discount);
        System.out.println("Final Price: $" + (amount - discount));
    }
}
```

---

## ✅ 10. **Loan Eligibility Checker**

```java
import java.util.Scanner;

public class LoanEligibility {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Are you employed? (yes/no): ");
        String employed = sc.next();

        if (employed.equalsIgnoreCase("yes")) {
            System.out.print("Enter your salary: ");
            float salary = sc.nextFloat();

            if (salary > 3000)
                System.out.println("Loan Approved");
            else {
                System.out.print("Enter your credit score: ");
                int score = sc.nextInt();

                if (score > 700)
                    System.out.println("Loan Approved");
                else
                    System.out.println("Loan Denied");
            }
        } else {
            System.out.println("Loan Denied");
        }
    }
}
```

---

# Foor Loop

### ✅ 1. **Program to Print the Table of a Number Entered by User**

```java
import java.util.Scanner;

public class MultiplicationTable {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int num = sc.nextInt();

        for (int i = 1; i <= 10; i++) {
            System.out.println(num + " x " + i + " = " + (num * i));
        }
    }
}
```

---

### ✅ 2. **Program to Print Prime Numbers in a Given Range**

```java
import java.util.Scanner;

public class PrimeInRange {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter starting number: ");
        int start = sc.nextInt();
        System.out.print("Enter ending number: ");
        int end = sc.nextInt();

        System.out.println("Prime numbers between " + start + " and " + end + " are:");
        for (int i = start; i <= end; i++) {
            boolean isPrime = true;
            if (i <= 1) continue;
            for (int j = 2; j <= i / 2; j++) {
                if (i % j == 0) {
                    isPrime = false;
                    break;
                }
            }
            if (isPrime)
                System.out.println(i);
        }
    }
}
```

---

### ✅ 3. **Program to Find the Fibonacci Series (First `n` Numbers)**

```java
import java.util.Scanner;

public class FibonacciSeries {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter how many Fibonacci numbers to print: ");
        int count = sc.nextInt();

        int a = 0, b = 1, c;
        System.out.print("Fibonacci Series: " + a + " " + b + " ");
        for (int i = 3; i <= count; i++) {
            c = a + b;
            System.out.print(c + " ");
            a = b;
            b = c;
        }
    }
}
```

---

### ✅ 4. **Program to Print Numbers from 1 to 10**

```java
public class OneToTen {
    public static void main(String[] args) {
        System.out.println("Numbers from 1 to 10:");
        for (int i = 1; i <= 10; i++) {
            System.out.println(i);
        }
    }
}
```

---

# Pattern Printing

### ✅ 1. **Right-Angled Triangle (Stars)**

```
*
* *
* * *
* * * *
* * * * *
```

```java
public class Pattern1 {
    public static void main(String[] args) {
        for (int i = 1; i <= 5; i++) {
            for (int j = 1; j <= i; j++)
                System.out.print("* ");
            System.out.println();
        }
    }
}
```

---

### ✅ 2. **Inverted Right-Angled Triangle**

```
* * * * *
* * * *
* * *
* *
*
```

```java
public class Pattern2 {
    public static void main(String[] args) {
        for (int i = 5; i >= 1; i--) {
            for (int j = 1; j <= i; j++)
                System.out.print("* ");
            System.out.println();
        }
    }
}
```

---

### ✅ 3. **Right-Angled Triangle (Numbers)**

```
1
1 2
1 2 3
1 2 3 4
```

```java
public class Pattern3 {
    public static void main(String[] args) {
        for (int i = 1; i <= 4; i++) {
            for (int j = 1; j <= i; j++)
                System.out.print(j + " ");
            System.out.println();
        }
    }
}
```

---

### ✅ 4. **Right-Angled Triangle (Same Numbers)**

```
1
2 2
3 3 3
4 4 4 4
```

```java
public class Pattern4 {
    public static void main(String[] args) {
        for (int i = 1; i <= 4; i++) {
            for (int j = 1; j <= i; j++)
                System.out.print(i + " ");
            System.out.println();
        }
    }
}
```

---

### ✅ 5. **Right-Aligned Triangle (Stars)**

```
        *
      * *
    * * *
  * * * *
* * * * *
```

```java
public class Pattern5 {
    public static void main(String[] args) {
        for (int i = 1; i <= 5; i++) {
            for (int s = 5; s > i; s--)
                System.out.print("  ");
            for (int j = 1; j <= i; j++)
                System.out.print("* ");
            System.out.println();
        }
    }
}
```

---

### ✅ 6. **Pyramid Pattern**

```
    *
   * *
  * * *
 * * * *
```

```java
public class Pattern6 {
    public static void main(String[] args) {
        for (int i = 1; i <= 4; i++) {
            for (int s = 4; s > i; s--)
                System.out.print(" ");
            for (int j = 1; j <= i; j++)
                System.out.print("* ");
            System.out.println();
        }
    }
}
```

---

### ✅ 7. **Inverted Number Pattern**

```
1 2 3 4 5
1 2 3 4
1 2 3
1 2
1
```

```java
public class Pattern7 {
    public static void main(String[] args) {
        for (int i = 5; i >= 1; i--) {
            for (int j = 1; j <= i; j++)
                System.out.print(j + " ");
            System.out.println();
        }
    }
}
```

---

### ✅ 8. **Half Pyramid with Alphabets**

```
A
A B
A B C
A B C D
```

```java
public class Pattern8 {
    public static void main(String[] args) {
        for (char i = 'A'; i <= 'D'; i++) {
            for (char j = 'A'; j <= i; j++)
                System.out.print(j + " ");
            System.out.println();
        }
    }
}
```

---

### ✅ 9. **Full Pyramid (Stars)**

```
    *
   * * 
  * * * 
 * * * *
```

```java
public class Pattern9 {
    public static void main(String[] args) {
        for (int i = 1; i <= 4; i++) {
            for (int s = 4; s > i; s--)
                System.out.print(" ");
            for (int j = 1; j <= i; j++)
                System.out.print("* ");
            System.out.println();
        }
    }
}
```

---

### ✅ 10. **Diamond Pattern**

```
   *
  * *
 * * *
* * * *
 * * *
  * *
   *
```

```java
public class Pattern10 {
    public static void main(String[] args) {
        int i, j, space = 3;
        for (i = 1; i <= 4; i++) {
            for (j = 1; j <= space; j++)
                System.out.print(" ");
            space--;
            for (j = 1; j <= i; j++)
                System.out.print("* ");
            System.out.println();
        }
        space = 1;
        for (i = 3; i >= 1; i--) {
            for (j = 1; j <= space; j++)
                System.out.print(" ");
            space++;
            for (j = 1; j <= i; j++)
                System.out.print("* ");
            System.out.println();
        }
    }
}
```

---

# While Loop

### ✅ 1. **Print Numbers from 1 to 10 using `while` loop**

```java
public class Print1to10 {
    public static void main(String[] args) {
        int i = 1;
        while (i <= 10) {
            System.out.println(i);
            i++;
        }
    }
}
```

---

### ✅ 2. **Check if a Number is an Armstrong Number**

(Example: 153 → 1³ + 5³ + 3³ = 153)

```java
import java.util.Scanner;

public class ArmstrongNumber {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int num = sc.nextInt(), sum = 0, temp = num;

        while (temp != 0) {
            int rem = temp % 10;
            sum += rem * rem * rem;
            temp = temp / 10;
        }

        if (sum == num)
            System.out.println(num + " is an Armstrong Number.");
        else
            System.out.println(num + " is not an Armstrong Number.");
    }
}
```

---

### ✅ 3. **Check the Reverse of a Number**

```java
import java.util.Scanner;

public class ReverseNumber {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int num = sc.nextInt(), rev = 0;

        while (num != 0) {
            int digit = num % 10;
            rev = rev * 10 + digit;
            num /= 10;
        }

        System.out.println("Reversed number: " + rev);
    }
}
```

---

### ✅ 4. **Check Whether a Number is Palindrome or Not**

```java
import java.util.Scanner;

public class PalindromeNumber {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int num = sc.nextInt(), rev = 0, temp = num;

        while (temp != 0) {
            int digit = temp % 10;
            rev = rev * 10 + digit;
            temp /= 10;
        }

        if (num == rev)
            System.out.println(num + " is a Palindrome.");
        else
            System.out.println(num + " is not a Palindrome.");
    }
}
```

---

### ✅ 5. **Print `n` Odd Numbers in Descending Order**

```java
import java.util.Scanner;

public class OddDescending {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter how many odd numbers to print: ");
        int n = sc.nextInt();

        int count = 0, num = n * 2 - 1;
        while (count < n) {
            System.out.print(num + " ");
            num -= 2;
            count++;
        }
    }
}
```

---

### ✅ 6. **Print Series: `1 4 7 10 ... 40`**

```java
public class Series1 {
    public static void main(String[] args) {
        int i = 1;
        while (i <= 40) {
            System.out.print(i + " ");
            i += 3;
        }
    }
}
```

---

### ✅ 7. **Print Series: `1 -4 7 -10 ... -40`**

```java
public class Series2 {
    public static void main(String[] args) {
        int i = 1;
        int count = 1;

        while (i <= 40) {
            if (count % 2 == 0)
                System.out.print(-i + " ");
            else
                System.out.print(i + " ");
            i += 3;
            count++;
        }
    }
}
```

---

### ✅ 8. **Print Series: `-1 4 -7 10 ... 40`**

```java
public class Series3 {
    public static void main(String[] args) {
        int i = 1;
        int count = 1;

        while (i <= 40) {
            if (count % 2 != 0)
                System.out.print(-i + " ");
            else
                System.out.print(i + " ");
            i += 3;
            count++;
        }
    }
}
```


---

# Do-while Loop

### ✅ 1. **Print Numbers from 1 to 10**

```java
public class DoWhile1 {
    public static void main(String[] args) {
        int i = 1;
        do {
            System.out.println(i);
            i++;
        } while (i <= 10);
    }
}
```

---

### ✅ 2. **Print the Sum of First `n` Natural Numbers**

```java
import java.util.Scanner;

public class DoWhile2 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter n: ");
        int n = sc.nextInt();
        int sum = 0, i = 1;

        do {
            sum += i;
            i++;
        } while (i <= n);

        System.out.println("Sum = " + sum);
    }
}
```

---

### ✅ 3. **Reverse a Number**

```java
import java.util.Scanner;

public class DoWhile3 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int num = sc.nextInt(), rev = 0;

        do {
            int digit = num % 10;
            rev = rev * 10 + digit;
            num /= 10;
        } while (num != 0);

        System.out.println("Reversed Number = " + rev);
    }
}
```

---

### ✅ 4. **Print the Multiplication Table of a Number**

```java
import java.util.Scanner;

public class DoWhile4 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int num = sc.nextInt();
        int i = 1;

        do {
            System.out.println(num + " x " + i + " = " + (num * i));
            i++;
        } while (i <= 10);
    }
}
```

---

### ✅ 5. **Menu-Driven Calculator (Add, Subtract, Exit)**

```java
import java.util.Scanner;

public class DoWhile5 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int choice;

        do {
            System.out.println("\n1. Add\n2. Subtract\n3. Exit");
            System.out.print("Enter choice: ");
            choice = sc.nextInt();

            if (choice == 1 || choice == 2) {
                System.out.print("Enter two numbers: ");
                int a = sc.nextInt();
                int b = sc.nextInt();

                if (choice == 1)
                    System.out.println("Sum = " + (a + b));
                else
                    System.out.println("Difference = " + (a - b));
            } else if (choice != 3) {
                System.out.println("Invalid choice!");
            }
        } while (choice != 3);

        System.out.println("Exited.");
    }
}
```

---

# Strings

---

### ✅ 1. **Accept and Display a String**

```java
import java.util.Scanner;

public class StringAcceptDisplay {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a string: ");
        String input = sc.nextLine();

        System.out.println("You entered: " + input);
    }
}
```

---

### ✅ 2. **Find the Length of a String**

```java
import java.util.Scanner;

public class StringLength {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a string: ");
        String str = sc.nextLine();

        System.out.println("Length: " + str.length());
    }
}
```

---

### ✅ 3. **Compare Two Strings**

```java
import java.util.Scanner;

public class StringCompare {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter first string: ");
        String s1 = sc.nextLine();
        System.out.print("Enter second string: ");
        String s2 = sc.nextLine();

        if (s1.equals(s2))
            System.out.println("Strings are equal.");
        else
            System.out.println("Strings are not equal.");
    }
}
```

---

### ✅ 4. **Copy One String to Another**

```java
import java.util.Scanner;

public class StringCopy {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a string to copy: ");
        String original = sc.nextLine();

        String copied = original;

        System.out.println("Copied string: " + copied);
    }
}
```

---

### ✅ 5. **Concatenate Two Strings**

```java
import java.util.Scanner;

public class StringConcat {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter first string: ");
        String s1 = sc.nextLine();
        System.out.print("Enter second string: ");
        String s2 = sc.nextLine();

        String result = s1 + s2;
        System.out.println("Concatenated string: " + result);
    }
}
```

---

### ✅ 6. **Convert Uppercase to Lowercase and Vice Versa**

```java
import java.util.Scanner;

public class StringCaseConversion {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a string: ");
        String str = sc.nextLine();

        String upper = str.toUpperCase();
        String lower = str.toLowerCase();

        System.out.println("Uppercase: " + upper);
        System.out.println("Lowercase: " + lower);
    }
}
```

---

### ✅ 7. **Print Common Letters in Two Strings**

```java
import java.util.Scanner;

public class CommonLetters {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter first string: ");
        String s1 = sc.nextLine().toLowerCase();
        System.out.print("Enter second string: ");
        String s2 = sc.nextLine().toLowerCase();

        System.out.print("Common letters: ");
        for (int i = 0; i < s1.length(); i++) {
            char ch = s1.charAt(i);
            if (s2.indexOf(ch) != -1 && ch != ' ') {
                System.out.print(ch + " ");
                s2 = s2.replaceFirst(Character.toString(ch), ""); // Avoid duplicates
            }
        }
    }
}
```

---

# Java Arrays

### What is an Array?

* An **array** is a container object that holds a fixed number of values of a single type.
* The length of an array is established when the array is created. After creation, its length is fixed.
* Arrays store elements in **contiguous memory locations** and use an index starting from 0.

---

## Declaring and Initializing Arrays

```java
// Declaration
int[] numbers;          // Preferred style
int numbers2[];         // Also valid, less common

// Initialization
numbers = new int[5];   // Array of 5 integers (default 0)
```

Or combined:

```java
int[] numbers = new int[5];        // size 5, all zeros

int[] values = {1, 2, 3, 4, 5};    // initialize with values
```

---

## Accessing Array Elements

```java
int first = values[0];    // Access first element (1)
values[2] = 10;           // Change 3rd element to 10
```

---

## Common Array Methods and Usage

Java arrays themselves are basic, but **`java.util.Arrays`** class provides many utility methods.

Import:

```java
import java.util.Arrays;
```

### 1. **Printing an Array**

```java
int[] arr = {1, 2, 3, 4, 5};
System.out.println(Arrays.toString(arr));  
// Output: [1, 2, 3, 4, 5]
```

---

### 2. **Sorting an Array**

```java
int[] arr = {5, 3, 8, 1, 2};
Arrays.sort(arr);
System.out.println(Arrays.toString(arr));  
// Output: [1, 2, 3, 5, 8]
```

---

### 3. **Searching an Element**

Binary search (array must be sorted):

```java
int[] arr = {1, 2, 3, 4, 5};
int index = Arrays.binarySearch(arr, 3);
System.out.println(index);  // Output: 2 (index of element 3)
```

If element not found, returns negative value.

---

### 4. **Copying Arrays**

```java
int[] arr = {1, 2, 3};
int[] copy = Arrays.copyOf(arr, arr.length);
System.out.println(Arrays.toString(copy));  
// Output: [1, 2, 3]
```

---

### 5. **Filling Arrays**

```java
int[] arr = new int[5];
Arrays.fill(arr, 7);
System.out.println(Arrays.toString(arr));  
// Output: [7, 7, 7, 7, 7]
```

---

### 6. **Comparing Arrays**

```java
int[] arr1 = {1, 2, 3};
int[] arr2 = {1, 2, 3};
int[] arr3 = {3, 2, 1};

System.out.println(Arrays.equals(arr1, arr2));  // true
System.out.println(Arrays.equals(arr1, arr3));  // false
```

---

## Example: Using Arrays in a Program

```java
import java.util.Arrays;
import java.util.Scanner;

public class ArrayExample {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int[] numbers = new int[5];

        System.out.println("Enter 5 numbers:");
        for (int i = 0; i < 5; i++) {
            numbers[i] = sc.nextInt();
        }

        System.out.println("You entered: " + Arrays.toString(numbers));

        Arrays.sort(numbers);
        System.out.println("Sorted array: " + Arrays.toString(numbers));

        int searchFor = 3;
        int index = Arrays.binarySearch(numbers, searchFor);
        if (index >= 0)
            System.out.println(searchFor + " found at index " + index);
        else
            System.out.println(searchFor + " not found.");
    }
}
```

---

## Important Notes

* Arrays are  **fixed size** . To work with dynamic lists, use **ArrayList** (from `java.util`).
* Array index starts at 0 and ends at length-1.
* Accessing invalid index throws `ArrayIndexOutOfBoundsException`.

---
