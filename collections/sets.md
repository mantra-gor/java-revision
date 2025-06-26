# 🧩 Java Set Interface

## 🔹 What is Set?

- `Set` is a **collection that does not allow duplicate elements**.
- It models the mathematical set abstraction.
- Part of the `java.util` package.
- Insertion order is **not guaranteed** (except in `LinkedHashSet`).

#### Syntax:

```java
Set<String> set = new HashSet<>();
```

## 🧰 Key Implementations of Set

### 1. ✅ HashSet

- Uses a HashTable for storage.
- No guaranteed order of elements.
- Allows null values.
- Best performance for basic operations (add, remove, contains).
  
```java
Set<String> set = new HashSet<>();
set.add("A");               // Adds "A"
set.add("B");
set.add("A");               // Duplicate, ignored
System.out.println(set);   // Output order is unpredictable
```

### 2. ✅ LinkedHashSet

- Inherits from HashSet.
- Maintains insertion order.
- Slightly slower than HashSet.

```java
Set<String> set = new LinkedHashSet<>();
set.add("Java");
set.add("Python");
set.add("C++");
System.out.println(set);   // Output: [Java, Python, C++]
```

### 3. ✅ TreeSet

- Implements NavigableSet, based on a Red-Black Tree.
- Sorted in natural order or by a custom comparator.
- Does not allow null values.

## 🔄 Set vs List

| Feature           | Set                      | List  |
| ----------------- | ------------------------ | ----- |
| Allows duplicates | ❌ No                     | ✅ Yes |
| Maintains order   | ❌ (Except LinkedHashSet) | ✅ Yes |
| Allows nulls      | ✅ (Except TreeSet)       | ✅ Yes |
| Access by index   | ❌ No                     | ✅ Yes |

## 🧪 Common Set Methods

```java
set.add("A");         // Adds "A" to the set
set.remove("A");      // Removes "A"
set.contains("A");    // Checks if "A" exists in the set
set.size();           // Returns number of elements
set.isEmpty();        // Checks if set is empty
set.clear();          // Removes all elements
```

> 🧠 Tip: Use HashSet for performance, LinkedHashSet when order matters, and TreeSet when sorting is needed.
