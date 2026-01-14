
# Java Interview Notes – Access Modifiers

---

## 1️⃣ What are Access Modifiers?

Access Modifiers in Java are used to **control the visibility and accessibility** of classes, variables, methods, and constructors.

They help in:
- Data hiding
- Encapsulation
- Security
- Controlled access

---

## 2️⃣ Types of Access Modifiers

Java provides four access modifiers:
1. private
2. default (no keyword)
3. protected
4. public

---

## 3️⃣ private Access Modifier

### 🔹 Definition
Accessible **only within the same class**.

- Most restrictive
- Used for data hiding

```java
class Account {
    private int balance;
}
```

---

## 4️⃣ default Access Modifier (Package-Private)

### 🔹 Definition
When no modifier is specified.

Accessible:
- Within the same package only

```java
class Student {
    int rollNo;
}
```

---

## 5️⃣ protected Access Modifier

### 🔹 Definition
Accessible:
- Within same package
- In subclasses outside package

```java
class Parent {
    protected void show() {
        System.out.println("Protected");
    }
}
```

---

## 6️⃣ public Access Modifier

### 🔹 Definition
Accessible from anywhere.

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello");
    }
}
```

---

## 7️⃣ Accessibility Comparison Table

| Modifier | Same Class | Same Package | Subclass (Diff Package) | Everywhere |
|--------|-----------|--------------|--------------------------|------------|
| private | Yes | No | No | No |
| default | Yes | Yes | No | No |
| protected | Yes | Yes | Yes | No |
| public | Yes | Yes | Yes | Yes |

---

## 8️⃣ Access Modifiers on Classes

Allowed for top-level classes:
- public
- default

Not allowed:
- private
- protected

---

## 9️⃣ Constructors & Access Modifiers

Used to control object creation.

```java
class Singleton {
    private Singleton() {}
}
```

---

## 🧠 Interview One-Liners

- private → class only
- default → package only
- protected → package + subclass
- public → everywhere

---

## ⚠ Interview Traps

- default is not public
- protected is not accessible everywhere
- private members are not inherited

---

## 🧠 Quick Revision

private → class  
default → package  
protected → package + child  
public → everywhere
