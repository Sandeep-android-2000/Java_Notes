
# Java Interview Notes – static and final Keywords (Refined)

---

## 1️⃣ static Keyword

### 🔹 What is static?
The `static` keyword is **primarily used for memory management** in Java.

The main concept behind `static` is:
> **Static members belong to the class rather than instances of the class.**

Because of this:
- Only **one copy** of static members exists
- Memory is shared across all objects of the class

---

### 🔹 Where can static be applied?
The `static` keyword can be applied to:
- Variables
- Methods
- Blocks
- Nested classes

---

## 2️⃣ static Variables

### 🔹 Definition
A static variable is a **class-level variable** shared among all objects.

Characteristics:
- Single copy in memory
- Stored in **Method Area / Metaspace**
- Initialized when the class is loaded

### 🔹 Example
```java
class Counter {
    static int count = 0;

    Counter() {
        count++;
    }
}
```

---

## 3️⃣ static Methods

### 🔹 Definition
A static method:
- Belongs to the class
- Can be called without creating an object

### 🔹 Example
```java
class Utils {
    static void greet() {
        System.out.println("Hello");
    }
}

Utils.greet();
```

---

### 🔹 Rules of static Methods
- ❌ Cannot use non-static data members
- ❌ Cannot call non-static methods directly
- ❌ Cannot use `this` or `super`
- ✅ Can access only static members

📌 Reason: Static context has **no object reference**.

---

## 4️⃣ static Block

### 🔹 Definition
Used to initialize static variables.

Characteristics:
- Executes once
- Runs when class is loaded into JVM
- Executes before `main()`

### 🔹 Example
```java
class Test {
    static int x;

    static {
        x = 10;
        System.out.println("Static block executed");
    }
}
```

---

## 5️⃣ static Nested Class

Only nested (inner) classes can be static.

```java
class Outer {
    static class Inner {
        void show() {
            System.out.println("Inside static inner class");
        }
    }
}
```

---

## 6️⃣ static Use Case – Singleton Design Pattern

### 🔹 Why static in Singleton?
- Static variable holds the single instance
- Static method provides global access point
- No object required to access instance

### 🔹 Example
```java
class Singleton {
    private static Singleton instance;

    private Singleton() {}

    public static Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }
}
```

---

## 7️⃣ final Keyword

### 🔹 What is final?
The `final` keyword is used to **restrict modification**.

Applied to:
- Variables
- Methods
- Classes

---

## 8️⃣ final Variable

### 🔹 Definition
Once assigned, a final variable cannot be changed.

```java
final int MAX = 100;
```

---

## 9️⃣ final Method

### 🔹 Definition
Final methods cannot be overridden.

```java
class Parent {
    final void show() {
        System.out.println("Final method");
    }
}
```

---

## 🔟 final Class

### 🔹 Definition
Final classes cannot be inherited.

```java
final class Utility {
}
```

Example: String class

---

## 1️⃣1️⃣ static vs final

| Feature | static | final |
|------|------|------|
| Purpose | Memory management | Restriction |
| Belongs to | Class | Depends |
| Modification | Allowed | Not Allowed |

---

## 🧠 Interview One-Liners

- static is used mainly for memory management
- static members belong to class, not object
- static methods cannot access non-static members
- this and super cannot be used in static context
- final variable cannot be reassigned
- final method cannot be overridden
- final class cannot be inherited

---

## ⚠ Interview Traps

- Static methods are not overridden (method hiding)
- Constructor cannot be static
- static + final is used for constants
- main() is static so JVM can call it without object

---

## 🧠 Quick Revision

static → class-level → shared memory  
final → restriction  
static + final → constants  
static in Singleton → single instance
