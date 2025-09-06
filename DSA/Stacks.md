# 📚 Stack Interview Notes

## 🔹 What is a Stack?
- A **stack** is a linear data structure that follows **LIFO (Last In, First Out)** order.
- **Core operations:**
  - `push(x)` → insert element `x` at the top.
  - `pop()` → remove and return the top element.
  - `peek()` → return the top element without removing it.
  - `isEmpty()` → check if the stack has no elements.

✅ **Time complexity (array or linked list implementation):**  
- Push: `O(1)`  
- Pop: `O(1)`  
- Peek: `O(1)`  
- IsEmpty: `O(1)`

---

## 🔹 Two Main Stack Patterns

### 1. **Monotonic Stack**
- A stack that maintains elements in either **increasing** or **decreasing** order.
- Typically used when you need to find **next/previous greater/smaller** elements.
👉 **When to use:**  
- The problem asks about **nearest element to the left/right** that is greater/smaller.  
- You need to **maintain order** while efficiently discarding irrelevant elements.  
- You’re asked for something like “for each element, find the next ___”.

---

### 2. **Classic Matching / Tracking Stack**
- A stack used to **track state/history** or **match pairs**.
- Often involves **pushing when you see an opening condition** and **popping when you see a closing condition**.

👉 **When to use:**  
- The problem involves **nested or paired structures** (brackets, tags, recursive calls).  
- You need to **reverse order** or keep track of **previous states**.  
- There’s a natural **“open → close” matching rule**.

---

## 🔹 Order of processing in a Stack

### When processing (pushing) each element in a stack:
1. **Left to Right** (Normal) processing:
    When you are focusing on the elements that come after the current one you are at

2. **Right to Left** (Reverse) processing:
  When you are focusing on the elements that come before the current one you are at

---

## 🔹 Core Operation of Stacks in LeetCode Problems

At their heart, most stack problems boil down to **pushing elements until a condition breaks, then popping until the condition is restored**.

### The General Recipe:
1. **Iterate** through the input (array, string, expression).
2. **Push** items (index, value, or state) onto the stack as long as they "fit" the invariant.
3. **Pop** from the stack when:
   - A condition is violated (e.g., new element is greater/smaller, or closing bracket appears).
   - You’ve completed a match (e.g., valid parentheses).
4. **Use the popped item(s)** to compute results (e.g., distances, areas, matches, evaluations).
5. Continue until the input is processed.
