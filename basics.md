# Basics in JAVA

## Basics of Arrays

An array in Java is a data structure that stores a fixed-size, sequential collection of elements of the same data type.

### ✍️ How to initialize array

```java
int arr[] = new int[5];
```

### ✍️ Multi-dimensional array

```java
int twoDimArr = new int[4][5];
```

## Basics of Strings

### ✍️ String Initialization in Java

#### ▶ TL;DR:

Strings can be created using **string literals** or the **`new` keyword**. Literals are memory efficient; `new` creates a new object each time.

#### ▶ When to Use:

- Use **string literals** for most cases (faster, memory-friendly).
- Use **`new String()`** when you need a distinct object (rare in practice).

#### ▶ Syntax:

```java
// Using string literal
String str2 = "Mantra";

// Using new keyword
String str1 = new String("Mantra");
```

### ✍️ String Comparisation in Java

- == checks for reference equality, i.e., whether both variables point to the same memory location

```java
String x = "World";
String y = "World";
System.out.println(x == y); // true ✅ (same reference from string pool)

System.out.println(a.equals(b)); // true ✅ (compares content)
```
