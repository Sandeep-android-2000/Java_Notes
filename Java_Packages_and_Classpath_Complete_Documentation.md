# Java Packages & Classpath – Complete Documentation

## 1. What is a Package in Java?

A **package** in Java is a **namespace** that groups related classes and interfaces together.

### Why Packages?
- Avoid **class name conflicts**
- Better **code organization**
- Control **access (protected/default)**
- Reusability & maintainability

```java
package com.example.service;
```

---

## 2. Types of Packages

### 2.1 Built-in Packages
Provided by Java SDK.

Examples:
- `java.lang` (String, Math, System)
- `java.util` (List, Map, Collections)
- `java.io` (File, InputStream)
- `java.time` (LocalDate, Instant)

```java
import java.util.List;
```

---

### 2.2 User-Defined Packages

```java
package com.company.project.module;
```

---

## 3. Package Naming Conventions

✔ Reverse domain name style

```text
com.companyname.projectname.layer
```

Rules:
- All lowercase
- Meaningful hierarchy
- Avoid underscores

---

## 4. Creating Packages

```java
package com.demo;

public class Test {
    public static void main(String[] args) {
        System.out.println("Hello Package");
    }
}
```

---

## 5. Accessing Classes from Other Packages

### Fully Qualified Name
```java
com.demo.Test t = new com.demo.Test();
```

### Using import
```java
import com.demo.Test;
```

---

## 6. Access Modifiers & Packages

| Modifier | Same Class | Same Package | Subclass | Other Package |
|--------|-----------|-------------|----------|---------------|
| public | ✔ | ✔ | ✔ | ✔ |
| protected | ✔ | ✔ | ✔ | ❌ |
| default | ✔ | ✔ | ❌ | ❌ |
| private | ✔ | ❌ | ❌ | ❌ |

---

## 7. What is Classpath?

Classpath tells JVM where to find `.class` files and libraries.

---

## 8. Setting Classpath

### Command Line (Linux/Mac)
```bash
java -cp lib/*:bin com.demo.Main
```

### Command Line (Windows)
```bash
java -cp lib/*;bin com.demo.Main
```

---

## 9. Classpath vs PATH

| PATH | CLASSPATH |
|------|-----------|
| OS commands | JVM classes |
| Finds java/javac | Finds .class/.jar |

---

## 10. Common Errors

- `ClassNotFoundException`
- `NoClassDefFoundError`

---

## 11. Spring Boot Package Structure

```text
com.company.project
 ├── controller
 ├── service
 ├── repository
 ├── dto
 └── config
```

---

## End of Documentation
