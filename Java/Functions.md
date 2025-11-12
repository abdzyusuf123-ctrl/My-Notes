# Functions

In Java, a **function** (also called a *method*) is a block of code used to **execute specific instructions** to compute or modify something.  
All functions **must live inside a class**.

---

## 🧩 Basic Function Definition

```java
public int add(int a, int b) {
    return a + b;
}
```

**Breakdown:**
- `public` → Access modifier (defines who can access the function).  
- `int` → Return type of the function (similar to `: Int` in Scala).  
- `add` → Function name.  
- `(int a, int b)` → Parameter list (variables passed into the function).  
- `{ }` → Function body (contains the instructions to execute).  

---

## 🔍 Function Signature

A **function signature** allows the JVM to identify and execute a specific function.  
It includes the **method name** and **parameter types**:  

```
methodName(parameterType)
```

This helps the JVM find the correct function when it’s called — even if the argument variable names are different.

**Example:**
```java
public int add(int a, int b) {
    return a + b;
}

// Function call:
add(myNumber, myNumber2);
```

Even though the parameters have different names, the types match — allowing proper execution.  

You can also **store the returned result**:
```java
int result = add(myNumber, myNumber2);
```

---

## 🎯 Return Type

Since Java functions are **statement-oriented**, each function may or may not compute a value.  
You must **explicitly declare what type of data** your function returns.

**Example:**
```java
public int add(int a, int b) {
    return a + b;
}
```

Because we declared `public int`, the function **must return an integer**.  
When called, the computed result (`a + b`) can be reused anywhere.

> 🧠 Note:
> - Every path in the function must return a value of the declared type.  
> - If a function returns **nothing**, use the `void` keyword (similar to Scala’s `Unit`).  

---

## 🏗️ Constructor Functions

In Java, **all functions live inside classes**.  
**Constructor functions** are special methods used to **create new objects** and **initialize their fields**.  

**Example:**
```java
public class Person {
    String name;
    int age;

    public Person(String name, int age) {
        this.name = name; // Assign constructor parameter to the instance variable
        this.age = age;
    }
}

Person david = new Person("David", 30);
```

**Notes:**
- Constructors **don’t have return types**.  
- They run **once per object creation**.  
- The JVM allocates **new memory** for each object when you use the `new` keyword.

---

## ⚙️ Static vs Instance Functions

All Java functions are either **static** or **instance-based**, since they must belong to a class.

---

### 🧮 Static Functions

These functions **belong to the class itself** and can be called without creating an object.

**Example:**
```java
public class MathUtils {
    public static int add(int a, int b) {
        return a + b;
    }
}

// Access without creating an instance
int result = MathUtils.add(myNumber, myNumber2);
```

---

### 👤 Instance Functions

These functions **belong to a specific object** of a class.  
Their behavior depends on the object they are called from.

**Example:**
```java
public class Person {
    String name;
    double balance;

    public Person(String name, double initialBalance) {
        this.name = name;
        balance = initialBalance;
    }

    public void deposit(double amount) { // Instance-based function
        balance += amount;
        System.out.println("Balance: " + balance);
    }
}

Person john = new Person("John", 200);
Person david = new Person("David", 300);

john.deposit(100);  // Balance: 300
david.deposit(400); // Balance: 700
```

The printed result **changes based on the object**, proving that instance-based functions behave differently depending on instance state.

---

## 🔑 Key Differences: Static vs Instance

| Type              | Belongs To | Behavior | Access Method |
|-------------------|-------------|-----------|----------------|
| **Static Function** | The class itself | Same behavior across all calls | `ClassName.method()` |
| **Instance Function** | A specific object | Behavior varies per object | `object.method()` |
