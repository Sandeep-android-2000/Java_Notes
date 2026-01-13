
# Java Interview Notes – Object-Oriented Programming (OOPS)

---

## 1️⃣ What is OOPS?

**Object-Oriented Programming System (OOPS)** is a programming paradigm based on the concept of **objects**, which contain:
- Data (fields / variables)
- Behavior (methods / functions)

OOPS helps in writing **modular, reusable, maintainable, and scalable code**.

---

## 2️⃣ Core Principles of OOPS

Java follows **four main OOPS principles**:
1. Encapsulation
2. Inheritance
3. Polymorphism
4. Abstraction

---

## 3️⃣ Class and Object

### 🔹 Class
A **class** is a blueprint used to create objects.

```java
class Student {
    int id;
    String name;

    void study() {
        System.out.println("Student is studying");
    }
}
```

---

### 🔹 Object
An **object** is an instance of a class.

```java
Student s = new Student();
```

Object is stored in **heap memory**.

---

## 4️⃣ Encapsulation

### 🔹 Definition
Encapsulation is the process of **wrapping data and methods into a single unit** and **restricting direct access to data**.

Achieved using:
- private variables
- public getters and setters

---

### 🔹 Example
```java
class BankAccount {
    private double balance;

    public double getBalance() {
        return balance;
    }

    public void setBalance(double balance) {
        this.balance = balance;
    }
}
```

Benefits:
- Data security
- Controlled access
- Maintainability

---

## 5️⃣ Inheritance

### 🔹 Definition
Inheritance allows a class to **inherit properties and behavior** from another class.

Implemented using `extends` keyword.

---

### 🔹 Example
```java
class Animal {
    void eat() {
        System.out.println("Eating");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Barking");
    }
}
```

---

### 🔹 Types of Inheritance
- Single
- Multilevel
- Hierarchical

Multiple inheritance using classes is **not supported** in Java.
Supported using **interfaces**.

---

## 6️⃣ Polymorphism

### 🔹 Definition
Polymorphism means **one method with multiple behaviors**.

Types:
- Compile-time (Method Overloading)
- Runtime (Method Overriding)

---

### 🔹 Method Overloading
```java
class Calculator {
    int add(int a, int b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }
}
```

---

### 🔹 Method Overriding
```java
class Parent {
    void show() {
        System.out.println("Parent show");
    }
}

class Child extends Parent {
    void show() {
        System.out.println("Child show");
    }
}
```

---

## 7️⃣ Abstraction

### 🔹 Definition
Abstraction hides **implementation details** and shows **essential features** only.

Achieved using:
- Abstract classes
- Interfaces

---

### 🔹 Abstract Class
```java
abstract class Vehicle {
    abstract void start();
}
```

---

### 🔹 Interface
```java
interface Payment {
    void pay();
}
```

Interfaces support **multiple inheritance**.

---

## 8️⃣ Abstract Class vs Interface

| Feature | Abstract Class | Interface |
|------|--------------|----------|
| Methods | Abstract + Concrete | Abstract / Default |
| Variables | Instance | public static final |
| Multiple Inheritance | No | Yes |
| Constructor | Yes | No |

---

## 9️⃣ Important Keywords

- this → current object
- super → parent object
- final → restriction
- static → class-level

---

## 🔟 Interview One-Liners

- Encapsulation = data hiding
- Inheritance = IS-A relationship
- Polymorphism = one name, many forms
- Abstraction = implementation hiding
- Objects are stored in heap memory
- Java avoids multiple inheritance ambiguity

---

## 🧠 Quick Revision
Class → Blueprint  
Object → Instance  
Encapsulation → Security  
Inheritance → Reusability  
Polymorphism → Flexibility  
Abstraction → Simplicity
