# 📑 Java List Interface

## 🔹 What is List?

- `List` is a **subinterface of Collection** in Java.
- It is an **ordered collection** that **allows duplicate elements**.
- Elements can be accessed by their **index** (zero-based).
- Declared as: `List<E> list = new ArrayList<>();`

---

## 🧰 Key Implementations of List

### 1. ✅ ArrayList

- Backed by a **resizable array**.
- Provides **fast random access** (via index).
- **Insertion/removal** is slow (due to internal array resizing).
- Not synchronized.

```java
List<String> list = new ArrayList<>();
list.add("Java");
```

| Operation                       | Complexity     |
| ------------------------------- | -------------- |
| `get(index)`                    | O(1)           |
| `add/remove` at end             | O(1) amortized |
| `insert/remove` at middle/start | O(n)           |

### 2. ✅ LinkedList

- Based on a doubly linked list.
- Faster insertion and deletion in the middle or ends.
- Slower random access (must traverse nodes).
- Implements both List and Deque.

```java
List<String> list = new LinkedList<>();
list.add("Java");
```

| Operation                 | Complexity |
| ------------------------- | ---------- |
| `get(index)`              | O(n)       |
| `add/remove` at head/tail | O(1)       |
| `insert/remove` at middle | O(n)       |

### 3. ✅ Vector

- Similar to ArrayList, but synchronized (thread-safe).
- Slower in single-threaded programs due to overhead.

```java
List<String> list = new ArrayList<>();
list.add("Java");
```

### 4. ✅ Stack (extends Vector)

- Last-In-First-Out (LIFO) structure.
- Inherited from Vector.
- Methods: push(), pop(), peek(), empty().

```java
Stack<Integer> stack = new Stack<>();
stack.push(10);
stack.pop();
```

| Operation                       | Complexity     |
| ------------------------------- | -------------- |
| `get(index)`                    | O(1)           |
| `add/remove` at end             | O(1) amortized |
| `insert/remove` at middle/start | O(n)           |

## 📊 When to Use What?

| Use Case                        | Recommended  |
| ------------------------------- | ------------ |
| Fast access by index            | `ArrayList`  |
| Frequent insertions/removals    | `LinkedList` |
| Thread-safe list operations     | `Vector`     |
| LIFO structure (stack behavior) | `Stack`      |

## 🧪 Common List Methods

```java
list.add("A");          // Adds element "A" to the end of the list
list.get(0);            // Retrieves the element at index 0
list.set(1, "B");       // Updates the element at index 1 to "B"
list.remove(2);         // Removes the element at index 2
list.contains("X");     // Checks if "X" exists in the list (returns true/false)
list.indexOf("A");      // Returns the index of first occurrence of "A"
list.size();            // Returns the number of elements in the list
list.clear();           // Removes all elements from the list
```

> Tip: Always use List as the reference type and choose the implementation (ArrayList, LinkedList, etc.) based on your needs.
