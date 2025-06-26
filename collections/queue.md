# 📨 Java Queue Interface

## 🔹 What is Queue?

- A **Queue** is a **linear data structure** that follows the **FIFO (First-In-First-Out)** order.
- It is part of the **java.util** package and a subinterface of `Collection`.
- Elements are added from the **rear** and removed from the **front**.

#### Syntax:

```java
  Queue<String> queue = new LinkedList<>();
```

---

## 🧰 Key Implementations of Queue

### 1. ✅ LinkedList (as Queue)

- Implements both List and Queue.
- Can be used as a basic FIFO queue.
- Allows null elements.

```java
Queue<String> queue = new LinkedList<>();
queue.add("A");           // Adds element to the end
queue.remove();           // Removes element from the front
queue.peek();             // Retrieves head without removing it
```

### 2. ✅ PriorityQueue

- Elements are ordered based on natural ordering or a custom comparator.
- Does not allow null elements.
- Not thread-safe.

```java
Queue<Integer> pq = new PriorityQueue<>();
pq.add(30);               // Adds 30
pq.add(10);               // Adds 10
pq.add(20);               // Adds 20

System.out.println(pq);  // Output order depends on priority
```

### 3. ✅ ArrayDeque

- Resizable array implementation of a double-ended queue.
- Faster than LinkedList and Stack.
- Does not allow null elements.

```java
Queue<String> adq = new ArrayDeque<>();
adq.add("A");            // Adds element to the end
adq.offer("B");          // Adds element to the end (preferred)
adq.poll();              // Removes element from the front
adq.peek();              // Returns head without removing
```

## 🔄 Queue vs Deque

| Feature        | Queue                                 | Deque (Double-Ended Queue)                 |
| -------------- | ------------------------------------- | ------------------------------------------ |
| Access         | FIFO only                             | FIFO & LIFO                                |
| Methods        | add, remove                           | addFirst, addLast, removeFirst, removeLast |
| Implementation | LinkedList, PriorityQueue, ArrayDeque | ArrayDeque, LinkedList                     |

## 🧪 Common Queue Methods

```java
queue.add("A");        // Adds "A" to the queue, throws exception if full
queue.offer("B");      // Adds "B" to the queue, returns false if fails
queue.remove();        // Removes and returns head, throws exception if empty
queue.poll();          // Removes and returns head, returns null if empty
queue.element();       // Retrieves head, throws exception if empty
queue.peek();          // Retrieves head, returns null if empty
```

> 🧠 Tip: Prefer offer(), poll(), and peek() over add(), remove(), and element() to avoid exceptions in edge cases.
