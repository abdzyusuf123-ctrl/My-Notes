# Java vs Scala Syntax

This file outlines the **day-to-day syntax differences** between **Scala** and **Java**.  

> 🧠 **Note:**  
> Scala is primarily an **evaluation-heavy** language, while Java is **statement-heavy**.  
> - **Statements** are instructions to be executed.  
> - **Evaluations** compute expressions into a single final value.

---

## 🧩 Variables & Type Inference

### Scala
```scala
val name = "John" // immutable
var age = 30      // mutable
```

### Java
```java
final String name = "John"; // immutable
int age = 30;               // mutable
```

**Key Difference:**  
Scala’s `val` is automatically immutable, whereas Java requires the `final` keyword for immutability.

---

## 🔁 Conditionals and Loops

### If / Else Statements

#### Scala
```scala
val x = 10
val result = if (x > 5) "big" else "small"
```

#### Java
```java
final int x = 10;
String result;

if (x > 5) {
    result = "big";
} else {
    result = "small";
}
```

**Key Difference:**  
- In **Scala**, `if/else` is an **expression** that evaluates to a value (`"big"` or `"small"`).  
- In **Java**, `if/else` is a **statement** that executes instructions (`assign result = ...`).  

---

### For Loops

#### Java
```java
List<Integer> nums = List.of(1, 2, 3, 4, 5);
int sum = 0;

for (int i = 0; i < nums.size(); i++) {
    sum += nums.get(i);
}

System.out.println(sum); // 15
```

#### Scala
```scala
val nums = List(1, 2, 3, 4, 5)
val sum = nums.sum
println(sum) // 15
```

---

### While Loops

#### Java
```java
int i = 0;
int total = 0;

while (i < nums.size()) {
    total += nums.get(i);
    i++;
}

System.out.println(total); // 15
```

#### Scala
```scala
val nums = List(1, 2, 3, 4, 5)
val sum = nums.sum
println(sum) // 15
```

**Key Difference:**  
- In **Java**, loops execute instructions repeatedly, updating variables manually.  
- In **Scala**, higher-order functions (like `.sum`, `.map`, `.filter`) handle iteration internally and return results.

---

## ⚙️ Functions

### Basic Function Definition

#### Java
```java
public int add(int a, int b) {
    return a + b; // Instructs the program to return the result of a + b
}
```

#### Scala
```scala
def add(a: Int, b: Int): Int = a + b // Computes the result a + b
```

**Key Difference:**  
- In **Java**, function logic is a **series of statements** — you execute and return.  
- In **Scala**, the function body is an **expression** — you compute and return.

---

### Multi-Line Function Definition

#### Java
```java
public int add(int a, int b) {
    int result = a + b;
    System.out.println("The result is: " + result);
    return result; // must be specified
}
```

#### Scala
```scala
def add(a: Int, b: Int): Int = {
    val result = a + b
    println(s"The result is: $result")
    result
}
```

**Key Difference:**  
- In **Java**, you must **explicitly specify** what to return.  
- In **Scala**, the **final expression** in the block is automatically evaluated and returned.
