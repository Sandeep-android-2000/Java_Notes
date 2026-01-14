
# Java Interview Notes – Abstraction

---

## 1️⃣ What is Abstraction?

Abstraction is the process of **hiding implementation details** and exposing **only essential features** to the user.

It focuses on:
- What an object does
- Not how it does it

---

## 2️⃣ Why Abstraction is Needed

- Reduces complexity
- Improves maintainability
- Encourages loose coupling
- Allows partial implementation

Sometimes, we do not need to implement all methods immediately.

---

## 3️⃣ Abstract Class

### 🔹 Definition
An **abstract class** is declared using the `abstract` keyword.

Characteristics:
- Can contain **abstract methods**
- Can contain **non-abstract (concrete) methods**
- Cannot be instantiated
- Can have constructors

---

### 🔹 Example
```java
abstract class Vehicle {

    abstract void start();

    void stop() {
        System.out.println("Vehicle stopped");
    }
}
```

📌 Abstract class can contain both abstract and concrete methods.

---

## 4️⃣ Abstract Methods

### 🔹 Definition
An abstract method:
- Has no method body
- Must be implemented by subclasses

```java
abstract void start();
```

📌 If a class has at least one abstract method, the class must be abstract.

---

## 5️⃣ Instantiation Rules

- Abstract classes cannot be instantiated
- Reference of abstract class can be created

```java
Vehicle v = new Car();
```

📌 Used for runtime polymorphism.

---

## 6️⃣ Constructors in Abstract Class

### 🔹 Important Fact
- Abstract classes can have constructors
- Constructors are used for **initial setup**
- Commonly marked as `protected`

```java
abstract class Vehicle {
    protected Vehicle() {
        System.out.println("Vehicle initialized");
    }
}
```

📌 Constructor is called when child class object is created.

---

## 7️⃣ Abstract Class vs Concrete Class

| Feature | Abstract Class | Concrete Class |
|------|---------------|---------------|
| Instantiation | No | Yes |
| Abstract Methods | Allowed | Not allowed |
| Constructors | Yes | Yes |
| Object Creation | Via subclass | Direct |

---

## 8️⃣ Abstract Class vs Interface (Quick Comparison)

| Feature | Abstract Class | Interface |
|------|---------------|----------|
| Methods | Abstract + Concrete | Abstract / Default |
| Variables | Instance | public static final |
| Constructor | Yes | No |
| Multiple Inheritance | No | Yes |

---

## 🧠 Interview One-Liners

- Abstraction hides implementation details
- Abstract class cannot be instantiated
- Abstract class can have concrete methods
- Abstract class can have constructors
- Reference of abstract class is allowed

---

## ⚠ Common Interview Traps

- Abstract class is not fully abstract
- Abstract methods cannot have body
- Abstract class constructor is executed via child class

---

## 🧠 Quick Revision

Abstraction → Implementation hiding  
Abstract class → Partial abstraction  
No instantiation → Reference allowed  
Constructor → Initialization
