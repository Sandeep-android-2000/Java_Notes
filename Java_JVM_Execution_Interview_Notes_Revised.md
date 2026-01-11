
# Java Interview Notes – JVM, JDK, JRE & Execution Flow (Revised)

---

## 1️⃣ JDK vs JRE vs JVM

### 🔹 JDK (Java Development Kit)
The **JDK** provides all the **tools and libraries required to write and develop Java programs**.

It is used when you are **writing, compiling, and debugging Java code**.

Includes:
- Compiler (`javac`)
- Debugger (`jdb`)
- Development tools (`jar`, `javadoc`, `jshell`)
- Standard Java libraries
- JRE (internally)

📌 **Purpose**: Development (write + debug + compile)

---

### 🔹 JRE (Java Runtime Environment)
The **JRE provides the runtime environment required to run a Java program**.

It is used when:
- You want to **execute** Java applications
- You are **not writing or compiling code**

Includes:
- JVM
- Core Java class libraries

❌ Does NOT include compiler or debugger

📌 **Purpose**: Runtime execution only

---

### 🔹 JVM (Java Virtual Machine)
The **JVM is responsible for executing Java bytecode**.

It:
- Converts bytecode into machine code
- Manages memory
- Handles garbage collection
- Ensures security

📌 JVM is **platform dependent**
📌 Bytecode is **platform independent**

---

### 🔹 Relationship Summary
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

### 🔹 Step 1: Compilation Phase
- Source code (`test.java`) is compiled using **javac**
- Output is a **`.class` file**
- `.class` file contains **bytecode**
- Bytecode is **platform independent**

```
test.java → javac → test.class (bytecode)
```

---

### 🔹 Step 2: Class Loading
- JVM loads `.class` file using **ClassLoader**
- Required classes are loaded into memory

---

### 🔹 Step 3: Execution Phase (Inside JVM)

JVM executes bytecode using:

### 🔸 Interpreter
- Reads bytecode
- Parses instructions
- Interprets **line by line**
- Slower execution
- Repeats interpretation every time method is called

📌 **Interpreter parses once and groups instructions, but executes line by line**

---

### 🔸 JIT (Just-In-Time Compiler)
- Detects **frequently executed code**
- Converts bytecode directly into **machine code**
- Improves performance
- Avoids repeated interpretation

📌 JVM uses **both Interpreter and JIT together**

---

### 🔹 Execution Flow Inside JVM
```
.class (Bytecode)
   ↓
Interpreter  →  JIT Compiler
   ↓
Machine Code (OS dependent)
```

---

## 3️⃣ Stack vs Heap Memory

### 🔹 Stack Memory
Used for:
- Method calls
- Local variables
- Reference variables

Characteristics:
- LIFO (Last In First Out)
- Fast access
- Thread-safe
- Automatically cleared when method execution ends

---

### 🔹 Heap Memory
Used for:
- Object storage
- Class instances

Characteristics:
- Shared among threads
- Slower access
- Managed by Garbage Collector
- Larger memory size

---

### 🔹 Stack vs Heap Comparison

| Feature | Stack | Heap |
|------|------|------|
| Stores | Local variables, references | Objects |
| Speed | Faster | Slower |
| Thread Safe | Yes | No |
| Garbage Collected | No | Yes |

---

### 🔹 Example
```java
int x = 10;                 // stored in stack
Student s = new Student();  // reference in stack, object in heap
```

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
- Objects
- Arrays
- Strings

Characteristics:
- Store memory address
- Reference stored in stack
- Object stored in heap
- Can be null

---

### 🔹 Comparison

| Feature | Primitive | Reference |
|------|----------|----------|
| Stores | Actual value | Memory address |
| Location | Stack | Stack + Heap |
| Null Allowed | No | Yes |

---

## 🧠 Interview One-Liners

- JDK is used for development, JRE is used for execution.
- Bytecode is platform independent, JVM is platform dependent.
- `.class` file contains bytecode.
- Interpreter executes bytecode line by line.
- JIT improves performance by compiling frequently used code.
- Objects are stored in heap, references are stored in stack.
