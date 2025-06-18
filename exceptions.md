# ⚠️ Exception Handling in JAVA

In Java, **exceptions** are unwanted or unexpected events that disrupt the normal flow of a program.

Java provides a robust **exception handling mechanism** to gracefully handle errors during runtime.

## 🔹 Types of Exceptions

### ✅ Checked Exceptions

- Checked at **compile-time**.
- Must be either caught or declared using `throws`.
- Example: `IOException`, `SQLException`

### ✅ Unchecked Exceptions

- Checked at **runtime**.
- Subclasses of `RuntimeException`.
- Example: `NullPointerException`, `ArrayIndexOutOfBoundsException`

### ✅ Errors

- Serious problems beyond the control of the program.
- Example: `OutOfMemoryError`, `StackOverflowError`

---

### 🔸 Exception Hierarchy

- Object
  - Throwable
    - Error
    - Exception
      - IOException
      - SQLException
      - RuntimeException
        - NullPointerException
        - ArithmeticException
        - ArrayIndexOutOfBoundsException

---

### 🔹 Exception Handling Keywords

| Keyword  | Description |
|----------|-------------|
| `try`    | Block of code to be tested for exceptions. |
| `catch`  | Block of code that handles the exception. |
| `finally`| Block of code that always executes (optional). |
| `throw`  | Used to explicitly throw an exception. |
| `throws` | Declares exceptions that might be thrown by a method. |

---

### 🔸 Syntax Example

```java
try {
    int result = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Cannot divide by zero.");
} finally {
    System.out.println("Finally block always executes.");
}
```

### 🔹 Throwing an Exception

```java
public void checkAge(int age) throws Exception {
    if(age < 18) {
        throw new Exception("Not eligible to vote");
    }
}
```

### 🔸 Multiple Catch Blocks

```java
try {
    // some code
} catch (IOException e) {
    // handle IOException
} catch (Exception e) {
    // handle generic Exception
}
```

### 🔹 Custom Exception

```java
class MyException extends Exception {
    public MyException(String message) {
        super(message);
    }
}
```
