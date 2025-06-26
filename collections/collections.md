# Collections Framework in JAVA

## 🎯 Wrapper Classes in Java

- Java is an **object-oriented language**, but primitive data types (`int`, `char`, `double`, etc.) are not objects.
- To use primitives where objects are required (like collections), Java provides **Wrapper Classes**.

| Primitive | Wrapper Class |
|-----------|----------------|
| `byte`    | `Byte`         |
| `short`   | `Short`        |
| `int`     | `Integer`      |
| `long`    | `Long`         |
| `float`   | `Float`        |
| `double`  | `Double`       |
| `char`    | `Character`    |
| `boolean` | `Boolean`      |

---

### 🔄 Autoboxing and Unboxing

---

#### ✅ Autoboxing

- Automatic conversion of a **primitive** to its **wrapper object**.

```java
int num = 10;
Integer boxedNum = num; // autoboxing
```

#### ✅ Unboxing

- Automatic conversion of a wrapper object to its primitive type.

```java
Integer boxedNum = 20;
int num = boxedNum; // unboxing

//🔥 Behind the scenes:
Integer boxedNum = Integer.valueOf(num); // autoboxing
int num = boxedNum.intValue(); // unboxing
```

## 📦 Generics in Java

- Generics allow us to create classes, interfaces, and methods that operate on types specified at runtime.
- Provide type safety and code reusability.

#### ✅ Without Generics

```java
ArrayList list = new ArrayList();
list.add("Hello");
String s = (String) list.get(0); // Type casting required
```

#### ✅ With Generics

```java
ArrayList<String> list = new ArrayList<>();
list.add("Hello");
String s = list.get(0); // No casting needed
```

## 🔐 Bounded Generics

- Restrict the type parameters to a certain type or its subclasses using extends keyword.

#### ✅ Syntax

```java
class Box<T extends Number> {
    private T value;

    public void set(T value) { this.value = value; }
    public T get() { return value; }
}
```

### ✅ Wildcards

| Wildcard        | Meaning                             |
| --------------- | ----------------------------------- |
| `<?>`           | Unknown type                        |
| `<? extends T>` | Any type that is a subtype of `T`   |
| `<? super T>`   | Any type that is a supertype of `T` |

#### Example

```java
public static void printNumbers(List<? extends Number> list) {
    for (Number num : list) {
        System.out.println(num);
    }
}
```

## Collections

### 📦 What is a Collection?

- A **Collection** is an object that **groups multiple elements** into a single unit.
- It is used to **store, retrieve, manipulate, and communicate** data efficiently.
- Java provides a **standard set of interfaces and classes** for collections in the `java.util` package.

### 🔧 What is the Collections Framework?

- The **Collections Framework** is a **unified architecture** for representing and manipulating collections.
- It includes:
  - **Interfaces** (like `List`, `Set`, `Queue`, `Map`)
  - **Implementations** (like `ArrayList`, `HashSet`, `LinkedList`, `HashMap`, etc.)
  - **Algorithms** (like `sort`, `shuffle`, `reverse` from `Collections` utility class)

### 🧩 Key Interfaces in Collections Framework

| Interface  | Description |
|------------|-------------|
| `Collection` | Root interface for most collection classes |
| `List`     | Ordered collection, allows duplicates |
| `Set`      | Unordered collection, does not allow duplicates |
| `Queue`    | Designed for holding elements prior to processing |
| `Deque`    | Double-ended queue |
| `Map`      | Key-value pairs, no duplicate keys |

### 🛠️ Common Implementations

| Interface | Implementations |
|-----------|-----------------|
| `List`    | `ArrayList`, `LinkedList`, `Vector`, `Stack` |
| `Set`     | `HashSet`, `LinkedHashSet`, `TreeSet` |
| `Queue`   | `PriorityQueue`, `ArrayDeque` |
| `Map`     | `HashMap`, `TreeMap`, `LinkedHashMap`, `Hashtable` |

### 📌 Collections vs Collection

| Term         | Meaning |
|--------------|--------|
| `Collection` | Root interface for all collection types |
| `Collections` | A utility class with static methods to operate on collections (like sort, reverse, etc.) |

### 🔄 Common Methods in Collections Utility Class

```java
Collections.sort(list);
Collections.reverse(list);
Collections.shuffle(list);
Collections.max(list);
Collections.min(list);
```

## ✅ Benefits of Java Collections Framework

- Reduces programming effort
- Increases performance
- Provides interoperability between unrelated APIs
- Promotes reusability and consistency

## Explore the core interfaces of the Java Collections Framework:

- [List Interface](./list.md)
- [Queue Interface](./queue.md)
- [Sets Interface](./sets.md)
