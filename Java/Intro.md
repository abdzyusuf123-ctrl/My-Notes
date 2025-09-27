# Java Notes

Java is an **Object-Oriented Programming (OOP)** based language that also contains some **Functional Programming paradigms** (Java 11+).  

When Java programs are compiled, they are turned into **JVM Bytecode** to be executed.  

**Path of execution:**
```
.java source -> compiled to .class bytecode -> executed by the JVM
```

---

## Expressions and Statements

- A **Statement** is an instruction executed by the JVM.  
- An **Expression** is something that is evaluated to a value.  

Unlike Scala (where everything is an expression due to immutability), in Java things can be **expressions** and **statements** since we can re-assign data to variables.

### Example
```java
String message;
if (x > 4) {
    message = "Expression wrapped in Statement!";
}
```

- `x > 4` → this is an **Expression** (evaluates to a boolean).  
- `message = "Expression wrapped in Statement!";` → this is a **Statement** (a command telling the JVM to assign a value).  

---

### Key Idea

- **Statements** are commands or steps for the JVM to execute.  
- **Expressions** are potential values that can be computed.  

---

### How They Work Together

Statements are often used to execute the potential values computed from expressions.  

---

### Conclusion

In Java, **Statements and Expressions exist and work together** as we constantly change state and data between variables.  

---

## Values and Variables

In Java, the default approach for variables is to be **mutable** unless specified otherwise.

### Mutable Variables
Regular variables are mutable and can be reassigned.  
(Similar to Scala’s `var`)

```java
String x;
x = "Hello";
x = "World"; // valid reassignment
```

### Immutable Variables
Immutable variables are declared with the `final` keyword and **cannot** be reassigned.  
(Similar to Scala’s `val`)

```java
final String x = "Hello";
x = "World"; // ERROR - cannot reassign a final variable
```
