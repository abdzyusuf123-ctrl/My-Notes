# Stacks

A **stack** is a **Last-In, First-Out (LIFO)** data structure — meaning the **last element added is the first one to be processed**.

## Core Operations:
```python
stack = []
# 1) Adding 'x' onto the top of stack
stack.append(x)
# 2) Removing (process) x from the stack
stack.pop(x)
```

✅ Both operations are **O(1)**.  
In Python, Stacks are **lists** so adding and removing things from the end is instant

## Other Operations:
```python
stack = []
stack.append(0, x)  # Adding x to the front of stack 
stack.pop(0)        # Removing from the front of stack
```

⚠️ These operations are **O(N)**, since adding/removing from the start of a Python list requires shifting elements.


## 🧠 Common Stack Syntax

```python
stack = []          # Create a stack
stack.append(x)     # Push x onto the stack
stack.pop()         # Pop (remove) from the stack

if stack:           # Check if stack is not empty
    top = stack[-1] # Peek at the top element
```

---

# 2 Main Patterns
Below are the two core **patterns** for using stacks effectively.


## Monotonic Stack (Rememebring Order of Data):
Used when a problem requires **tracking a sequence or timeline** — for example, when data needs to be processed in order.

**Memory**: We use it as a memory to remember (push) all the relevant data and forget (skip/pop) everything else  
**Core Logic**: For each data we encounter we use the memory to decide under specific conditions (depending on the problem) - when we should push or pop the stack

**High-Level Logic:**
```python
for element in list:
    # Core logic
    while stack and (specific condition based on problem):
        process(stack[-1])   # Process top of stack when condition met
        stack.pop()

    # Memory
    if not stack:
        stack.append(element)
```
🧠 **Key Idea:**  
The Monotonic Stack can process **multiple elements at once** — that’s why it uses a **while loop**.

---

## Pattern Stack (Using a stack to track patterns)
Used when a problem requires **temporarily storing data** until its **matching or completing pair** is encountered.

**Memory**: We use it as a memory to remember (**push**) unprocessed data and remove (**pop**) when we find its pair (which is based on the problem's condition)  
**Core Logic**: For each data we encounter we use the memory to decide if we should remove (**pop**) the unprocessed data as we found its match (**the current data**) or add (**push**) the current data as we need to find its matching pair

**High-Level Logic:**
```python
for element in list:
    # Core logic
    if stack and (current element completes a pattern):
        process(stack[-1])   # Handle matched pair
        stack.pop()
    else:
        stack.append(element)  # Store unmatched data
```
🧠 **Key Idea:**  
The Pattern Stack processes **one element at a time** — hence, **no while loop** is needed.

---

## 🧩 Conclusion

Use a **stack** whenever a problem requires you to **temporarily store data** that will be **resolved, matched, or completed later**.  

---

