
# Java Interview Notes – String vs StringBuilder vs StringBuffer

---

## 1️⃣ Overview

`String`, `StringBuilder`, and `StringBuffer` are used to **store a sequence of characters**.

The difference between them lies in:
- Mutability
- Performance
- Thread safety

---

## 2️⃣ String

### 🔹 Definition
`String` is **immutable**, meaning its value cannot be changed once created.

Strings are stored in the **String Pool**.

---

### 🔹 Immutability Example
```java
String s = "Hello";
s = s + " World";
```
📌 A new String object is created every time.

---

### 🔹 concat() Method
```java
String s1 = "Hello";
String s2 = s1.concat(" World");
```
- Creates a new String
- Original String remains unchanged

---

### 🔹 Why String is Immutable?
- Security (String Pool)
- Thread safety
- Performance optimization
- Used as keys in HashMap

---

## 3️⃣ StringBuilder

### 🔹 Definition
`StringBuilder` is **mutable** and optimized for **performance**.

- Not thread-safe
- Faster than StringBuffer
- Best for single-threaded usage

---

### 🔹 Method Chaining
```java
StringBuilder sb = new StringBuilder("Hello");
sb.append(" World").append("!");
```

---

### 🔹 Common Methods
```java
sb.replace(1, 4, "abc");
sb.delete(1, 3);
sb.length();
sb.reverse();
```

---

### 🔹 Internal Working
- Uses an internal **char[]**
- Default capacity = **16**
- Capacity doubles when exceeded

---

## 4️⃣ StringBuffer

### 🔹 Definition
`StringBuffer` is **mutable** and **thread-safe**.

- Methods are synchronized
- Slower than StringBuilder
- Suitable for multi-threaded environments

---

## 5️⃣ Comparison Table

| Feature | String | StringBuilder | StringBuffer |
|------|--------|---------------|--------------|
| Mutability | No | Yes | Yes |
| Thread Safe | Yes | No | Yes |
| Performance | Slow | Fast | Medium |
| Synchronization | N/A | No | Yes |
| Stored in Pool | Yes | No | No |

---

## 6️⃣ When to Use

- Use **String** when value does not change
- Use **StringBuilder** for frequent modifications
- Use **StringBuffer** when thread safety is required

---

## 🧠 Interview One-Liners

- String is immutable and stored in string pool
- `+` operator creates new String objects
- StringBuilder is mutable and fastest
- StringBuffer ensures thread safety

---

## ⚠ Interview Traps

- Using String in loops hurts performance
- StringBuilder is not thread-safe
- concat() does not modify original string

---

## 🧠 Quick Revision

String → Immutable  
StringBuilder → Mutable + Fast  
StringBuffer → Mutable + Thread-safe
