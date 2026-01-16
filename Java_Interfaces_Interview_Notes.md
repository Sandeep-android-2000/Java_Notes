
# Java Interview Notes – Interfaces in Java (Updated)

---

## 1️⃣ Class vs Interface

### 🔹 Class
A **class** is a **blueprint for an object**.

- Used to create objects
- Can have instance variables and methods
- Supports single inheritance

---

### 🔹 Interface
An **interface** is a **blueprint for a class**.

It defines a **contract** that implementing classes must follow.

Interfaces are mainly used to:
- Achieve abstraction
- Achieve multiple inheritance

---

## 2️⃣ What Does an Interface Contain?

An interface can contain:
- Abstract methods
- Static constants
- Default methods
- Static methods

📌 All variables in an interface are **public static final by default**.

---

## 3️⃣ Abstract Methods in Interface

Abstract methods:
- Do not have a body
- Must be implemented by the implementing class

```java
interface Animal {
    void sound();   // public abstract by default
}
```

---

## 4️⃣ Static Methods in Interface

### 🔹 Important Rule
- Static methods **belong to the interface**
- They can be accessed **only using the interface name**
- They cannot be accessed via implementation classes
- They cannot be overridden

```java
interface Utility {
    static void greet() {
        System.out.println("Hello");
    }
}

Utility.greet();   // Valid
```

---

## 5️⃣ Default Methods in Interface

### 🔹 Why Default Methods?
Earlier, adding a new method to an interface would **break existing implementations**.

Default methods solve this problem.

---

### 🔹 Definition
A default method:
- Has a method body
- Is inherited by implementing classes
- Does not need to be implemented

```java
interface Vehicle {
    default void start() {
        System.out.println("Vehicle started");
    }
}
```

---

## 6️⃣ Multiple Inheritance Using Interfaces

Java does **not** support multiple inheritance using classes.  
Java **supports multiple inheritance using interfaces**.

```java
interface A {
    void show();
}

interface B {
    void display();
}

class C implements A, B {
    public void show() {}
    public void display() {}
}
```

---

## 7️⃣ Abstract Class vs Interface (Important Interview Point)

### 🔹 Abstract Class
- Can have **instance variables**
- Instance variables are initialized using **constructors**
- Can have constructors
- A class can **extend only one abstract class**

---

### 🔹 Interface
- Cannot have instance variables
- Does **not have constructors**
- Variables are static and final
- A class can **implement multiple interfaces**

---

## 8️⃣ Abstract Class vs Interface – Comparison Table

| Feature | Abstract Class | Interface |
|------|---------------|----------|
| Instance Variables | Yes | No |
| Constructor | Yes | No |
| Inheritance | Single | Multiple |
| Methods | Abstract + Concrete | Abstract, Default, Static |
| Object Creation | No | No |

---

## 🧠 Interview One-Liners

- Interface is a blueprint for a class
- Abstract class has instance variables and constructors
- Interface does not have constructors
- A class can extend only one abstract class
- A class can implement multiple interfaces
- Static interface methods belong only to interface
- Default methods avoid breaking code

---

## 🧠 Quick Revision

Class → Object blueprint  
Interface → Class blueprint  
Abstract class → State + behavior  
Interface → Behavior only  
Extend → One class  
Implement → Multiple interfaces
