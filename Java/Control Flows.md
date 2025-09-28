# Control Flows in Java

Control flows determine **which statements are executed in a program**.  

They allow you to:  
- **Decide** which statements to execute: `if`, `else if`, `else`, `switch`.  
- **Repeat** certain actions until a condition is met (or input runs out): `while`, `for`, `do-while`.  

This gives you the ability to **control how your program behaves** depending on the data you are working with.  

---

## Control Flows and Java's Statement/Expression Methodology

- Control flows are **statements** themselves.  
- They contain an **expression**, which is always evaluated to `true` or `false`.  
- The result of that expression decides if the control flow executes.  

---

## Operators

Operators are the tools that allow you to create expressions (which evaluate to a value) inside control flows:  

- **Arithmetic**: `+`, `-`, `*`, `/`, `%`  
- **Relational**: `<`, `>`, `<=`, `>=`, `==`, `!=`  
- **Logical**: `&&`, `||`, `!`  
- **Assignment**: `=`, `+=`, `-=`, `*=`, `/=`  
- **Increment/Decrement**: `++`, `--`  

**Flow:**  
```
Operators → Expressions → Boolean → Control Flow Execution
```

### Example
```java
if (x + 4) { 
    System.out.println(x); 
} 
// ERROR - condition does not evaluate to boolean

if (x + 4 > 10) { 
    System.out.println(x); 
} 
// Works - condition evaluates to boolean
```

Even loop conditions are just boolean expressions:  

```java
for (int i = 0; i < myList.size(); i++) {
    System.out.println(i);
}
```

---

## If / Else If / Else Statements

These are the most basic control flows. They allow you to decide which statement to execute based on conditions.  

```java
int x = 20;

if (x < 10) { 
    System.out.println(x + " is less than 10"); 
}
else if (x > 10) {
    System.out.println(x + " is greater than 10"); 
}
else {
    System.out.println("Error");
}
```

---

## Loop Statements

Java provides **three main loop statements**: `for`, `while`, and `do-while`.

### 1. For Loops
Used when you **know how many times** to process something.  

Syntax:
```java
for (initialization; condition; update) {
    // body
}
```

Example (counting 1–10):
```java
for (int i = 0; i < 10; i++) {
    System.out.println(i);
}
```

---

### 2. While Loops
Used when you **don’t know how many times** to process something. Runs until the condition becomes false.  

Example (roll a die until a 6 is rolled):
```java
Random rand = new Random();
int x = 0;

while (x != 6) {
    x = rand.nextInt(6) + 1;
    System.out.println("Rolled: " + x);
}

System.out.println("Got a 6! Stopping.");
```

---

### 3. Do-While Loops
Like a `while` loop, but the body executes **at least once**, even if the condition is false.  

Syntax:
```java
do {
    // body
} while (condition);
```

Example:
```java
int x = 0;

do {
    System.out.println(x);
    x++;
} while (x < 5);

System.out.println("done");
```

💡 Note: The statements inside the `do` block execute at least once before the condition is checked.  

---

## Switch Statements

Switch statements are similar to Scala’s pattern matching and provide an alternative to many `if/else if` chains.  

Syntax:
```java
switch (variable) {
    case value1: 
        // statement
        break;
    case value2: 
        // statement
        break;
    default:
        // fallback statement
}
```

Example:
```java
int dayOfWeek = 2;

switch (dayOfWeek) {
    case 1: 
        System.out.println("Monday"); 
        break;
    case 2: 
        System.out.println("Tuesday"); 
        break;
    case 3: 
        System.out.println("Wednesday"); 
        break;
    default: 
        System.out.println("Some Other Day");
}
// Output: Tuesday
```

⚠️ **Important:**  
- Use `break;` to stop execution after a case is matched.  
- Without `break`, the JVM will continue executing the next cases (called **fall-through**).  
- The `default` case does not require `break` (but you can include it for consistency).  
