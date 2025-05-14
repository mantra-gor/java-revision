# 🧱 Keywords in Java

## 🔁 The `this` Keyword

### ▶ TL;DR:

`this` is a reference variable that refers to the **current object** of the class.

---

### ▶ When to Use:

- To **differentiate** between instance variables and method/constructor parameters.
- To call another **constructor** within the same class.
- To **pass the current object** as a parameter.
- For **method chaining**.

---

### ▶ Syntax & Use Cases:

#### ✅ 1. Disambiguating instance variables:

```java
class Student {
  String name;

  Student(String name) {
    this.name = name; // 'this' refers to instance variable
  }
}
```

#### ✅ 2. Calling another constructor (constructor chaining):

```java
class Box {
  int length, width;

  Box() {
    this(10, 20); // calls parameterized constructor
  }

  Box(int l, int w) {
    this.length = l;
    this.width = w;
  }
}
```

#### ✅ 3. Passing current object:

```java
class A {
  void show(A obj) {
    System.out.println("Object received");
  }

  void call() {
    show(this); // passing current object
  }
}
```

#### ✅ 4. Method chaining:

```java
class Builder {
  Builder setA() {
    // do something
    return this;
  }

  Builder setB() {
    // do something else
    return this;
  }
}
Builder obj = new Builder().setA().setB();
```

### 💡 Key Point:

- this is implicit in non-static context.
- Cannot be used in static methods (no object context).

#### ✅ Best Practice: Use this to improve code clarity and enable chaining/constructor logic.

## 🧭 The `super` Keyword

### ▶ TL;DR:

`super` is a reference variable used to refer to the **immediate parent class** in inheritance.

---

### ▶ When to Use:

- To access **parent class constructor**.
- To access **parent class methods** or **variables** that are overridden or hidden.
- Helps avoid ambiguity when subclass and superclass have the same members.

---

### ▶ Syntax & Use Cases:

#### ✅ 1. Calling parent class constructor:

```java
class Parent {
  Parent() {
    System.out.println("Parent Constructor");
  }
}

class Child extends Parent {
  Child() {
    super(); // calls Parent()
    System.out.println("Child Constructor");
  }
}
```

#### ✅ 2. Accessing parent class variable:

```java
class Parent {
  int x = 10;
}

class Child extends Parent {
  int x = 20;

  void print() {
    System.out.println(super.x); // prints 10
  }
}
```

#### ✅ 3. Accessing parent class method:

```java
class Animal {
  void sound() {
    System.out.println("Animal sound");
  }
}

class Dog extends Animal {
  void sound() {
    super.sound(); // calls Animal's sound()
    System.out.println("Dog barks");
  }
}
```

### 💡 Key Point:

- super() must be the first statement in the subclass constructor.
- Cannot be used in static contexts (no object reference).
- Often used in method overriding scenarios to call the original version.

#### ✅ Best Practice: Use super in inheritance scenarios to access parent class features safely and clearly.

---

## ⚔️ `this` vs `super` in Java

Understanding the difference between `this` and `super` is essential in object-oriented programming, especially when working with inheritance and constructors.

### 🔄 Comparison Table

| Feature/Use Case              | `this`                                      | `super`                                       |
|-------------------------------|---------------------------------------------|-----------------------------------------------|
| Refers To                     | Current class instance                      | Immediate parent class instance               |
| Used In                       | Non-static context of the current class     | Subclass to refer to superclass               |
| Constructor Call              | Calls another constructor in the same class | Calls parent class constructor                |
| Method Access                 | Calls current class method                  | Calls overridden method from parent class     |
| Variable Access               | Access current class variable               | Access parent class variable                  |
| Syntax                        | `this.variable`, `this()`, `this.method()`  | `super.variable`, `super()`, `super.method()` |
| Must Be First Statement?      | Yes, when calling another constructor       | Yes, when calling parent constructor          |
| Static Use                    | ❌ Not allowed in static context             | ❌ Not allowed in static context              |

---

### 💡 Summary

- Use **`this`** when you are working **within the current object**, especially for:
  - Disambiguating variable names
  - Method chaining
  - Constructor chaining

- Use **`super`** when you want to **access parent class features**, especially in:
  - Method overriding
  - Accessing hidden variables
  - Calling superclass constructors

✅ **Best Practice**: Use `this` for current context clarity, and `super` for working with inherited members.

## 🔒 The `final` Keyword in Java

### ▶ TL;DR:

The `final` keyword is used to declare **constants**, **prevent inheritance**, and **restrict method overriding or variable reassignment**.

---

### ▶ Where You Can Use `final`:

- On **variables**: to make them constants (immutable).
- On **methods**: to prevent overriding in subclasses.
- On **classes**: to prevent inheritance.

---

### ▶ Syntax & Use Cases:

#### ✅ 1. Final Variable (Constant):

```java
final int MAX_VALUE = 100;
MAX_VALUE = 200; // ❌ Error: cannot assign a value to final variable
```

#### ✅ 2. Final Method (No Overriding Allowed):

```java
class Animal {
  final void makeSound() {
    System.out.println("Animal sound");
  }
}

class Dog extends Animal {
  void makeSound() {         // ❌ Error: cannot override final method
    System.out.println("Bark");
  }
}
```

#### ✅ 3. Final Class (Cannot be Inherited):

```java
final class MathConstants {
  // some constants
}

// ❌ Error: cannot subclass final class
class AdvancedMath extends MathConstants {}
```

### 💡 Key Point:

- Final variables must be initialized only once.
- Final methods are locked from being overridden.
- Final classes cannot be extended, useful for security and performance.

#### ✅ Best Practice: Use final to protect values, methods, or classes from unwanted modification or extension.
