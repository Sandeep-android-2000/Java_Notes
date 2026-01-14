
# Java Interview Notes – static and final Keywords

---

## 1️⃣ static Keyword

### 🔹 What is static?
The `static` keyword is used to make **class-level members** instead of object-level members.

Static members belong to the **class**, not to individual objects.

---

## 2️⃣ static Variables

### 🔹 Definition
A static variable is **shared among all objects** of a class.

- Only one copy exists
- Stored in Method Area / Metaspace
- Initialized once during class loading

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
Static methods:
- Belong to class
- Can be called without object creation

### 🔹 Example
```java
class Utils {
    static void greet() {
        System.out.println("Hello");
    }
}

Utils.greet();
```

### 🔹 Rules
- Can access only static members
- Cannot use `this` or `super`
- Cannot access instance variables directly

---

## 4️⃣ static Block

### 🔹 Definition
Used to initialize static variables.

- Executes once
- Runs when class is loaded
- Executes before main()

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

Only inner classes can be static.

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

## 6️⃣ final Keyword

### 🔹 What is final?
The `final` keyword is used to **restrict modification**.

It can be applied to:
- Variables
- Methods
- Classes

---

## 7️⃣ final Variable

### 🔹 Definition
Once assigned, value **cannot be changed**.

```java
final int MAX = 100;
```

---

## 8️⃣ final Method

### 🔹 Definition
Final methods **cannot be overridden**.

```java
class Parent {
    final void show() {
        System.out.println("Final method");
    }
}
```

---

## 9️⃣ final Class

### 🔹 Definition
Final classes **cannot be inherited**.

```java
final class Utility {
}
```

Example: String class

---

## 🔟 static vs final

| Feature | static | final |
|------|------|------|
| Purpose | Class-level | Restriction |
| Applies to | Variables, Methods, Blocks, Classes | Variables, Methods, Classes |
| Modification | Allowed | Not Allowed |

---

## 🧠 Interview One-Liners

- static belongs to class
- final prevents modification
- static method cannot use this
- final method cannot be overridden
- final class cannot be inherited
- static block runs before main()

---

## ⚠ Interview Traps

- Static methods are not overridden (method hiding)
- Constructor cannot be static
- static and final together create constants

---

## 🧠 Quick Revision

static → class-level  
final → restriction  
static + final → constants  
static block → class load time
