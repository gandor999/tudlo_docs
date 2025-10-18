# SOLID Principles Summary

## 🧱 S – Single Responsibility Principle (SRP)
**Definition:**  
A class should have only one reason to change — it should do only one thing.

**Example:**
```java
// ❌ Bad: Handles both user data and saving to file
class User {
    void saveToFile() { /* save logic */ }
}

// ✅ Good: Separate responsibilities
class User {}
class UserRepository {
    void save(User user) { /* save logic */ }
}
```

---

## 🧩 O – Open/Closed Principle (OCP)
**Definition:**  
Classes should be **open for extension, but closed for modification.**

**Example:**
```java
// ❌ Bad: Must modify class to add new type
class AreaCalculator {
    double area(Object shape) {
        if (shape instanceof Circle) { ... }
        else if (shape instanceof Square) { ... }
    }
}

// ✅ Good: Use polymorphism
interface Shape { double area(); }
class Circle implements Shape { public double area() { ... } }
class Square implements Shape { public double area() { ... } }

class AreaCalculator {
    double area(Shape shape) { return shape.area(); }
}
```

---

## 🧠 L – Liskov Substitution Principle (LSP)
**Definition:**  
Subclasses should be usable anywhere their base class is used **without breaking behavior.**

**Example:**
```java
// ❌ Bad: Rectangle’s behavior changes when used as a Square
class Rectangle { void setWidth(int w); void setHeight(int h); }
class Square extends Rectangle {
    void setWidth(int w) { super.setWidth(w); super.setHeight(w); }
}

// ✅ Good: Don’t force subclass to change expected behavior
interface Shape { int area(); }
class Rectangle implements Shape { ... }
class Square implements Shape { ... }
```

---

## 🪜 I – Interface Segregation Principle (ISP)
**Definition:**  
Don’t force a class to implement methods it doesn’t need.  
Use **smaller, focused interfaces** instead of one large one.

**Example:**
```java
// ❌ Bad: Not all workers can eat
interface Worker { void work(); void eat(); }

// ✅ Good: Separate interfaces
interface Workable { void work(); }
interface Eatable { void eat(); }

class Robot implements Workable {
    public void work() { ... }
}
class Human implements Workable, Eatable {
    public void work() { ... }
    public void eat() { ... }
}
```

---

## ⚙️ D – Dependency Inversion Principle (DIP)
**Definition:**  
Depend on **abstractions**, not on **concrete implementations.**  
High-level modules shouldn’t depend on low-level modules directly.

**Example:**
```java
// ❌ Bad: Depends on a concrete class
class LightSwitch {
    private LightBulb bulb = new LightBulb();
    void toggle() { bulb.turnOn(); }
}

// ✅ Good: Depend on abstraction
interface Switchable { void turnOn(); }
class LightBulb implements Switchable { public void turnOn() { ... } }

class LightSwitch {
    private final Switchable device;
    LightSwitch(Switchable device) { this.device = device; }
    void toggle() { device.turnOn(); }
}
```

---

## ✅ In short
| Principle | Meaning |
|------------|----------|
| **S** | One responsibility per class |
| **O** | Extend without modifying existing code |
| **L** | Subclasses must behave like their parent class |
| **I** | Prefer many small interfaces |
| **D** | Depend on abstractions, not concrete classes |
