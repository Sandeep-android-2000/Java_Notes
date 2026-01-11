
# Java Interview Notes – JVM, JDK, JRE, Execution Flow & Basics (Revised)

---

## 1️⃣ JDK vs JRE vs JVM

### 🔹 JDK (Java Development Kit)
The **JDK** provides tools and libraries that help developers **write, compile, and debug Java code**.

Includes:
- Compiler (`javac`)
- Debugger (`jdb`)
- Development tools (`jar`, `javadoc`, `jshell`)
- Standard Java libraries
- JRE

📌 Used during **development phase**.

---

### 🔹 JRE (Java Runtime Environment)
The **JRE provides the runtime environment required to run Java programs**.

Includes:
- JVM
- Core Java libraries

❌ Does NOT include compiler or debugger

📌 Used during **execution phase**.

---

### 🔹 JVM (Java Virtual Machine)
The **JVM executes Java bytecode and converts it into machine code**.

Responsibilities:
- Loads `.class` files
- Verifies bytecode
- Executes bytecode
- Manages memory
- Performs garbage collection

📌 Bytecode → Platform Independent  
📌 JVM → Platform Dependent

---

### 🔹 Relationship
```
JDK → JRE → JVM
```

---

## 2️⃣ How Java Code Is Executed

### 🔹 Overall Flow
```
test.java 
   ↓ (compile using javac)
test.class (Bytecode – Platform Independent)
   ↓ (run using JVM)
Machine Code (Platform Dependent)
```

---

### 🔹 Compilation Phase
- `test.java` is compiled using **javac**
- Output is a `.class` file
- `.class` file contains **bytecode**

```
test.java → javac → test.class
```

---

### 🔹 Execution Phase (Inside JVM)

#### 🔸 Interpreter
- Parses bytecode instructions
- Groups instructions
- Interprets **line by line**
- Slower execution
- Repeats work for every call

#### 🔸 JIT (Just-In-Time Compiler)
- Identifies frequently executed code
- Converts bytecode directly to machine code
- Improves performance

📌 JVM uses **Interpreter + JIT together**

---

## 3️⃣ Stack vs Heap Memory

### 🔹 Stack Memory
Used for:
- Method calls
- Local variables
- Reference variables

Characteristics:
- LIFO structure
- Fast access
- Thread-safe
- Automatically cleared

---

### 🔹 Heap Memory
Used for:
- Objects
- Class instances

Characteristics:
- Shared among threads
- Slower than stack
- Managed by Garbage Collector

---

### 🔹 Stack vs Heap Comparison

| Feature | Stack | Heap |
|------|------|------|
| Stores | Local variables, references | Objects |
| Speed | Faster | Slower |
| Thread Safe | Yes | No |
| Garbage Collected | No | Yes |

---

## 4️⃣ Primitive vs Reference Types

### 🔹 Primitive Types
Examples:
- int, double, char, boolean

Characteristics:
- Store actual value
- Fixed size
- Stored in stack
- Cannot be null

---

### 🔹 Reference Types
Examples:
- Objects, Arrays, Strings

Characteristics:
- Store memory address
- Reference stored in stack
- Object stored in heap
- Can be null

---

## 5️⃣ Java Hello World Program – Code Breakdown

### 🔹 Code Example
```java
class Test {
    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}
```

---

### 🔹 Breakdown of Code

#### 🔸 `class Test`
- Defines a class named `Test`
- Every Java program must have at least one class

---

#### 🔸 `public static void main(String[] args)`
- **public**: JVM can access this method
- **static**: No object needed to call the method
- **void**: No return value
- **main**: Entry point of Java program
- **String[] args**: Command-line arguments

---

#### 🔸 `System.out.println("Hello World");`

##### `System`
- Class in `java.lang` package
- Provides access to system resources like console

##### `out`
- Static instance of `PrintStream` class
- Represents standard output stream

##### `println`
- Method of `PrintStream` class
- Prints text and moves cursor to next line

---

## 🧠 Interview One-Liners

- `.class` file contains bytecode
- Bytecode is platform independent
- JVM converts bytecode to machine code
- Interpreter executes bytecode line by line
- JIT improves performance
- Objects live in heap, references live in stack
- `main()` is the entry point of Java program
