# Data Types

A **Data Type** in Java tells the JVM:  
- The kind of values that can be stored in a variable.  
- The operations that can be performed on that variable.  

In Java, there are **two kinds of data types**:  
- **Primitive Data Types**  
- **Reference Data Types**

---

## Primitive Data Types

Unlike Scala’s data types, Java has **primitive data types** which are stored directly in the memory slot of a given variable.  

For example:
```java
int x = 42; // x literally has 42 stored in it
```

**Primitive Data Types:**

| Type     | Size   | Example                        |
|----------|--------|--------------------------------|
| byte     | 8-bit  | `byte b = 100;`                |
| short    | 16-bit | `short s = 300;`               |
| int      | 32-bit | `int x = 42;`                  |
| long     | 64-bit | `long l = 123L;`               |
| float    | 32-bit | `float f = 3.14f;`             |
| double   | 64-bit | `double d = 3.14159;`          |
| char     | 16-bit | `char c = 'A';`                |
| boolean  | 1-bit  | `boolean flag = true;`         |

✅ **Advantages**: Fast and efficient.  

---

## Reference Data Types

These are **custom data types** that are stored as a reference (pointer) to an object in memory.  

For example:
```java
String x = "Hello World"; 
// x is a reference pointing to the "Hello World" object
```

Any **class, object, or collection** you define is considered a **reference type**.  
👉 In modern IDEs, if a type is not highlighted when defined, it’s most likely a reference type.  

---

## Primitive Wrappers

Since primitive types are not objects:  
- They **cannot** be used in collections.  
- They **lack utility methods** (e.g., no `.toString()` on `int`).  

To solve this, Java provides **wrapper classes** in the `java.lang` library.  

| Primitive | Wrapper   |
|-----------|-----------|
| byte      | Byte      |
| short     | Short     |
| int       | Integer   |
| long      | Long      |
| float     | Float     |
| double    | Double    |
| char      | Character |
| boolean   | Boolean   |

---

### Example: Collections
```java
List<int> myList = new ArrayList<>();     // ERROR: primitives not allowed
List<Integer> myList = new ArrayList<>(); // Works: Integer is an object
```

### Example: Utility Methods
```java
int x = 42;
System.out.println(x.toString()); // ERROR: int has no methods

Integer y = 42;
System.out.println(y.toStr


Primitive Type Casting
As part of Java's mutability, type casting allows you to 

