# Object-Oriented Programming (OOP) – The Four Pillars

Object-Oriented Programming (OOP) is a programming paradigm based on the concept of **objects** — entities that combine **data** (fields) and **behavior** (methods).  
The **four main pillars** of OOP are **Encapsulation, Abstraction, Inheritance,** and **Polymorphism.**

---

## 🧱 1. Encapsulation
**Definition:**  
Encapsulation means **bundling data and methods** that operate on that data into a single unit (a class), while restricting direct access to internal details.

**Goal:** Protect object integrity by controlling how data is accessed and modified.

**Example:**
```java
public class BankAccount {
    private double balance; // hidden data

    public void deposit(double amount) {
        if (amount > 0) balance += amount;
    }

    public double getBalance() {
        return balance;
    }
}
```
✅ Only the methods control how `balance` is changed.

---

## 🎭 2. Abstraction
**Definition:**  
Abstraction means **showing only essential details** while hiding unnecessary complexity.  
It focuses on **what an object does**, not **how it does it.**

**Example:**
```java
abstract class Vehicle {
    abstract void move();
}

class Car extends Vehicle {
    void move() {
        System.out.println("Car is driving");
    }
}

class Airplane extends Vehicle {
    void move() {
        System.out.println("Airplane is flying");
    }
}
```
✅ Users only need to call `move()` — they don’t care how each vehicle moves.

---

## 🧬 3. Inheritance
**Definition:**  
Inheritance allows a new class (child/subclass) to **reuse** fields and methods from another class (parent/superclass).  
It helps in **code reusability and hierarchy** creation.

**Example:**
```java
class Animal {
    void eat() {
        System.out.println("This animal eats food.");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("The dog barks.");
    }
}
```
✅ `Dog` automatically gets the `eat()` behavior from `Animal`.

---

## 🌀 4. Polymorphism
**Definition:**  
Polymorphism means **many forms** — the same method name can behave differently based on the object calling it.

**Types:**
- **Compile-time (method overloading)**  
- **Runtime (method overriding)**

**Example:**
```java
class Animal {
    void makeSound() {
        System.out.println("Some generic animal sound");
    }
}

class Dog extends Animal {
    void makeSound() {
        System.out.println("Bark");
    }
}

class Cat extends Animal {
    void makeSound() {
        System.out.println("Meow");
    }
}

public class TestPolymorphism {
    public static void main(String[] args) {
        Animal a1 = new Dog();
        Animal a2 = new Cat();

        a1.makeSound(); // Bark
        a2.makeSound(); // Meow
    }
}
```
✅ The same `makeSound()` call behaves differently depending on the actual object type.

---

## ✅ Summary Table

| Pillar | Description | Key Benefit |
|---------|--------------|--------------|
| **Encapsulation** | Hide data and expose behavior via methods | Protects data integrity |
| **Abstraction** | Expose essential features only | Simplifies complexity |
| **Inheritance** | Reuse code from parent classes | Promotes code reusability |
| **Polymorphism** | Same interface, different behavior | Increases flexibility |

---

### 💡 In short:
- **Encapsulation** = Hide the data.  
- **Abstraction** = Hide the complexity.  
- **Inheritance** = Reuse the code.  
- **Polymorphism** = Redefine the behavior.
