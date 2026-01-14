
# Java Interview Notes – Enums in Java

---

## 1️⃣ What are Enums?

**Enum** stands for **Enumeration**.

Enums are used to define a **fixed set of named constants** in a type-safe manner.

---

## 2️⃣ Why Enums?

Earlier approaches:
- public static final constants in a class
- Constants in an interface

Problems:
- Not type-safe
- Poor grouping
- No behavior support

📌 Best approach is to use **enum**.

---

## 3️⃣ Basic Enum Example

```java
enum Day {
    MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY
}
```

📌 At compile time, each enum constant becomes an **instance of the enum type**.

---

## 4️⃣ Important Properties of Enum

- Enum constants are implicitly `public static final`
- Enum constants are **objects**
- Enums are inherently static
- Enum cannot extend another class
- Enum can implement interfaces

---

## 5️⃣ Common Enum Methods

All enums implicitly extend `java.lang.Enum`.

### 🔹 ordinal()
Returns index of enum constant.

```java
Day.MONDAY.ordinal(); // 0
```

---

### 🔹 name()
Returns name of enum constant.

```java
Day.MONDAY.name(); // "MONDAY"
```

---

### 🔹 toString()
Returns string representation.

```java
Day.MONDAY.toString();
```

---

### 🔹 valueOf()
Converts string to enum constant.

```java
Day.valueOf("MONDAY");
```

---

## 6️⃣ Enum with Fields and Constructor

Enums can have:
- Fields
- Methods
- Constructors

📌 Constructors are **private by default**.

```java
enum Status {

    SUCCESS(200),
    ERROR(500);

    private int code;

    Status(int code) {
        this.code = code;
    }

    public int getCode() {
        return code;
    }
}
```

---

## 7️⃣ Enum Constructor Rules

- Cannot use `new` to create enum objects
- Constructor is called once per constant
- Used for initial setup

---

## 8️⃣ Enums in Switch Statement

### Java 12+ Switch Syntax

```java
switch (day) {
    case MONDAY -> {
        System.out.println("Start of week");
    }
    case FRIDAY -> {
        System.out.println("End of week");
    }
}
```

---

## 🧠 Interview One-Liners

- Enum means enumeration
- Enum constants are objects
- Enum fields are static and final
- Enum constructors are private
- Avoid using ordinal() in logic

---

## ⚠ Interview Traps

- Enum cannot extend classes
- Enum can have methods and fields
- valueOf throws exception for invalid input

---

## 🧠 Quick Revision

Enum → Enumeration  
Constants → Objects  
Implicit → static + final  
Constructor → private  
Switch → Java 12 arrow syntax
