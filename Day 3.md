### ✅ **Stack Implementation in Java**

```java
import java.util.Scanner;

class Stack {
    private int maxSize;
    private int[] stackArray;
    private int top;

    // Constructor
    public Stack(int size) {
        maxSize = size;
        stackArray = new int[maxSize];
        top = -1; // initially, stack is empty
    }

    // Push operation
    public void push(int value) {
        if (isFull()) {
            System.out.println("Stack Overflow! Cannot push " + value);
        } else {
            stackArray[++top] = value;
            System.out.println("Pushed: " + value);
        }
    }

    // Pop operation
    public int pop() {
        if (isEmpty()) {
            System.out.println("Stack Underflow! Cannot pop.");
            return -1;
        } else {
            return stackArray[top--];
        }
    }

    // Peek operation
    public int peek() {
        if (isEmpty()) {
            System.out.println("Stack is empty.");
            return -1;
        } else {
            return stackArray[top];
        }
    }

    // Check if stack is empty
    public boolean isEmpty() {
        return (top == -1);
    }

    // Check if stack is full
    public boolean isFull() {
        return (top == maxSize - 1);
    }

    // Display the stack
    public void display() {
        if (isEmpty()) {
            System.out.println("Stack is empty.");
        } else {
            System.out.print("Stack contents: ");
            for (int i = 0; i <= top; i++) {
                System.out.print(stackArray[i] + " ");
            }
            System.out.println();
        }
    }
}

// Main class to use the stack
public class StackDemo {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter stack size: ");
        int size = sc.nextInt();

        Stack myStack = new Stack(size);

        while (true) {
            System.out.println("\nChoose operation:");
            System.out.println("1. Push\n2. Pop\n3. Peek\n4. Display\n5. Exit");
            System.out.print("Enter choice: ");
            int choice = sc.nextInt();

            switch (choice) {
                case 1:
                    System.out.print("Enter value to push: ");
                    int val = sc.nextInt();
                    myStack.push(val);
                    break;
                case 2:
                    int popped = myStack.pop();
                    if (popped != -1)
                        System.out.println("Popped: " + popped);
                    break;
                case 3:
                    int top = myStack.peek();
                    if (top != -1)
                        System.out.println("Top Element: " + top);
                    break;
                case 4:
                    myStack.display();
                    break;
                case 5:
                    System.out.println("Exiting...");
                    System.exit(0);
                default:
                    System.out.println("Invalid choice.");
            }
        }
    }
}
```

---

### 💡 Output Example

```
Enter stack size: 3

Choose operation:
1. Push
2. Pop
3. Peek
4. Display
5. Exit
Enter choice: 1
Enter value to push: 10
Pushed: 10

Enter choice: 1
Enter value to push: 20
Pushed: 20

Enter choice: 4
Stack contents: 10 20

Enter choice: 3
Top Element: 20

Enter choice: 2
Popped: 20
```

---

### ✅ **Queue Implementation in Java (Using Array)**

```java
import java.util.Scanner;

class Queue {
    private int maxSize;
    private int[] queueArray;
    private int front;
    private int rear;

    // Constructor
    public Queue(int size) {
        maxSize = size;
        queueArray = new int[maxSize];
        front = 0;
        rear = -1;
    }

    // Enqueue (insert) operation
    public void enqueue(int value) {
        if (isFull()) {
            System.out.println("Queue Overflow! Cannot insert " + value);
        } else {
            queueArray[++rear] = value;
            System.out.println("Inserted: " + value);
        }
    }

    // Dequeue (remove) operation
    public int dequeue() {
        if (isEmpty()) {
            System.out.println("Queue Underflow! Cannot remove element.");
            return -1;
        } else {
            int removed = queueArray[front++];
            return removed;
        }
    }

    // Peek front element
    public int peek() {
        if (isEmpty()) {
            System.out.println("Queue is empty.");
            return -1;
        } else {
            return queueArray[front];
        }
    }

    // Check if queue is empty
    public boolean isEmpty() {
        return front > rear;
    }

    // Check if queue is full
    public boolean isFull() {
        return rear == maxSize - 1;
    }

    // Display the queue
    public void display() {
        if (isEmpty()) {
            System.out.println("Queue is empty.");
        } else {
            System.out.print("Queue elements: ");
            for (int i = front; i <= rear; i++) {
                System.out.print(queueArray[i] + " ");
            }
            System.out.println();
        }
    }
}

// Main class
public class QueueDemo {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter queue size: ");
        int size = sc.nextInt();

        Queue myQueue = new Queue(size);

        while (true) {
            System.out.println("\nChoose operation:");
            System.out.println("1. Enqueue\n2. Dequeue\n3. Peek\n4. Display\n5. Exit");
            System.out.print("Enter choice: ");
            int choice = sc.nextInt();

            switch (choice) {
                case 1:
                    System.out.print("Enter value to insert: ");
                    int val = sc.nextInt();
                    myQueue.enqueue(val);
                    break;
                case 2:
                    int removed = myQueue.dequeue();
                    if (removed != -1)
                        System.out.println("Removed: " + removed);
                    break;
                case 3:
                    int front = myQueue.peek();
                    if (front != -1)
                        System.out.println("Front Element: " + front);
                    break;
                case 4:
                    myQueue.display();
                    break;
                case 5:
                    System.out.println("Exiting...");
                    System.exit(0);
                default:
                    System.out.println("Invalid choice.");
            }
        }
    }
}
```

---

### 📝 Sample Output

```
Enter queue size: 3

Choose operation:
1. Enqueue
2. Dequeue
3. Peek
4. Display
5. Exit
Enter choice: 1
Enter value to insert: 10
Inserted: 10

Enter choice: 1
Enter value to insert: 20
Inserted: 20

Enter choice: 4
Queue elements: 10 20

Enter choice: 2
Removed: 10

Enter choice: 3
Front Element: 20
```

---

### ✅ Circular Queue

```java
import java.util.Scanner;

class CircularQueue {
    private int[] queue;
    private int front, rear, size, capacity;

    public CircularQueue(int capacity) {
        this.capacity = capacity;
        queue = new int[capacity];
        front = -1;
        rear = -1;
        size = 0;
    }

    public void enqueue(int value) {
        if (isFull()) {
            System.out.println("Queue is Full! Cannot insert " + value);
        } else if (isEmpty()) {
            front = rear = 0;
            queue[rear] = value;
            size++;
            System.out.println("Inserted: " + value);
        } else if (rear == capacity - 1 && front != 0) {
            rear = 0;
            queue[rear] = value;
            size++;
            System.out.println("Inserted: " + value);
        } else if (rear < capacity - 1) {
            rear = rear + 1;
            queue[rear] = value;
            size++;
            System.out.println("Inserted: " + value);
        } else {
            System.out.println("Cannot insert " + value + ", queue is in an invalid state.");
        }
    }

    public int dequeue() {
        if (isEmpty()) {
            System.out.println("Queue is Empty! Cannot remove.");
            return -1;
        } else if (front == rear) {
            int value = queue[front];
            front = rear = -1;
            size--;
            return value;
        } else if (front == capacity - 1) {
            int value = queue[front];
            front = 0;
            size--;
            return value;
        } else {
            int value = queue[front];
            front = front + 1;
            size--;
            return value;
        }
    }

    public int peek() {
        if (isEmpty()) {
            System.out.println("Queue is Empty!");
            return -1;
        } else {
            return queue[front];
        }
    }

    public boolean isFull() {
        return (size == capacity);
    }

    public boolean isEmpty() {
        return (size == 0);
    }

    public void display() {
        if (isEmpty()) {
            System.out.println("Queue is Empty.");
        } else {
            System.out.print("Queue elements: ");
            int i = front;
            int count = 0;

            while (count < size) {
                System.out.print(queue[i] + " ");
                if (i == capacity - 1) {
                    i = 0;
                } else {
                    i = i + 1;
                }
                count++;
            }
            System.out.println();
        }
    }
}
```

---

### 🧪 Main Class to Run

```java
public class CircularQueueMain {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter Circular Queue size: ");
        int size = sc.nextInt();

        CircularQueue cq = new CircularQueue(size);

        while (true) {
            System.out.println("\nChoose operation:");
            System.out.println("1. Enqueue\n2. Dequeue\n3. Peek\n4. Display\n5. Exit");
            System.out.print("Enter choice: ");
            int choice = sc.nextInt();

            switch (choice) {
                case 1:
                    System.out.print("Enter value to insert: ");
                    int val = sc.nextInt();
                    cq.enqueue(val);
                    break;
                case 2:
                    int removed = cq.dequeue();
                    if (removed != -1)
                        System.out.println("Removed: " + removed);
                    break;
                case 3:
                    int front = cq.peek();
                    if (front != -1)
                        System.out.println("Front Element: " + front);
                    break;
                case 4:
                    cq.display();
                    break;
                case 5:
                    System.out.println("Exiting...");
                    return;
                default:
                    System.out.println("Invalid choice.");
            }
        }
    }
}
```

---

### 🔁 **Deque Implementation in Java**

```java
import java.util.Scanner;

class Deque {
    private int[] deque;
    private int front, rear, size, capacity;

    public Deque(int capacity) {
        this.capacity = capacity;
        deque = new int[capacity];
        front = -1;
        rear = -1;
        size = 0;
    }

    // Insert at front
    public void insertFront(int value) {
        if (isFull()) {
            System.out.println("Deque is Full! Cannot insert at front.");
        } else if (isEmpty()) {
            front = rear = 0;
            deque[front] = value;
            size++;
            System.out.println("Inserted at front: " + value);
        } else if (front == 0) {
            front = capacity - 1;
            deque[front] = value;
            size++;
            System.out.println("Inserted at front: " + value);
        } else {
            front = front - 1;
            deque[front] = value;
            size++;
            System.out.println("Inserted at front: " + value);
        }
    }

    // Insert at rear
    public void insertRear(int value) {
        if (isFull()) {
            System.out.println("Deque is Full! Cannot insert at rear.");
        } else if (isEmpty()) {
            front = rear = 0;
            deque[rear] = value;
            size++;
            System.out.println("Inserted at rear: " + value);
        } else if (rear == capacity - 1) {
            rear = 0;
            deque[rear] = value;
            size++;
            System.out.println("Inserted at rear: " + value);
        } else {
            rear = rear + 1;
            deque[rear] = value;
            size++;
            System.out.println("Inserted at rear: " + value);
        }
    }

    // Delete from front
    public int deleteFront() {
        if (isEmpty()) {
            System.out.println("Deque is Empty! Cannot delete from front.");
            return -1;
        } else if (front == rear) {
            int value = deque[front];
            front = rear = -1;
            size--;
            return value;
        } else if (front == capacity - 1) {
            int value = deque[front];
            front = 0;
            size--;
            return value;
        } else {
            int value = deque[front];
            front = front + 1;
            size--;
            return value;
        }
    }

    // Delete from rear
    public int deleteRear() {
        if (isEmpty()) {
            System.out.println("Deque is Empty! Cannot delete from rear.");
            return -1;
        } else if (front == rear) {
            int value = deque[rear];
            front = rear = -1;
            size--;
            return value;
        } else if (rear == 0) {
            int value = deque[rear];
            rear = capacity - 1;
            size--;
            return value;
        } else {
            int value = deque[rear];
            rear = rear - 1;
            size--;
            return value;
        }
    }

    // Display all elements
    public void display() {
        if (isEmpty()) {
            System.out.println("Deque is Empty.");
        } else {
            System.out.print("Deque elements: ");
            int i = front;
            int count = 0;
            while (count < size) {
                System.out.print(deque[i] + " ");
                if (i == capacity - 1) {
                    i = 0;
                } else {
                    i++;
                }
                count++;
            }
            System.out.println();
        }
    }

    public boolean isFull() {
        return size == capacity;
    }

    public boolean isEmpty() {
        return size == 0;
    }
}
```

---

### 📌 **Main Class to Test Deque**

```java
public class DequeMain {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter size of Deque: ");
        int size = sc.nextInt();

        Deque dq = new Deque(size);

        while (true) {
            System.out.println("\nChoose operation:");
            System.out.println("1. Insert Front\n2. Insert Rear\n3. Delete Front\n4. Delete Rear\n5. Display\n6. Exit");
            System.out.print("Enter choice: ");
            int choice = sc.nextInt();

            switch (choice) {
                case 1:
                    System.out.print("Enter value to insert at front: ");
                    dq.insertFront(sc.nextInt());
                    break;
                case 2:
                    System.out.print("Enter value to insert at rear: ");
                    dq.insertRear(sc.nextInt());
                    break;
                case 3:
                    int dFront = dq.deleteFront();
                    if (dFront != -1) System.out.println("Deleted from front: " + dFront);
                    break;
                case 4:
                    int dRear = dq.deleteRear();
                    if (dRear != -1) System.out.println("Deleted from rear: " + dRear);
                    break;
                case 5:
                    dq.display();
                    break;
                case 6:
                    System.out.println("Exiting...");
                    return;
                default:
                    System.out.println("Invalid choice.");
            }
        }
    }
}
```

---

### 🧠 Output Example

```
Enter size of Deque: 4
1. Insert Rear → 10
2. Insert Rear → 20
3. Insert Front → 5
4. Display → 5 10 20
5. Delete Rear → 20
6. Delete Front → 5
7. Display → 10
```

---

### ✅ Singly Linked List with Position-Based Operations

```java
import java.util.Scanner;

// Node class
class Node {
    int data;
    Node next;

    Node(int value) {
        data = value;
        next = null;
    }
}

// Singly Linked List class
class SinglyLinkedList {
    private Node head;

    // Insert at beginning
    public void insertAtBeginning(int value) {
        Node newNode = new Node(value);

        if (head == null) {
            head = newNode;
        } else {
            newNode.next = head;
            head = newNode;
        }

        System.out.println("Inserted at beginning: " + value);
    }

    // Insert at end
    public void insertAtEnd(int value) {
        Node newNode = new Node(value);

        if (head == null) {
            head = newNode;
        } else {
            Node temp = head;
            while (temp.next != null) {
                temp = temp.next;
            }
            temp.next = newNode;
        }

        System.out.println("Inserted at end: " + value);
    }

    // Insert at specific position
    public void insertAtPosition(int value, int pos) {
        Node newNode = new Node(value);

        if (pos <= 0) {
            System.out.println("Invalid position.");
        } else if (pos == 1) {
            insertAtBeginning(value);
        } else {
            Node temp = head;
            int i = 1;
            while (temp != null && i < pos - 1) {
                temp = temp.next;
                i++;
            }

            if (temp == null) {
                System.out.println("Position out of range.");
            } else {
                newNode.next = temp.next;
                temp.next = newNode;
                System.out.println("Inserted " + value + " at position " + pos);
            }
        }
    }

    // Delete from beginning
    public void deleteFromBeginning() {
        if (head == null) {
            System.out.println("List is empty.");
        } else {
            System.out.println("Deleted from beginning: " + head.data);
            head = head.next;
        }
    }

    // Delete from end
    public void deleteFromEnd() {
        if (head == null) {
            System.out.println("List is empty.");
        } else if (head.next == null) {
            System.out.println("Deleted from end: " + head.data);
            head = null;
        } else {
            Node temp = head;
            while (temp.next.next != null) {
                temp = temp.next;
            }
            System.out.println("Deleted from end: " + temp.next.data);
            temp.next = null;
        }
    }

    // Delete from specific position
    public void deleteFromPosition(int pos) {
        if (head == null) {
            System.out.println("List is empty.");
        } else if (pos <= 0) {
            System.out.println("Invalid position.");
        } else if (pos == 1) {
            deleteFromBeginning();
        } else {
            Node temp = head;
            int i = 1;

            while (temp != null && i < pos - 1) {
                temp = temp.next;
                i++;
            }

            if (temp == null || temp.next == null) {
                System.out.println("Position out of range.");
            } else {
                System.out.println("Deleted from position " + pos + ": " + temp.next.data);
                temp.next = temp.next.next;
            }
        }
    }

    // Display the list
    public void display() {
        if (head == null) {
            System.out.println("List is empty.");
        } else {
            Node temp = head;
            System.out.print("Linked List: ");
            while (temp != null) {
                System.out.print(temp.data + " -> ");
                temp = temp.next;
            }
            System.out.println("null");
        }
    }
}
```

---

### 🧪 Main Class to Test

```java
public class SinglyLinkedListMain {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        SinglyLinkedList list = new SinglyLinkedList();

        while (true) {
            System.out.println("\nChoose operation:");
            System.out.println("1. Insert at Beginning");
            System.out.println("2. Insert at End");
            System.out.println("3. Insert at Position");
            System.out.println("4. Delete from Beginning");
            System.out.println("5. Delete from End");
            System.out.println("6. Delete from Position");
            System.out.println("7. Display");
            System.out.println("8. Exit");
            System.out.print("Enter choice: ");

            int choice = sc.nextInt();

            if (choice == 1) {
                System.out.print("Enter value: ");
                list.insertAtBeginning(sc.nextInt());
            } else if (choice == 2) {
                System.out.print("Enter value: ");
                list.insertAtEnd(sc.nextInt());
            } else if (choice == 3) {
                System.out.print("Enter value: ");
                int value = sc.nextInt();
                System.out.print("Enter position: ");
                int pos = sc.nextInt();
                list.insertAtPosition(value, pos);
            } else if (choice == 4) {
                list.deleteFromBeginning();
            } else if (choice == 5) {
                list.deleteFromEnd();
            } else if (choice == 6) {
                System.out.print("Enter position to delete: ");
                list.deleteFromPosition(sc.nextInt());
            } else if (choice == 7) {
                list.display();
            } else if (choice == 8) {
                System.out.println("Exiting...");
                break;
            } else {
                System.out.println("Invalid choice.");
            }
        }
    }
}
```

---

### 🧠 Sample Output

```
1. Insert at Beginning → 10
2. Insert at End → 30
3. Insert at Position (20 at 2) → 10 -> 20 -> 30
4. Delete from Position 2 → 10 -> 30
5. Display → 10 -> 30 -> null
```

---

# Circular Linked List Code (Java)

### ✅ Features:

* Insert at beginning
* Insert at end
* Insert at position
* Delete from beginning
* Delete from end
* Delete from position
* Display the circular list

All nodes are connected in a circle: the  **last node points back to the first** .

---

### 🔁 **Circular Linked List Code (Java)**

```java
import java.util.Scanner;

class Node {
    int data;
    Node next;

    Node(int value) {
        data = value;
        next = null;
    }
}

class CircularLinkedList {
    private Node head = null;
    private Node tail = null;

    // Insert at beginning
    public void insertAtBeginning(int value) {
        Node newNode = new Node(value);

        if (head == null) {
            head = tail = newNode;
            tail.next = head;
        } else {
            newNode.next = head;
            head = newNode;
            tail.next = head;
        }

        System.out.println("Inserted at beginning: " + value);
    }

    // Insert at end
    public void insertAtEnd(int value) {
        Node newNode = new Node(value);

        if (head == null) {
            head = tail = newNode;
            tail.next = head;
        } else {
            tail.next = newNode;
            tail = newNode;
            tail.next = head;
        }

        System.out.println("Inserted at end: " + value);
    }

    // Insert at position
    public void insertAtPosition(int value, int pos) {
        Node newNode = new Node(value);

        if (pos <= 0) {
            System.out.println("Invalid position.");
        } else if (pos == 1) {
            insertAtBeginning(value);
        } else {
            Node temp = head;
            int i = 1;

            while (i < pos - 1 && temp.next != head) {
                temp = temp.next;
                i++;
            }

            if (temp.next == head && i < pos - 1) {
                System.out.println("Position out of range.");
            } else {
                newNode.next = temp.next;
                temp.next = newNode;

                if (temp == tail) {
                    tail = newNode;
                }

                System.out.println("Inserted " + value + " at position " + pos);
            }
        }
    }

    // Delete from beginning
    public void deleteFromBeginning() {
        if (head == null) {
            System.out.println("List is empty.");
        } else if (head == tail) {
            System.out.println("Deleted from beginning: " + head.data);
            head = tail = null;
        } else {
            System.out.println("Deleted from beginning: " + head.data);
            head = head.next;
            tail.next = head;
        }
    }

    // Delete from end
    public void deleteFromEnd() {
        if (head == null) {
            System.out.println("List is empty.");
        } else if (head == tail) {
            System.out.println("Deleted from end: " + head.data);
            head = tail = null;
        } else {
            Node temp = head;
            while (temp.next != tail) {
                temp = temp.next;
            }
            System.out.println("Deleted from end: " + tail.data);
            tail = temp;
            tail.next = head;
        }
    }

    // Delete from position
    public void deleteFromPosition(int pos) {
        if (head == null) {
            System.out.println("List is empty.");
        } else if (pos <= 0) {
            System.out.println("Invalid position.");
        } else if (pos == 1) {
            deleteFromBeginning();
        } else {
            Node temp = head;
            int i = 1;

            while (i < pos - 1 && temp.next != head) {
                temp = temp.next;
                i++;
            }

            if (temp.next == head || temp.next == null) {
                System.out.println("Position out of range.");
            } else {
                Node toDelete = temp.next;
                System.out.println("Deleted from position " + pos + ": " + toDelete.data);
                temp.next = toDelete.next;

                if (toDelete == tail) {
                    tail = temp;
                }
            }
        }
    }

    // Display list
    public void display() {
        if (head == null) {
            System.out.println("List is empty.");
        } else {
            Node temp = head;
            System.out.print("Circular List: ");
            do {
                System.out.print(temp.data + " -> ");
                temp = temp.next;
            } while (temp != head);
            System.out.println("(back to head)");
        }
    }
}
```

---

### 💡 Main Class to Use the Circular List

```java
public class CircularLinkedListMain {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        CircularLinkedList list = new CircularLinkedList();

        while (true) {
            System.out.println("\n--- Circular Linked List Menu ---");
            System.out.println("1. Insert at Beginning");
            System.out.println("2. Insert at End");
            System.out.println("3. Insert at Position");
            System.out.println("4. Delete from Beginning");
            System.out.println("5. Delete from End");
            System.out.println("6. Delete from Position");
            System.out.println("7. Display");
            System.out.println("8. Exit");
            System.out.print("Enter choice: ");
            int choice = sc.nextInt();

            if (choice == 1) {
                System.out.print("Enter value: ");
                list.insertAtBeginning(sc.nextInt());
            } else if (choice == 2) {
                System.out.print("Enter value: ");
                list.insertAtEnd(sc.nextInt());
            } else if (choice == 3) {
                System.out.print("Enter value: ");
                int value = sc.nextInt();
                System.out.print("Enter position: ");
                int pos = sc.nextInt();
                list.insertAtPosition(value, pos);
            } else if (choice == 4) {
                list.deleteFromBeginning();
            } else if (choice == 5) {
                list.deleteFromEnd();
            } else if (choice == 6) {
                System.out.print("Enter position: ");
                list.deleteFromPosition(sc.nextInt());
            } else if (choice == 7) {
                list.display();
            } else if (choice == 8) {
                System.out.println("Exiting...");
                break;
            } else {
                System.out.println("Invalid choice.");
            }
        }
    }
}
```

---

### 🧠 Sample Output

```
1. Insert at Beginning → 10
2. Insert at End → 20
3. Insert at Position (15 at 2) → 10 -> 15 -> 20 -> (back to head)
4. Delete from Position 2 → 10 -> 20 -> (back to head)
```

# Doubly Circular Linked List (Java Code)

### ✅ Features Included:

* Insert at beginning
* Insert at end
* Insert at any position
* Delete from beginning
* Delete from end
* Delete from any position
* Display forward and reverse

---

### 🔄 **Doubly Circular Linked List (Java Code)**

```java
import java.util.Scanner;

class DCNode {
    int data;
    DCNode next;
    DCNode prev;

    DCNode(int value) {
        data = value;
        next = null;
        prev = null;
    }
}

class DoublyCircularLinkedList {
    private DCNode head = null;
    private DCNode tail = null;

    // Insert at beginning
    public void insertAtBeginning(int value) {
        DCNode newNode = new DCNode(value);

        if (head == null) {
            head = tail = newNode;
            head.next = head.prev = head;
        } else {
            newNode.next = head;
            newNode.prev = tail;
            head.prev = newNode;
            tail.next = newNode;
            head = newNode;
        }

        System.out.println("Inserted at beginning: " + value);
    }

    // Insert at end
    public void insertAtEnd(int value) {
        DCNode newNode = new DCNode(value);

        if (head == null) {
            head = tail = newNode;
            head.next = head.prev = head;
        } else {
            newNode.prev = tail;
            newNode.next = head;
            tail.next = newNode;
            head.prev = newNode;
            tail = newNode;
        }

        System.out.println("Inserted at end: " + value);
    }

    // Insert at any position
    public void insertAtPosition(int value, int pos) {
        DCNode newNode = new DCNode(value);

        if (pos <= 0) {
            System.out.println("Invalid position.");
        } else if (pos == 1) {
            insertAtBeginning(value);
        } else {
            DCNode temp = head;
            int i = 1;

            while (i < pos - 1 && temp.next != head) {
                temp = temp.next;
                i++;
            }

            if (i < pos - 1) {
                System.out.println("Position out of range.");
            } else {
                newNode.next = temp.next;
                newNode.prev = temp;
                temp.next.prev = newNode;
                temp.next = newNode;

                if (temp == tail) {
                    tail = newNode;
                }

                System.out.println("Inserted " + value + " at position " + pos);
            }
        }
    }

    // Delete from beginning
    public void deleteFromBeginning() {
        if (head == null) {
            System.out.println("List is empty.");
        } else if (head == tail) {
            System.out.println("Deleted from beginning: " + head.data);
            head = tail = null;
        } else {
            System.out.println("Deleted from beginning: " + head.data);
            head = head.next;
            head.prev = tail;
            tail.next = head;
        }
    }

    // Delete from end
    public void deleteFromEnd() {
        if (head == null) {
            System.out.println("List is empty.");
        } else if (head == tail) {
            System.out.println("Deleted from end: " + tail.data);
            head = tail = null;
        } else {
            System.out.println("Deleted from end: " + tail.data);
            tail = tail.prev;
            tail.next = head;
            head.prev = tail;
        }
    }

    // Delete from any position
    public void deleteFromPosition(int pos) {
        if (head == null) {
            System.out.println("List is empty.");
        } else if (pos <= 0) {
            System.out.println("Invalid position.");
        } else if (pos == 1) {
            deleteFromBeginning();
        } else {
            DCNode temp = head;
            int i = 1;

            while (i < pos && temp.next != head) {
                temp = temp.next;
                i++;
            }

            if (i < pos) {
                System.out.println("Position out of range.");
            } else {
                System.out.println("Deleted from position " + pos + ": " + temp.data);
                temp.prev.next = temp.next;
                temp.next.prev = temp.prev;

                if (temp == tail) {
                    tail = temp.prev;
                }
            }
        }
    }

    // Display forward
    public void displayForward() {
        if (head == null) {
            System.out.println("List is empty.");
        } else {
            DCNode temp = head;
            System.out.print("Forward: ");
            do {
                System.out.print(temp.data + " <-> ");
                temp = temp.next;
            } while (temp != head);
            System.out.println("(head)");
        }
    }

    // Display reverse
    public void displayReverse() {
        if (tail == null) {
            System.out.println("List is empty.");
        } else {
            DCNode temp = tail;
            System.out.print("Reverse: ");
            do {
                System.out.print(temp.data + " <-> ");
                temp = temp.prev;
            } while (temp != tail);
            System.out.println("(tail)");
        }
    }
}
```

---

### 🧪 Main Class to Test the Doubly Circular Linked List

```java
public class DoublyCircularLinkedListMain {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        DoublyCircularLinkedList list = new DoublyCircularLinkedList();

        while (true) {
            System.out.println("\n--- Doubly Circular Linked List Menu ---");
            System.out.println("1. Insert at Beginning");
            System.out.println("2. Insert at End");
            System.out.println("3. Insert at Position");
            System.out.println("4. Delete from Beginning");
            System.out.println("5. Delete from End");
            System.out.println("6. Delete from Position");
            System.out.println("7. Display Forward");
            System.out.println("8. Display Reverse");
            System.out.println("9. Exit");
            System.out.print("Enter your choice: ");
            int choice = sc.nextInt();

            if (choice == 1) {
                System.out.print("Enter value: ");
                list.insertAtBeginning(sc.nextInt());
            } else if (choice == 2) {
                System.out.print("Enter value: ");
                list.insertAtEnd(sc.nextInt());
            } else if (choice == 3) {
                System.out.print("Enter value: ");
                int val = sc.nextInt();
                System.out.print("Enter position: ");
                int pos = sc.nextInt();
                list.insertAtPosition(val, pos);
            } else if (choice == 4) {
                list.deleteFromBeginning();
            } else if (choice == 5) {
                list.deleteFromEnd();
            } else if (choice == 6) {
                System.out.print("Enter position to delete: ");
                list.deleteFromPosition(sc.nextInt());
            } else if (choice == 7) {
                list.displayForward();
            } else if (choice == 8) {
                list.displayReverse();
            } else if (choice == 9) {
                System.out.println("Exiting...");
                break;
            } else {
                System.out.println("Invalid choice.");
            }
        }
    }
}
```

---

### 🧠 Sample Output

```
1. Insert at Beginning → 10
2. Insert at End → 30
3. Insert at Position (20 at 2) → 10 <-> 20 <-> 30
4. Delete from Position 2 → 10 <-> 30
5. Display Reverse → 30 <-> 10 <-> (tail)
```

---

### 🌳 **Binary Search Tree in Java (Recursive)**

```java
class TreeNode {
    int data;
    TreeNode left, right;

    TreeNode(int value) {
        data = value;
        left = right = null;
    }
}

public class BSTree {
    TreeNode root;

    // Insert node using recursion
    public TreeNode insert(TreeNode node, int value) {
        if (node == null) {
            return new TreeNode(value);
        }

        if (value < node.data) {
            node.left = insert(node.left, value);
        } else if (value > node.data) {
            node.right = insert(node.right, value);
        }

        return node;
    }

    // In-order Traversal (Left, Root, Right)
    public void inOrder(TreeNode node) {
        if (node != null) {
            inOrder(node.left);
            System.out.print(node.data + " ");
            inOrder(node.right);
        }
    }

    // Pre-order Traversal (Root, Left, Right)
    public void preOrder(TreeNode node) {
        if (node != null) {
            System.out.print(node.data + " ");
            preOrder(node.left);
            preOrder(node.right);
        }
    }

    // Post-order Traversal (Left, Right, Root)
    public void postOrder(TreeNode node) {
        if (node != null) {
            postOrder(node.left);
            postOrder(node.right);
            System.out.print(node.data + " ");
        }
    }

    public static void main(String[] args) {
        BSTree tree = new BSTree();

        // Insert nodes into BST
        int[] values = {50, 30, 70, 20, 40, 60, 80};
        for (int v : values) {
            tree.root = tree.insert(tree.root, v);
        }

        // Traversals
        System.out.print("In-order: ");
        tree.inOrder(tree.root);
        System.out.println();

        System.out.print("Pre-order: ");
        tree.preOrder(tree.root);
        System.out.println();

        System.out.print("Post-order: ");
        tree.postOrder(tree.root);
        System.out.println();
    }
}
```

---

### 🧾 Output:

```
In-order: 20 30 40 50 60 70 80
Pre-order: 50 30 20 40 70 60 80
Post-order: 20 40 30 60 80 70 50
```

---

## 🔍 1. **Linear Search**

### ✅ Concept:

* Traverse the array from start to end
* Compare each element with the target
* Time Complexity: O(n)

### 💻 Code:

```java
public class LinearSearch {
    public static int search(int[] arr, int key) {
        for (int i = 0; i < arr.length; i++) {
            if (arr[i] == key) {
                return i; // Found at index i
            }
        }
        return -1; // Not found
    }

    public static void main(String[] args) {
        int[] arr = {10, 23, 45, 70, 11};
        int key = 45;

        int result = search(arr, key);
        if (result != -1)
            System.out.println("Element found at index: " + result);
        else
            System.out.println("Element not found.");
    }
}
```

---

## 🔍 2. **Binary Search**

### ✅ Concept:

* Array must be **sorted**
* Repeatedly divide the array in half
* Time Complexity: O(log n)

### 💻 Code:

```java
public class BinarySearch {
    public static int search(int[] arr, int key) {
        int low = 0;
        int high = arr.length - 1;

        while (low <= high) {
            int mid = (low + high) / 2;

            if (arr[mid] == key)
                return mid;
            else if (key < arr[mid])
                high = mid - 1;
            else
                low = mid + 1;
        }

        return -1; // Not found
    }

    public static void main(String[] args) {
        int[] arr = {10, 20, 30, 40, 50, 60};
        int key = 50;

        int result = search(arr, key);
        if (result != -1)
            System.out.println("Element found at index: " + result);
        else
            System.out.println("Element not found.");
    }
}
```

---

# **Sorting Algorithms**

## 🔢 **1. Bubble Sort**

### 📌 Algorithm:

* Repeatedly compare and swap adjacent elements if they're in the wrong order.

### 💻 Java Code:

```java
public class BubbleSort {
    public static void bubbleSort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            for (int j = 0; j < n - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    // Swap
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }
    }
}
```

### 📈 Time Complexity:

* Worst: O(n²), Best: O(n) (if already sorted)

---

## 🔢 **2. Selection Sort**

### 📌 Algorithm:

* Find the smallest element in the unsorted part and put it at the beginning.

### 💻 Java Code:

```java
public class SelectionSort {
    public static void selectionSort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            int minIndex = i;

            for (int j = i + 1; j < n; j++) {
                if (arr[j] < arr[minIndex])
                    minIndex = j;
            }

            // Swap
            int temp = arr[i];
            arr[i] = arr[minIndex];
            arr[minIndex] = temp;
        }
    }
}
```

### 📈 Time Complexity:

* O(n²) for all cases

---

## 🔢 **3. Insertion Sort**

### 📌 Algorithm:

* Take one element at a time and insert it in the correct position in the sorted part.

### 💻 Java Code:

```java
public class InsertionSort {
    public static void insertionSort(int[] arr) {
        int n = arr.length;

        for (int i = 1; i < n; i++) {
            int key = arr[i];
            int j = i - 1;

            while (j >= 0 && arr[j] > key) {
                arr[j + 1] = arr[j];
                j--;
            }

            arr[j + 1] = key;
        }
    }
}
```

### 📈 Time Complexity:

* Best: O(n), Worst: O(n²)

---

## 🔢 **4. Merge Sort (Divide and Conquer)**

### 📌 Algorithm:

* Divide the array into two halves, sort them recursively, then merge.

### 💻 Java Code:

```java
public class MergeSort {
    public static void mergeSort(int[] arr, int l, int r) {
        if (l < r) {
            int m = (l + r) / 2;

            mergeSort(arr, l, m);
            mergeSort(arr, m + 1, r);
            merge(arr, l, m, r);
        }
    }

    public static void merge(int[] arr, int l, int m, int r) {
        int n1 = m - l + 1;
        int n2 = r - m;

        int[] L = new int[n1];
        int[] R = new int[n2];

        for (int i = 0; i < n1; i++)
            L[i] = arr[l + i];

        for (int j = 0; j < n2; j++)
            R[j] = arr[m + 1 + j];

        int i = 0, j = 0, k = l;

        while (i < n1 && j < n2) {
            if (L[i] <= R[j])
                arr[k++] = L[i++];
            else
                arr[k++] = R[j++];
        }

        while (i < n1)
            arr[k++] = L[i++];

        while (j < n2)
            arr[k++] = R[j++];
    }
}
```

### 📈 Time Complexity:

* O(n log n) in all cases

---

## 🔢 **5. Quick Sort**

### 📌 Algorithm:

* Pick a pivot, place it at the correct position, and sort both sides recursively.

### 💻 Java Code:

```java
public class QuickSort {
    public static void quickSort(int[] arr, int low, int high) {
        if (low < high) {
            int pi = partition(arr, low, high);

            quickSort(arr, low, pi - 1);
            quickSort(arr, pi + 1, high);
        }
    }

    public static int partition(int[] arr, int low, int high) {
        int pivot = arr[high];
        int i = low - 1;

        for (int j = low; j < high; j++) {
            if (arr[j] < pivot) {
                i++;

                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }

        // Swap pivot
        int temp = arr[i + 1];
        arr[i + 1] = arr[high];
        arr[high] = temp;

        return i + 1;
    }
}
```

### 📈 Time Complexity:

* Best: O(n log n), Worst: O(n²), Average: O(n log n)

---

## 📊 Comparison Table

| Algorithm      | Best Time  | Worst Time | Stable | In-place |
| -------------- | ---------- | ---------- | ------ | -------- |
| Bubble Sort    | O(n)       | O(n²)     | Yes    | Yes      |
| Selection Sort | O(n²)     | O(n²)     | No     | Yes      |
| Insertion Sort | O(n)       | O(n²)     | Yes    | Yes      |
| Merge Sort     | O(n log n) | O(n log n) | Yes    | No       |
| Quick Sort     | O(n log n) | O(n²)     | No     | Yes      |

---

### ✅ **Quick Sort to Sort an Array (No Recursion, Using Array as Stack)**

```java
public class QuickSortSimple {

    static int partition(int[] arr, int low, int high) {
        int pivot = arr[high];
        int i = low - 1;

        for (int j = low; j < high; j++) {
            if (arr[j] < pivot) {
                i++;
                int temp = arr[i]; arr[i] = arr[j]; arr[j] = temp;
            }
        }

        int temp = arr[i + 1]; arr[i + 1] = arr[high]; arr[high] = temp;
        return i + 1;
    }

    static void quickSort(int[] arr) {
        int n = arr.length;
        int[] stack = new int[n];

        int top = -1;
        stack[++top] = 0;
        stack[++top] = n - 1;

        while (top >= 0) {
            int high = stack[top--];
            int low = stack[top--];

            int p = partition(arr, low, high);

            if (p - 1 > low) {
                stack[++top] = low;
                stack[++top] = p - 1;
            }

            if (p + 1 < high) {
                stack[++top] = p + 1;
                stack[++top] = high;
            }
        }
    }

    public static void main(String[] args) {
        int[] arr = { 10, 7, 8, 9, 1, 5 };
        quickSort(arr);

        // Print the sorted array
        for (int num : arr) {
            System.out.print(num + " ");
        }
    }
}
```

---

### 🔍 Output:

```
1 5 7 8 9 10
```


### 🔄 **Doubly Simply Linked List (Java Code)**

```java
// Online Java Compiler
// Use this editor to write, compile and run your Java code online

import java.util.Scanner;
class Node{
    int data;
    Node prev;
    Node next;
    Node (int n){
        data=n;
        prev=null;
        next = null;
    }
}
  
class linkedlist {
    Node head;
    void insertAtEnd(int v){
        Node newnode = new Node(v);
        if(head==null){
            head = newnode;
        }
        else{
            Node temp =head;
            while(temp.next!=null){
                temp = temp.next;
            }
            temp.next = newnode;
            newnode.prev = temp;
        
        }
        System.out.print(v+"inserted.");
    }
  
    void insertAtBegin(int v){
        Node newnode = new Node(v);
        if(head==null){
            head = newnode;
        }
        else{
            newnode.next=head;
            head.prev=newnode;
            head=newnode;
        
        }
        System.out.print(v+"inserted.");
    }
    void insertAtPos(int v, int pos){
        if(pos<=0){
            System.out.print("Invalid pos");
        }
        else if(pos==1){
            insertAtBegin(v);
        }
        else{
            Node temp = head;
            int i = 1;
            while(i<pos-1 && temp.next!=null ){
                temp=temp.next;
                i++;
            }
        
            if(temp.next == null && i<pos-1){
                System.out.print("Out of range.");
            }
            else{
               Node newnode = new Node(v);
               newnode.next = temp.next;
               newnode.prev = temp;
               temp.next = newnode;
               newnode.next.prev= newnode;
            }
            System.out.print(v+"inserted.");
        }
    }
  
    void deleteAtEnd(){
        if (head==null){
            System.out.print("List is empty");
        }else if (head.next==null){
            System.out.print("Head is deleted" + head.data);
            head=null;
        }else {
            Node temp = head;
            while(temp.next.next!=null){
                temp = temp.next;
            }
            System.out.print("deleted ->"+temp.next.data);
            temp.next=null;
        
        }
    
    }
    void deleteAtBegin(){
         if(head==null){
            System.out.print("List is empty");
        }
        else{
           head = head.next;
            head.prev = null;
            System.out.print("node is deleted");
        }
    }
    void deleteAtPos(int pos){
        if(pos<=0){
            System.out.println("Invalid Position");
        }
        else if(pos==1){
            deleteAtBegin();
        }
        else{
            Node temp=head;
            int i=1;
            while(i<pos && temp.next!=null){
                temp = temp.next;
                i++;
            }
            if(temp.next==null && i<pos){
                System.out.println("Out of range");
            }
            else{
                System.out.println(temp.data + "deleted");
                temp.prev.next=temp.next;
                temp.next.prev=temp.prev;
            
            }
        }
    
    }
     public void displayForward() {
        if (head == null) {
            System.out.println("List is empty.");
        } else {
            Node temp = head;
            System.out.print("Forward: ");
            do {
                System.out.print(temp.data + " <-> ");
                temp = temp.next;
            } while (temp != null);
            System.out.println("(Null)");
        }
    }
  
  
}
class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        linkedlist list = new linkedlist();

        while (true) {
            System.out.println("\n--- Doubly Simply Linked List Menu ---");
            System.out.println("1. Insert at Beginning");
            System.out.println("2. Insert at End");
            System.out.println("3. Insert at Position");
            System.out.println("4. Delete from Beginning");
            System.out.println("5. Delete from End");
            System.out.println("6. Delete from Position");
            System.out.println("7. Display Forward");
            System.out.println("8. Display Reverse");
            System.out.println("9. Exit");
            System.out.print("Enter your choice: ");
            int choice = sc.nextInt();

            if (choice == 1) {
                System.out.print("Enter value: ");
                list.insertAtBegin(sc.nextInt());
            } else if (choice == 2) {
                System.out.print("Enter value: ");
                list.insertAtEnd(sc.nextInt());
            } else if (choice == 3) {
                System.out.print("Enter value: ");
                int val = sc.nextInt();
                System.out.print("Enter position: ");
                int pos = sc.nextInt();
                list.insertAtPos(val, pos);
            } else if (choice == 4) {
                list.deleteAtBegin();
            } else if (choice == 5) {
                list.deleteAtEnd();
            } else if (choice == 6) {
                System.out.print("Enter position to delete: ");
                list.deleteAtPos(sc.nextInt());
            } else if (choice == 7) {
                list.displayForward();
            } else {
                System.out.println("Invalid choice.");
            }
        }
    }
}
```

---

### 🧪 Main Class to Test the Doubly Circular Linked List

```java
public class DoublyCircularLinkedListMain {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        DoublyCircularLinkedList list = new DoublyCircularLinkedList();

        while (true) {
            System.out.println("\n--- Doubly Circular Linked List Menu ---");
            System.out.println("1. Insert at Beginning");
            System.out.println("2. Insert at End");
            System.out.println("3. Insert at Position");
            System.out.println("4. Delete from Beginning");
            System.out.println("5. Delete from End");
            System.out.println("6. Delete from Position");
            System.out.println("7. Display Forward");
            System.out.println("8. Display Reverse");
            System.out.println("9. Exit");
            System.out.print("Enter your choice: ");
            int choice = sc.nextInt();

            if (choice == 1) {
                System.out.print("Enter value: ");
                list.insertAtBeginning(sc.nextInt());
            } else if (choice == 2) {
                System.out.print("Enter value: ");
                list.insertAtEnd(sc.nextInt());
            } else if (choice == 3) {
                System.out.print("Enter value: ");
                int val = sc.nextInt();
                System.out.print("Enter position: ");
                int pos = sc.nextInt();
                list.insertAtPosition(val, pos);
            } else if (choice == 4) {
                list.deleteFromBeginning();
            } else if (choice == 5) {
                list.deleteFromEnd();
            } else if (choice == 6) {
                System.out.print("Enter position to delete: ");
                list.deleteFromPosition(sc.nextInt());
            } else if (choice == 7) {
                list.displayForward();
            } else if (choice == 8) {
                list.displayReverse();
            } else if (choice == 9) {
                System.out.println("Exiting...");
                break;
            } else {
                System.out.println("Invalid choice.");
            }
        }
    }
}
```

---
