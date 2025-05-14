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

## 🧱 Four Main Pillars of OOPS

- 🔍 **Abstraction**
- 🛡️ **Encapsulation**
- 🧬 **Inheritance**
- 🎭 **Polymorphism**

### 🔍 **Abstraction**

---

- Abstraction is a process of hiding implementation details and exposing only the functionality to the user. In abstraction, we deal with ideas and not events. This means the user will only know “what it does” rather than “how it does”.

### 🛡️ **Encapsulation**

---

- Encapsulation is the process of wrapping code and data together into a single unit.

  **Real-Life Example**: A capsule which is mixed of several medicines. The medicines are hidden data to the end user.

### 🧬 **Inheritance**

---

- Inheritance is the process of one class inheriting properties and methods from another class in Java. Inheritance is used when we have is-a relationship between objects.  Inheritance in Java is implemented using extends keyword.

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
