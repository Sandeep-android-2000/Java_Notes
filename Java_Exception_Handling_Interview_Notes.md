
# Java Interview Notes – Exception Handling in Java

---

## 1️⃣ Types of Errors in Java

Java programs can face three kinds of errors:

### 🔹 Syntax Error
- Occurs due to incorrect syntax
- Detected at compile time

---

### 🔹 Logical Error
- Program runs but gives wrong output
- Caused by incorrect logic

---

### 🔹 Runtime Error
- Occurs during execution
- Program may crash
- Handled using exception handling

---

## 2️⃣ What is Exception Handling?

Exception handling is a mechanism to **handle runtime errors** so that the **normal flow of the application can be maintained**.

---

## 3️⃣ What is an Exception?

An exception is:
- An event that disrupts normal program flow
- An object that is thrown at runtime

---

## 4️⃣ Exception Hierarchy

```
Object
 └── Throwable
      ├── Exception
      │    └── RuntimeException
      └── Error
```

---

## 5️⃣ Stack Trace

A stack trace:
- Shows method call sequence
- Displays line number where exception occurred
- Helps in debugging

---

## 6️⃣ Checked vs Unchecked Exceptions

### 🔹 Checked Exceptions
- Checked at compile time
- Compiler forces handling

Examples:
- IOException
- SQLException

---

### 🔹 Unchecked Exceptions
- Not checked at compile time
- Occur at runtime

Examples:
- NullPointerException
- ArithmeticException

---

## 7️⃣ try-catch Block

```java
try {
    int a = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Exception handled");
}
```

---

## 8️⃣ throws Keyword

Used to **delegate exception handling** to the caller.

```java
void readFile() throws IOException {
}
```

---

## 9️⃣ throw Keyword

Used to **explicitly throw an exception**.

```java
throw new ArithmeticException("Error");
```

---

## 🔟 finally Block

Used to manage resources like files or streams.

```java
finally {
    bufferedReader.close();
}
```

---

## 1️⃣1️⃣ Custom Exception

We can create custom exceptions by extending `Exception`.

```java
class InvalidAgeException extends Exception {
    InvalidAgeException(String msg) {
        super(msg);
    }
}
```

---

## 🧠 Interview One-Liners

- Exception is an object thrown at runtime
- Checked exceptions are compile-time
- Unchecked exceptions are runtime
- throw is used to create exception
- throws is used to delegate handling
- finally is used for cleanup

---

## 🧠 Quick Revision

Syntax → Compile-time  
Logic → Wrong output  
Runtime → Exception  
throw → Explicit  
throws → Delegate  
finally → Cleanup
