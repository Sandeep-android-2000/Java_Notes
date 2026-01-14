
# Java Interview Notes – Wrapper Classes

---

## 1️⃣ What are Wrapper Classes?

Wrapper classes are used to **convert primitive data types into objects**.

Each primitive type in Java has a corresponding wrapper class.

---

## 2️⃣ Why Wrapper Classes are Needed

- Java collections work with objects, not primitives
- Wrapper classes support **null values**
- Required in frameworks and APIs
- Enable object-oriented features

---

## 3️⃣ Primitive Types vs Wrapper Classes

| Primitive | Wrapper |
|---------|---------|
| int | Integer |
| double | Double |
| char | Character |
| boolean | Boolean |
| byte | Byte |
| short | Short |
| long | Long |
| float | Float |

---

## 4️⃣ Autoboxing

### 🔹 Definition
Autoboxing is the automatic conversion of a **primitive value into its corresponding wrapper object**.

Internally, Java uses the `valueOf()` method.

---

### 🔹 Example
```java
int x = 10;
Integer obj = Integer.valueOf(x); // Autoboxing
```

---

## 5️⃣ Unboxing

### 🔹 Definition
Unboxing is the conversion of a **wrapper object back into a primitive type**.

---

### 🔹 Example
```java
Integer obj = 20;
int x = obj; // Unboxing
```

---

## 6️⃣ valueOf() Method

The `valueOf()` method:
- Converts primitive or String to wrapper object
- Used internally during autoboxing

```java
Integer a = Integer.valueOf(10);
Integer b = Integer.valueOf("100");
```

---

## 7️⃣ Null Handling

- Primitive data types cannot hold null
- Wrapper classes can hold null values

```java
Integer x = null; // Valid
// int y = null;  // Compile-time error
```

---

## 8️⃣ Wrapper Classes in Collections

Collections store **objects only**.

```java
List<Integer> list = new ArrayList<>();
list.add(10); // Autoboxing happens internally
```

---

## 🧠 Interview One-Liners

- Wrapper classes convert primitives to objects
- Autoboxing uses valueOf() internally
- Wrapper classes support null
- Collections require wrapper classes

---

## ⚠ Common Interview Traps

- NullPointerException during unboxing
- Using == with wrapper objects
- Excessive autoboxing affects performance

---

## 🧠 Quick Revision

Primitive → Wrapper → Object  
Autoboxing → Primitive to Object  
Unboxing → Object to Primitive  
Wrapper → Supports null
