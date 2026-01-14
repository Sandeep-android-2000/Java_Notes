
# Java Interview Notes – Polymorphism

---

## 1️⃣ What is Polymorphism?

Polymorphism is a **core concept of Object-Oriented Programming (OOP)** that allows methods to **do different things based on the object it is acting upon**, even though:
- The method name is the same
- The method signature is the same

Meaning:
> **One method name, multiple behaviors**

---

## 2️⃣ Types of Polymorphism in Java

Java supports two types of polymorphism:

1. Compile-Time Polymorphism  
2. Runtime Polymorphism  

---

## 3️⃣ Compile-Time Polymorphism (Method Overloading)

### 🔹 Definition
Compile-time polymorphism is achieved using **method overloading**.

Method overloading means:
- Same method name
- Same return type
- Different number or type of arguments
- Decision is made at compile time

---

### 🔹 Example
```java
class Calculator {

    int add(int a, int b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }

    double add(double a, double b) {
        return a + b;
    }
}
```

📌 Return type alone cannot be used to overload methods.

---

## 4️⃣ Runtime Polymorphism (Dynamic Method Dispatch)

### 🔹 Definition
Runtime polymorphism occurs when a **parent class reference** refers to a **child class object**.

This is also called **Dynamic Method Dispatch** because:
- Method call is resolved at runtime
- JVM decides which method to execute

---

### 🔹 Example
```java
class Animal {
    void sound() {
        System.out.println("Animal makes sound");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Dog barks");
    }
}
```

---

### 🔹 Runtime Polymorphism in Action
```java
Animal dog = new Dog();
dog.sound();
```

Output:
```
Dog barks
```

---

## 5️⃣ Upcasting

### 🔹 Definition
Assigning a **child class object** to a **parent class reference** is called **upcasting**.

```java
Animal dog = new Dog();
```

Rules:
- Upcasting is implicit
- Only parent class methods can be called
- Overridden methods execute child implementation

---

## 6️⃣ Downcasting

### 🔹 Definition
Converting a parent class reference back to a child class reference is called **downcasting**.

```java
Dog d = (Dog) dog;
```

📌 Downcasting must be explicit and can cause `ClassCastException` if incorrect.

---

## 7️⃣ Important Rules of Runtime Polymorphism

- Requires inheritance
- Requires method overriding
- Static methods are not polymorphic
- Final methods cannot be overridden
- Constructors do not participate

---

## 🧠 Interview One-Liners

- Polymorphism means same method, different behavior
- Method overloading is compile-time polymorphism
- Method overriding is runtime polymorphism
- Runtime polymorphism is also called dynamic method dispatch
- Parent reference can refer to child object
- Upcasting is implicit, downcasting is explicit

---

## ⚠ Common Interview Traps

- Overloading is not runtime polymorphism
- Return type alone cannot overload methods
- Static methods are hidden, not overridden
- Incorrect downcasting leads to ClassCastException

---

## 🧠 Quick Revision

Compile-time → Method Overloading  
Runtime → Method Overriding  
Upcasting → Parent reference = Child object  
Downcasting → Explicit cast
