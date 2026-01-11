# Java String Class – Complete Documentation

## 1. What is a String in Java?

In Java, `String` is a **class** used to represent a sequence of characters.

```java
String s = "Hello";
```

### Key Properties
- `String` is **immutable**
- Stored in **String Constant Pool**
- Part of `java.lang` package

---

## 2. Ways to Create a String

```java
String s1 = "Hello";            // String literal (SCP)
String s2 = new String("Hello"); // Heap memory
```

---

## 3. Length & Empty Checks

### length()
```java
String s = "Java";
System.out.println(s.length()); // 4
```

### isEmpty()
```java
String s = "";
System.out.println(s.isEmpty()); // true
```

### isBlank() (Java 11+)
```java
String s = "   ";
System.out.println(s.isBlank()); // true
```

---

## 4. Character Access

### charAt()
```java
String s = "Hello";
System.out.println(s.charAt(1)); // e
```

### toCharArray()
```java
char[] arr = "Java".toCharArray();
```

---

## 5. Comparison Methods

### equals()
```java
"Java".equals("Java"); // true
```

### equalsIgnoreCase()
```java
"java".equalsIgnoreCase("JAVA"); // true
```

### compareTo()
```java
"abc".compareTo("abd"); // negative
```

---

## 6. Substring

```java
String s = "SpringBoot";
System.out.println(s.substring(0, 6)); // Spring
System.out.println(s.substring(6));    // Boot
```

---

## 7. Searching

```java
"Hello World".contains("World"); // true
"banana".indexOf("na");          // 2
"banana".lastIndexOf("na");      // 4
```

---

## 8. Case Conversion

```java
"java".toUpperCase(); // JAVA
"JAVA".toLowerCase(); // java
```

---

## 9. Trimming & Replacing

```java
"  hello  ".trim(); // hello
"apple".replace('a','A'); // Apple
"abc123".replaceAll("\\d",""); // abc
```

---

## 10. Splitting

```java
String s = "a,b,c";
String[] arr = s.split(",");
```

---

## 11. Concatenation

```java
String s = "Hello" + " World";
"Hello".concat(" World");
```

---

## 12. Conversion

```java
String s = String.valueOf(10);
```

---

## 13. Interning

```java
String s1 = new String("Java");
String s2 = s1.intern();
```

---

## 14. Immutability Example

```java
String s = "Hello";
s.concat(" World");
System.out.println(s); // Hello
```

Correct:
```java
s = s.concat(" World");
```

---

## 15. Common Interview Mistakes

```java
String a = "Java";
String b = new String("Java");

a == b;        // false
a.equals(b);   // true
```

---

## 16. When to Use What?

| Use Case | Class |
|---------|------|
| Immutable | String |
| Fast, Mutable | StringBuilder |
| Thread-safe | StringBuffer |

---

## End of Documentation
