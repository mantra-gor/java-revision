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
