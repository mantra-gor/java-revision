# 🧱 Object-Oriented Programming in Java

## 📌 Class and Object

### ▶ TL;DR:

- A **class** is a blueprint.
- An **object** is an instance of a class.

### ▶ Syntax:

```java
class Car {
  String color;
  void drive() {
    System.out.println("Driving...");
  }
}

Car myCar = new Car();  // Object creation
myCar.color = "Red";
myCar.drive();
```

## 📌 Constructors

### ▶ TL;DR:

- A constructor initializes an object.

- It has the same name as the class and no return type.

- Called automatically when you create an object.

### ▶ Types:

- Default constructor (no params)

- Parameterized constructor

### ▶ Syntax:

```java
class Student {
  String name;

  // Constructor
  Student(String n) {
    name = n;
  }
}
Student s1 = new Student("Alice");
```

## 📦 Java Packages

A package is simply a container that groups related types (Java classes, interfaces, enumerations and annotations).

It helps in:

- **Avoiding name conflicts**
- **Making code modular**
- **Providing access protection**
- **Easier code maintenance**

---

### ▶️ Types of Packages

1. **Built-in Packages** – Provided by Java (e.g., `java.util`, `java.io`, `java.lang`)
2. **User-defined Packages** – Created by programmers to organize classes as per project needs.

---

### 🧪 Example: Creating a Package

```java
// File: MyClass.java
package mypackage;  // declaring the package

public class MyClass {
    public void display() {
        System.out.println("Hello from MyClass inside mypackage!");
    }
}
```

```java
// File: Main.java
import mypackage.MyClass;  // importing the user-defined package

public class Main {
    public static void main(String[] args) {
        MyClass obj = new MyClass();
        obj.display();
    }
}
```

## 🧱 Four Main Pillars of OOPS

- 🔍 **Abstraction**
- 🛡️ **Encapsulation**
- 🧬 **Inheritance**
- 🎭 **Polymorphism**

### 🔍 **Abstraction**

---

- Abstraction is a process of hiding implementation details and exposing only the functionality to the user. In abstraction, we deal with ideas and not events. This means the user will only know “what it does” rather than “how it does”.

#### 💡 Why Abstraction?

- Reduces complexity
- Increases code readability
- Enhances maintainability
- Improves security by hiding sensitive logic

---

#### ▶️ Real-world Example

> **TV Remote:**  
> You use the buttons to control a TV (what it does), but you don't need to know the internal circuitry (how it works).

---

### 🛠️ How to Achieve Abstraction in Java

Java provides two ways to achieve abstraction:

| Method             | Abstraction Level  |
|--------------------|--------------------|
| **Abstract Class** | Partial            |
| **Interface**      | Full               |

---

### 🔹 Using Abstract Class

```java
abstract class Animal {
    abstract void sound();  // abstract method

    void sleep() {
        System.out.println("Sleeping...");
    }
}

class Dog extends Animal {
    void sound() {
        System.out.println("Barks");
    }
}
```

### 🛡️ **Encapsulation**

---

- Encapsulation is the process of wrapping code and data together into a single unit.

  **Real-Life Example**: A capsule which is mixed of several medicines. The medicines are hidden data to the end user.

### 🧬 **Inheritance**

---

- Inheritance is the process of one class inheriting properties and methods from another class in Java. Inheritance is used when we have is-a relationship between objects.  Inheritance in Java is implemented using extends keyword.
  
#### Types of Inheritance in Java

- Single Inheritance
- Multilevel Inheritance
- Hierarchical Inheritance
- Multiple Inheritance
- Hybrid Inheritance

#### Key Concept:

- A subclass can access public and protected members of the superclass.
- Java supports single inheritance (a class can inherit from one class only).
- For multiple inheritance (by functionality), Java uses interfaces.
- Constructors are not inherited.
- Private members of the superclass are not accessible directly in the subclass.

### ▶️ Syntax:

```java
class Parent {
    void display() {
        System.out.println("This is the parent class");
    }
}

class Child extends Parent {
    void show() {
        System.out.println("This is the child class");
    }
}
```

### Example:

```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    void breed() {
        System.out.println("This is a Labrador");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.sound();  // Inherited method
        d.breed();  // Child class method
    }
}
```

### 🎭 **Polymorphism**

---

- Polymorphism is the ability to perform many things in many ways. The word Polymorphism is from two different Greek words- poly and morphs. “Poly” means many, and “Morphs” means forms. So polymorphism means many forms. The polymorphism can be present in the case of inheritance also. The functions behave differently based on the actual implementation.

  **Real-Life Example**: A delivery person delivers items to the user. If it’s a postman he will deliver the letters. If it’s a food delivery boy he will deliver the foods to the user. Like this polymorphism implemented different ways for the delivery function.

- There are two types of polymorphism as listed below:
  
  1. Static or Compile-time Polymorphism

  - Static or Compile-time Polymorphism when the compiler is able to determine the actual function, it’s called compile-time polymorphism. Compile-time polymorphism can be achieved by method overloading in java. When different functions in a class have the same name but different signatures, it’s called method overloading. A method signature contains the name and method arguments. So, overloaded methods have different arguments. The arguments might differ in the numbers or the type of arguments.
  
  Example of Static Polymorphism:

  ```java
    public class Car{
      public void speed() {
      }

      public void speed(String accelerator) {
      }

      public int speed(String accelerator, int speedUp) {
          return carSpeed;
      }
    }
  ```

  2. Dynamic or Run-time Polymorphism
  - Dynamic or Run-time Polymorphism Dynamic (or run-time) polymorphism occurs when the compiler is not able to determine at compile-time which method (superclass or subclass) will be called. This decision is made at run-time. Run-time polymorphism is achieved through method overriding, which happens when a method in a subclass has the same name, return type, and parameters as a method in its superclass. When the superclass method is overridden in the subclass, it is called method overriding.

  Example of Dynamic Polymorphism

  ```java
  import java.util.Random;

  class DeliveryBoy {
  
      public void deliver() {
          System.out.println("Delivering Item");
      }
  
      public static void main(String[] args) {
          DeliveryBoy deliveryBoy = getDeliveryBoy();
          deliveryBoy.deliver();
      }
  
      private static DeliveryBoy getDeliveryBoy() {
          Random random = new Random();
          int number = random.nextInt(5);
          return number % 2 == 0 ? new Postman() : new FoodDeliveryBoy();
      }
  }
  
  class Postman extends DeliveryBoy {
      @Override
      public void deliver() {
          System.out.println("Delivering Letters");
      }
  }
  
  class FoodDeliveryBoy extends DeliveryBoy {
      @Override
      public void deliver() {
          System.out.println("Delivering Food");
      }
  }
  ```

### 📘 Interface in Java

---

An **interface** in Java is a blueprint of a class. It is used to achieve **100% abstraction** (before Java 8) and to define a **contract** that implementing classes must follow.

---

#### 🔹 Key Points

- Interfaces contain **abstract methods** (by default, `public` and `abstract`).
- Variables declared in an interface are **implicitly**:
  - `public`
  - `static`
  - `final`
- From Java 8 onward, interfaces can also contain:
  - `default` methods (with body)
  - `static` methods
- From Java 9, they can also have `private` methods.
- A class **implements** an interface using the `implements` keyword.
- A class can **implement multiple interfaces**, enabling **multiple inheritance**.

---

#### 🧱 Syntax

```java
interface Animal {
    int legs = 4;  // implicitly public static final
    void sound();  // abstract method
}
```

#### 🚀 Default and Static Methods (Java 8+)

```java
interface Vehicle {
    void start();

    default void fuelType() {
        System.out.println("Petrol");
    }

    static void wheels() {
        System.out.println("Usually 4 wheels");
    }
}

class Car implements Vehicle {
    public void start() {
        System.out.println("Car starting...");
    }
}

// USAGE:
Car c = new Car();
c.fuelType();          // default method
Vehicle.wheels();      // static method
```

#### 🧩 Multiple Inheritance with Interfaces

```java
interface A {
    void methodA();
}

interface B {
    void methodB();
}

class C implements A, B {
    public void methodA() {
        System.out.println("From A");
    }

    public void methodB() {
        System.out.println("From B");
    }
}
```

✅ No ambiguity like in multiple class inheritance

| Feature              | Interface                         |
| -------------------- | ----------------------------------|
| Inheritance          | `implements` keyword              |
| Methods              | Abstract, default, static         |
| Fields               | `public static final` by default  |
| Multiple Inheritance | ✅ Supported                      |
| Constructors         | ❌ Not allowed                    |
