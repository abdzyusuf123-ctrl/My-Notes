# Arrays

---

## What Are They?
Arrays are **collections of elements stored at continuous memory locations** (the elements are right next to each other).  

👉 In Python, we use **lists** as dynamic arrays for flexibility.  

---

## What Are Dynamic Arrays?
Dynamic arrays are a flexible kind of array that can **grow or shrink in size automatically**.  

- Under the hood (in Python), when the array is near capacity, memory is **doubled** and the array is migrated.  

---

## Key Properties

- **Index-based access**:  
  Access specific elements in **constant time** `O(1)`.  
  ```python
  arr = [1, 2, 3, 4, 5]
  print(arr[2])  # 3
  ```

- **Dynamic**:  
  Python lists can **grow or shrink automatically**.

- **Continuous**:  
  Elements are stored **back-to-back** in memory → enabling `O(1)` access.  
  ❌ But inserting or deleting in the middle requires shifting elements → `O(N)`.  

💡 **Rule of Thumb #1:**  
If you need **fast random access by index** → use an array (in Python, a list).  

---

## Array Operations

| Operation                     | Example                 | Time Complexity |
|--------------------------------|-------------------------|-----------------|
| Access by index                | `arr[i]`               | `O(1)` |
| Update by index                | `arr[i] = x`           | `O(1)` |
| Add element at the end         | `arr.append(x)`        | `O(1)` |
| Insert at a random index       | `arr.insert(i, x)`     | `O(N)` |
| Delete at a random index       | `del arr[i]`           | `O(N)` |
| Traverse the array             | `for x in arr:`        | `O(N)` |

💡 **Rule of Thumb #2:**  
Arrays are **great for fast access & updates**, but not for frequent insertions/deletions in the middle.  

---

## Array Traversals

Traversal = one of the **most important array skills** in DSA interviews.  

### 1. Index-Based Traversal
Use when you need the **index** (best for modifying the array).  
```python
for i in range(len(arr)):
    print(i, arr[i])
```

### 2. Element-Based Traversal
Use when you only need the **elements** (best for reading the array).  
```python
for n in arr:
    print(n)
```

### 3. Index + Element Traversal
Use when you need **both index and element**.  
```python
for i, n in enumerate(arr):
    print(i, "and", n)
```

✅ All three traversal methods are **O(N)**.  

💡 **Rule of Thumb #3:**  
Always ask: *Do I need the index, the value, or both?*  
That decides which traversal pattern to use.  

---

## Common Traversal Variants (Interview-Focused)

- **Running sum / average**  
  → Keep an accumulator, update as you traverse.  

- **Finding max/min**  
  → Initialize with `arr[0]` or use `float("inf") / float("-inf")`.  

- **Counting elements with a condition**  
  → Use a counter starting at `0`, update based on conditions.  

- **Transforming the array in-place**  
  → Use index-based traversals.  

💡 **Rule of Thumb #4:**  
Traversal + simple aggregation (sum, max, count) is one of the most common **interview warm-ups**.  
