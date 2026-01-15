
# Java Interview Notes – Inner Classes in Java

---

## 1️⃣ What are Inner Classes?

An **inner class** is a class defined **inside another class**.

They are mainly used to:
- Increase encapsulation
- Group logically related classes
- Access outer class members easily

---

## 2️⃣ Types of Inner Classes

Java supports four types of inner classes:

1. Member Inner Class  
2. Static Inner Class  
3. Local Inner Class  
4. Anonymous Inner Class  

---

## 3️⃣ Member Inner Class

### 🔹 Definition
A **member inner class** is a non-static class declared inside another class.

```java
class Outer {
    class Inner {
    }
}
```

📌 This inner class becomes a **member of the outer class instance**.

---

### 🔹 Characteristics
- Depends on outer class object
- Can access all members of outer class (even private)
- Cannot contain static members (except constants)

---

### 🔹 Example
```java
class Outer {
    private int x = 10;

    class Inner {
        void show() {
            System.out.println(x);
        }
    }
}
```

---

### 🔹 Object Creation
```java
Outer outer = new Outer();
Outer.Inner inner = outer.new Inner();
inner.show();
```

---

## 4️⃣ Static Inner Class

### 🔹 Definition
A **static inner class** is declared using `static` keyword.

```java
class Outer {
    static class Inner {
    }
}
```

---

### 🔹 Characteristics
- Does not require outer class object
- Can access only static members of outer class
- Can have static members

---

### 🔹 Example
```java
class Outer {
    static int x = 20;

    static class Inner {
        void show() {
            System.out.println(x);
        }
    }
}
```

---

### 🔹 Object Creation
```java
Outer.Inner inner = new Outer.Inner();
inner.show();
```

---

## 5️⃣ Local Inner Class

### 🔹 Definition
A local inner class is defined inside a method.

---

### 🔹 Example
```java
class Outer {
    void display() {
        int y = 5;

        class LocalInner {
            void show() {
                System.out.println(y);
            }
        }

        LocalInner li = new LocalInner();
        li.show();
    }
}
```

📌 Local variables must be effectively final.

---

## 6️⃣ Anonymous Inner Class

### 🔹 Definition
An anonymous inner class has no name and is used for one-time implementation.

---

### 🔹 Example
```java
interface Animal {
    void sound();
}

class Test {
    public static void main(String[] args) {
        Animal a = new Animal() {
            public void sound() {
                System.out.println("Dog barks");
            }
        };
        a.sound();
    }
}
```

---

## 7️⃣ Comparison Table

| Type | Outer Object Needed | Static Allowed |
|----|-------------------|---------------|
| Member Inner | Yes | No |
| Static Inner | No | Yes |
| Local Inner | Yes | No |
| Anonymous Inner | Yes | No |

---

## 🧠 Interview One-Liners

- Member inner class depends on outer object
- Static inner class is class-level
- Local inner class is method scoped
- Anonymous inner class is one-time use

---

## 🧠 Quick Revision

Member → Instance dependent  
Static → No outer object  
Local → Method scope  
Anonymous → No name
