
# 📘 Java Strings – Notes with All Methods

---

## ✅ What is a String?

* A **String** is a sequence of characters.
* Strings in Java are  **immutable** , meaning once created, they cannot be changed.
* Stored in **String Pool** in memory.

### Declaration:

```java
String s1 = "Hello";              // Using String literal
String s2 = new String("World");  // Using new keyword
```

---

## 🔹 Commonly Used String Methods with Examples

---

### 1. **`length()`**

Returns the number of characters in the string.

```java
String s = "Java";
System.out.println(s.length());  // Output: 4
```

---

### 2. **`charAt(int index)`**

Returns the character at the specified index.

```java
String s = "Java";
System.out.println(s.charAt(2));  // Output: v
```

---

### 3. **`equals(String another)`**

Checks if two strings are exactly equal (case-sensitive).

```java
String a = "Java";
String b = "Java";
System.out.println(a.equals(b));  // Output: true
```

---

### 4. **`equalsIgnoreCase(String another)`**

Compares strings ignoring case differences.

```java
String a = "hello";
String b = "HELLO";
System.out.println(a.equalsIgnoreCase(b));  // Output: true
```

---

### 5. **`toUpperCase()` / `toLowerCase()`**

Converts the entire string to upper or lower case.

```java
String s = "Java";
System.out.println(s.toUpperCase());  // Output: JAVA
System.out.println(s.toLowerCase());  // Output: java
```

---

### 6. **`indexOf(char)` / `lastIndexOf(char)`**

Finds index of first/last occurrence of a character.

```java
String s = "Programming";
System.out.println(s.indexOf('g'));     // Output: 3
System.out.println(s.lastIndexOf('g')); // Output: 10
```

---

### 7. **`contains(String)`**

Checks if the string contains a specific sequence.

```java
String s = "Welcome";
System.out.println(s.contains("come"));  // Output: true
```

---

### 8. **`startsWith(String)` / `endsWith(String)`**

Checks beginning and ending of the string.

```java
String s = "Java Programming";
System.out.println(s.startsWith("Java")); // true
System.out.println(s.endsWith("ing"));    // true
```

---

### 9. **`replace(char, char)`**

Replaces a character with another.

```java
String s = "banana";
System.out.println(s.replace('a', 'o'));  // Output: bonono
```

---

### 10. **`substring(int start, int end)`**

Returns a part of the string from `start` to `end - 1`.

```java
String s = "HelloWorld";
System.out.println(s.substring(0, 5));  // Output: Hello
```

---

### 11. **`trim()`**

Removes leading and trailing white spaces.

```java
String s = "   Hello Java   ";
System.out.println(s.trim());  // Output: Hello Java
```

---

### 12. **`split(String delimiter)`**

Splits the string into an array.

```java
String s = "apple,banana,mango";
String[] arr = s.split(",");
for (String fruit : arr)
    System.out.println(fruit);
// Output: apple
//         banana
//         mango
```

---

### 13. **`isEmpty()`**

Checks if the string is empty (length = 0).

```java
String s = "";
System.out.println(s.isEmpty());  // Output: true
```

---

### 14. **`compareTo(String)`**

Compares two strings lexicographically.

```java
String a = "Apple";
String b = "Banana";
System.out.println(a.compareTo(b));  // Output: Negative (A < B)
```

---

### 15. **`valueOf()`**

Converts other data types to String.

```java
int n = 100;
String s = String.valueOf(n);
System.out.println(s + 10);  // Output: 10010 (String concatenation)
```

---

### 16. **`concat(String)`**

Concatenates one string to another.

```java
String s1 = "Hello";
String s2 = "World";
System.out.println(s1.concat(s2));  // Output: HelloWorld
```

---

## 🔹 Program: Accept a String and Display All Methods

```java
import java.util.Scanner;

public class StringMethodsDemo {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a string: ");
        String str = sc.nextLine();

        System.out.println("Length: " + str.length());
        System.out.println("First char: " + str.charAt(0));
        System.out.println("Uppercase: " + str.toUpperCase());
        System.out.println("Lowercase: " + str.toLowerCase());
        System.out.println("Trimmed: " + str.trim());
        System.out.println("Starts with 'H': " + str.startsWith("H"));
        System.out.println("Ends with 'd': " + str.endsWith("d"));
        System.out.println("Contains 'Java': " + str.contains("Java"));
    }
}
```

---

## 🧠 Summary Table

| Method                 | Description                   |
| ---------------------- | ----------------------------- |
| `length()`           | Returns string length         |
| `charAt(i)`          | Returns character at index    |
| `equals()`           | Compares two strings          |
| `equalsIgnoreCase()` | Case-insensitive comparison   |
| `toUpperCase()`      | Converts to uppercase         |
| `toLowerCase()`      | Converts to lowercase         |
| `indexOf()`          | First occurrence of character |
| `lastIndexOf()`      | Last occurrence of character  |
| `contains()`         | Checks substring              |
| `replace()`          | Replaces characters           |
| `substring()`        | Extracts part of string       |
| `trim()`             | Removes whitespace            |
| `split()`            | Splits string into array      |
| `isEmpty()`          | Checks if string is empty     |
| `compareTo()`        | Lexicographical comparison    |
| `valueOf()`          | Converts values to string     |
| `concat()`           | Joins strings                 |


---

# 📘 OOPs in Java – Part 1

---

## 🔰 What is OOP?

**Object-Oriented Programming (OOP)** is a programming paradigm based on the concept of  **“objects”** , which contain data (fields) and code (methods).

---

## 🔹 Four Pillars of OOP

### 1. **Class**

* A **class** is a blueprint or template for creating objects.
* It contains **fields (variables)** and  **methods (functions)** .

#### ✅ Example:

```java
class Student {
    // Fields
    String name;
    int age;

    // Method
    void display() {
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
    }
}
```

---

### 2. **Object**

* An **object** is an instance of a class. It holds real values of the fields defined in the class.

#### ✅ Example:

```java
public class Main {
    public static void main(String[] args) {
        Student s1 = new Student();  // Creating object
        s1.name = "Ayush";
        s1.age = 20;
        s1.display();
    }
}
```

---

### 3. **Encapsulation**

* Encapsulation is **binding data and code together** into a single unit (class).
* Achieved by making variables **private** and using **getters/setters** to access them.

#### ✅ Example:

```java
class Employee {
    private int salary;  // private field

    // Getter
    public int getSalary() {
        return salary;
    }

    // Setter
    public void setSalary(int s) {
        salary = s;
    }
}
```

```java
public class Main {
    public static void main(String[] args) {
        Employee emp = new Employee();
        emp.setSalary(50000);
        System.out.println("Salary: " + emp.getSalary());
    }
}
```

---

### 4. **Abstraction**

* Hiding the internal implementation and showing only necessary details.
* Done using **abstract classes** or  **interfaces** .

#### ✅ Example with Abstract Class:

```java
abstract class Animal {
    abstract void sound();  // Abstract method
}

class Dog extends Animal {
    void sound() {
        System.out.println("Dog barks");
    }
}
```

```java
public class Main {
    public static void main(String[] args) {
        Animal obj = new Dog();
        obj.sound();  // Output: Dog barks
    }
}
```

---

## 🧱 More Concepts to be Covered in Part 2:

* Inheritance
* Polymorphism (Method Overloading and Overriding)
* Interface vs Abstract Class
* Constructors & Types
* ‘this’ and ‘super’ keyword

---

## ✅ Summary Table

| Concept       | Definition                       | Keyword/Example             |
| ------------- | -------------------------------- | --------------------------- |
| Class         | Blueprint for objects            | `class`                   |
| Object        | Instance of class                | `new`keyword              |
| Encapsulation | Hiding data with getters/setters | `private`,`get`,`set` |
| Abstraction   | Hiding complex implementation    | `abstract`,`interface`  |

---


Great! Here's your complete **OOPs Part 2** in Java — covering the remaining major pillars and features:  **Inheritance** ,  **Polymorphism** ,  **Constructors** ,  **‘this’ and ‘super’ keywords** , etc., with  **clear explanations and full Java examples** .

---

# 📘 OOPs in Java – Part 2

---

## 🔸 5. Inheritance

Inheritance is the process where **one class (child)** inherits the properties and methods of  **another class (parent)** .

### ✅ Types:

* **Single Inheritance**
* **Multilevel Inheritance**
* **Hierarchical Inheritance**

> ❌ Java does not support **multiple inheritance** using classes (but supports it with interfaces).

### ✅ Example: Single Inheritance

```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks");
    }
}
```

```java
public class Main {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.sound();  // Inherited
        d.bark();   // Own method
    }
}
```

---

## 🔸 6. Polymorphism

Polymorphism means  **“many forms”** . A single function can behave differently in different contexts.

### ✅ Types:

* **Compile-time (Method Overloading)**
* **Run-time (Method Overriding)**

---

### 🔹 a) Method Overloading

Same method name with  **different parameters** .

```java
class Calculator {
    void add(int a, int b) {
        System.out.println("Sum = " + (a + b));
    }

    void add(double a, double b) {
        System.out.println("Sum = " + (a + b));
    }
}
```

```java
public class Main {
    public static void main(String[] args) {
        Calculator c = new Calculator();
        c.add(5, 10);         // Calls int version
        c.add(5.5, 2.3);      // Calls double version
    }
}
```

---

### 🔹 b) Method Overriding

Same method name and parameters in **child class** as parent class. Overrides the behavior.

```java
class Vehicle {
    void run() {
        System.out.println("Vehicle is running");
    }
}

class Bike extends Vehicle {
    void run() {
        System.out.println("Bike is running fast");
    }
}
```

```java
public class Main {
    public static void main(String[] args) {
        Vehicle v = new Bike();
        v.run();  // Output: Bike is running fast
    }
}
```

---

## 🔸 7. Constructor in Java

A **constructor** is a special method that runs when an object is created.

### ✅ Types of Constructors:

* **Default Constructor**
* **Parameterized Constructor**
* **Copy Constructor** (not built-in, but can be made manually)

### ✅ Example:

```java
class Student {
    String name;
    int age;

    // Parameterized Constructor
    Student(String n, int a) {
        name = n;
        age = a;
    }

    void display() {
        System.out.println(name + " - " + age);
    }
}
```

```java
public class Main {
    public static void main(String[] args) {
        Student s1 = new Student("Ayush", 20);
        s1.display();
    }
}
```

---

## 🔸 8. The `this` Keyword

* Refers to  **current object** .
* Resolves **naming conflicts** between instance and local variables.

```java
class Test {
    int x;

    Test(int x) {
        this.x = x;  // 'this' differentiates the class variable and local variable
    }

    void show() {
        System.out.println("x = " + x);
    }
}
```

---

## 🔸 9. The `super` Keyword

* Refers to  **parent class** .
* Used to call **parent class constructor** or method.

```java
class A {
    A() {
        System.out.println("Class A Constructor");
    }
}

class B extends A {
    B() {
        super();  // Calls parent class constructor
        System.out.println("Class B Constructor");
    }
}
```

```java
public class Main {
    public static void main(String[] args) {
        B obj = new B();
    }
}
```

---

## ✅ Summary Table

| Concept     | Description                              | Example Keyword   |
| ----------- | ---------------------------------------- | ----------------- |
| Inheritance | Inherit fields/methods from parent class | `extends`       |
| Overloading | Same method name, different parameters   | `add(int, int)` |
| Overriding  | Redefine parent method in child class    | `@Override`     |
| Constructor | Special method to initialize objects     | `ClassName()`   |
| this        | Refers to current object                 | `this.x = x;`   |
| super       | Refers to parent class                   | `super()`       |

---

### ✅ Complete OOPs Covered in Part 1 + 2:

| Topic          | Status |
| -------------- | ------ |
| Class & Object | ✅     |
| Encapsulation  | ✅     |
| Abstraction    | ✅     |
| Inheritance    | ✅     |
| Polymorphism   | ✅     |
| Constructors   | ✅     |
| this & super   | ✅     |

---


## ✅ Why Only 3 Types of Inheritance in Java?

Java supports the following  **three inheritance types using classes** :

| Type                                         | Supported in Java   | Description                                                                       |
| -------------------------------------------- | ------------------- | --------------------------------------------------------------------------------- |
| **Single Inheritance**                 | ✅ Yes              | One child inherits from one parent                                                |
| **Multilevel Inheritance**             | ✅ Yes              | Child inherits from parent, which inherits from another                           |
| **Hierarchical Inheritance**           | ✅ Yes              | Multiple children inherit from one parent                                         |
| **Multiple Inheritance (via classes)** | ❌ No               | Java doesn't support it**with classes**to avoid ambiguity (Diamond Problem) |
| **Hybrid Inheritance**                 | ❌ No (via classes) | Combination of multiple types — supported only via**interfaces**           |

---

## 🔸 1. Single Inheritance

```java
class Animal {
    void eat() {
        System.out.println("Eating...");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Barking...");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.eat();   // inherited
        d.bark();  // own
    }
}
```

---

## 🔸 2. Multilevel Inheritance

```java
class Animal {
    void eat() {
        System.out.println("Eating...");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Barking...");
    }
}

class Puppy extends Dog {
    void weep() {
        System.out.println("Weeping...");
    }
}

public class Main {
    public static void main(String[] args) {
        Puppy p = new Puppy();
        p.eat();   // grandparent
        p.bark();  // parent
        p.weep();  // child
    }
}
```

---

## 🔸 3. Hierarchical Inheritance

```java
class Animal {
    void sound() {
        System.out.println("Animal sound...");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks...");
    }
}

class Cat extends Animal {
    void meow() {
        System.out.println("Cat meows...");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.sound();
        d.bark();

        Cat c = new Cat();
        c.sound();
        c.meow();
    }
}
```

---

## 🔴 Why Java Doesn’t Support Multiple Inheritance via Classes?

Let’s say you have this setup:

```java
class A {
    void show() {
        System.out.println("A");
    }
}

class B {
    void show() {
        System.out.println("B");
    }
}

// class C extends A, B ❌ This is not allowed in Java
```

If `class C` tries to inherit from both `A` and `B`, which version of `show()` should it inherit? This leads to  **ambiguity** , known as the  **Diamond Problem** .

---

## ✅ Java Solution: Use **Interfaces** for Multiple Inheritance

```java
interface A {
    void show();
}

interface B {
    void display();
}

class C implements A, B {
    public void show() {
        System.out.println("From A");
    }

    public void display() {
        System.out.println("From B");
    }
}
```

---

## ✅ Final Summary

| Inheritance Type | Supports via Class | Supports via Interface | Example |
| ---------------- | ------------------ | ---------------------- | ------- |
| Single           | ✅ Yes             | ✅ Yes                 | ✔️    |
| Multilevel       | ✅ Yes             | ✅ Yes                 | ✔️    |
| Hierarchical     | ✅ Yes             | ✅ Yes                 | ✔️    |
| Multiple         | ❌ No              | ✅ Yes                 | ✔️    |
| Hybrid           | ❌ No              | ✅ Yes                 | ✔️    |

---

# 📘 OOPs in Java – Part 3 (Advanced OOP Concepts)

---

## 🔸 1. Interface in Java

### 🔹 What is an Interface?

* An interface is a **completely abstract class** that defines a list of  **abstract methods** .
* It is used to achieve **multiple inheritance** in Java.

### ✅ Rules:

* All methods are `public` and `abstract` by default.
* No constructors or instance fields allowed.
* A class uses `implements` to inherit from an interface.

### ✅ Example:

```java
interface Animal {
    void eat();
    void sleep();
}

class Dog implements Animal {
    public void eat() {
        System.out.println("Dog eats bones");
    }

    public void sleep() {
        System.out.println("Dog sleeps at night");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.eat();
        d.sleep();
    }
}
```

---

## 🔸 2. Static Keyword

### ✅ Uses of `static`:

* **Static Variable** : Shared among all objects.
* **Static Method** : Can be called without creating object.
* **Static Block** : Executes once when class is loaded.

### ✅ Example:

```java
class Counter {
    static int count = 0;

    Counter() {
        count++;
        System.out.println(count);
    }

    static void greet() {
        System.out.println("Hello from static method");
    }
}

public class Main {
    public static void main(String[] args) {
        Counter c1 = new Counter();  // 1
        Counter c2 = new Counter();  // 2
        Counter.greet();             // No object needed
    }
}
```

---

## 🔸 3. Final Keyword

### ✅ Usage of `final`:

* `final variable` = constant (cannot change value)
* `final method` = cannot override
* `final class` = cannot inherit

### ✅ Example:

```java
final class Shape {
    final int sides = 4;

    final void display() {
        System.out.println("Shape has " + sides + " sides");
    }
}

// class Rectangle extends Shape ❌ Not allowed, because Shape is final
```

---

## 🔸 4. Types of Constructors

### ✅ a) Default Constructor

```java
class Student {
    Student() {
        System.out.println("Default constructor called");
    }
}
```

### ✅ b) Parameterized Constructor

```java
class Student {
    String name;

    Student(String n) {
        name = n;
    }

    void show() {
        System.out.println("Name: " + name);
    }
}
```

### ✅ c) Copy Constructor (manual in Java)

```java
class Student {
    String name;

    Student(String n) {
        name = n;
    }

    // Copy constructor
    Student(Student s) {
        name = s.name;
    }

    void show() {
        System.out.println("Name: " + name);
    }
}
```

```java
public class Main {
    public static void main(String[] args) {
        Student s1 = new Student("Ayush");
        Student s2 = new Student(s1);
        s2.show();  // Output: Ayush
    }
}
```

---

## 🔸 5. Packages in Java

### ✅ What is a Package?

* A **package** is a namespace that organizes classes and interfaces.
* Think of it as a folder in a directory.
* Helps avoid class name conflicts.

### ✅ Creating a Package:

```java
// File: MyPackage/Message.java
package MyPackage;

public class Message {
    public void show() {
        System.out.println("Hello from Package!");
    }
}
```

### ✅ Using a Package:

```java
import MyPackage.Message;

public class Main {
    public static void main(String[] args) {
        Message msg = new Message();
        msg.show();
    }
}
```

---

## ✅ Summary Table

| Concept      | Description                            | Keyword         |
| ------------ | -------------------------------------- | --------------- |
| Interface    | Abstract type for multiple inheritance | `interface`   |
| Static       | Class-level members                    | `static`      |
| Final        | Constant / Non-changeable              | `final`       |
| Constructors | Special methods to initialize objects  | `ClassName()` |
| Package      | Folder-like structure for classes      | `package`     |

---

## 🧱 Complete OOPs So Far:

| Part | Concepts Covered                                                |
| ---- | --------------------------------------------------------------- |
| 1    | Class, Object, Encapsulation, Abstraction                       |
| 2    | Inheritance (All Types), Polymorphism, this, super, Constructor |
| 3    | Interface, Static, Final, All Constructors, Packages            |

---


# 📘 Exception Handling in Java

---

## 1. What is an Exception?

* An **exception** is an **unexpected event** that disrupts the normal flow of a program during execution.
* It can occur due to various reasons like invalid input, division by zero, file not found, etc.
* Exceptions help in handling errors gracefully without crashing the program.

---

## 2. Types of Exceptions

| Type                          | Description                                          | Examples                                         |
| ----------------------------- | ---------------------------------------------------- | ------------------------------------------------ |
| **Checked Exception**   | Checked at compile time, must be handled or declared | `IOException`,`SQLException`                 |
| **Unchecked Exception** | Occurs at runtime, not checked at compile time       | `ArithmeticException`,`NullPointerException` |
| **Error**               | Serious problems not meant to be caught              | `OutOfMemoryError`,`StackOverflowError`      |

---

## 3. Exception Handling Keywords

| Keyword     | Description                                                                 |
| ----------- | --------------------------------------------------------------------------- |
| `try`     | Block where code that might throw exception is written                      |
| `catch`   | Block to handle the exception thrown by try block                           |
| `finally` | Block executed**always** , whether exception occurs or not            |
| `throw`   | Used to**explicitly throw**an exception                               |
| `throws`  | Declares exceptions a method**might throw**(used in method signature) |

---

## 4. Syntax of Try-Catch-Finally

```java
try {
    // Code that may throw exception
} catch (ExceptionType1 e1) {
    // Handle ExceptionType1
} catch (ExceptionType2 e2) {
    // Handle ExceptionType2
} finally {
    // Code executed always
}
```

---

## 5. Example of Exception Handling

### Handling Arithmetic Exception (divide by zero)

```java
public class ExceptionExample {
    public static void main(String[] args) {
        int a = 10, b = 0;
        try {
            int c = a / b; // This will cause ArithmeticException
            System.out.println("Result: " + c);
        } catch (ArithmeticException e) {
            System.out.println("Error: Cannot divide by zero");
        } finally {
            System.out.println("This block is always executed");
        }
    }
}
```

---

## 6. Throwing Exception Explicitly Using `throw`

```java
public class ThrowExample {
    static void checkAge(int age) {
        if (age < 18) {
            throw new ArithmeticException("Not eligible to vote");
        } else {
            System.out.println("Eligible to vote");
        }
    }

    public static void main(String[] args) {
        checkAge(16);  // Throws exception
    }
}
```

---

## 7. Declaring Exceptions with `throws`

```java
import java.io.*;

public class ThrowsExample {
    static void readFile() throws IOException {
        FileReader file = new FileReader("file.txt");
        BufferedReader fileInput = new BufferedReader(file);
      
        throw new IOException("File error");  // Manually throwing exception
    }

    public static void main(String[] args) {
        try {
            readFile();
        } catch (IOException e) {
            System.out.println("Exception caught: " + e.getMessage());
        }
    }
}
```

---

## 8. Common Exception Classes in Java

| Exception Name                     | Description                            |
| ---------------------------------- | -------------------------------------- |
| `ArithmeticException`            | Division by zero                       |
| `NullPointerException`           | Using an object reference that is null |
| `ArrayIndexOutOfBoundsException` | Accessing invalid array index          |
| `NumberFormatException`          | Converting string to number fails      |
| `IOException`                    | Input-output related exception         |
| `FileNotFoundException`          | When file not found                    |

---

## 9. Best Practices

* Use **specific exceptions** in catch blocks rather than generic `Exception`.
* Always use `finally` block to close resources like files, database connections.
* Avoid empty catch blocks.
* Use **custom exceptions** for application-specific errors.

---
