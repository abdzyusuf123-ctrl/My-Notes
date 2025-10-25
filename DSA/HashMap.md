# HashMap

---

## What Is a HashMap?

A **HashMap** is a data structure that allows you to:  
- Store **key–value pairs**.  
- Instantly **look up values by key** in **O(1)** average time complexity.

In Python, a **dictionary (`dict`)** serves as a HashMap.

---

## Python Syntax

### Create / Update a HashMap
```python
# Create a hashmap
hashmap = {}

# Insert a key/value pair
hashmap['a'] = 1   # {'a': 1}

# Increment the value of an existing key
hashmap['a'] += 1  # {'a': 2}

# Retrieve a value safely (with default if key not found)
value = hashmap.get('a', 0)
```

---

### Loop Through a HashMap
```python
hashmap = {'a': 2, 'b': 3, 'c': 1}

# Loop through keys
for k in hashmap.keys():
    print(k)

# Loop through values
for v in hashmap.values():
    print(v)

# Loop through key-value pairs
for k, v in hashmap.items():
    print(k, v)
```

✅ **LeetCode Use Cases**
- Comparing two frequency maps (`for k, v in hashmap.items():`)  
- Summing values or finding maximum frequency  

---

## Default Dictionary (Cleaner HashMap Pattern)

The `defaultdict` from Python’s `collections` module provides a **default value** for missing keys — perfect for counting or grouping tasks.

```python
from collections import defaultdict

freq = defaultdict(int)

for ch in "banana":
    freq[ch] += 1   # No need to check if key exists!

print(freq)  # {'b': 1, 'a': 3, 'n': 2}
```

✅ **LeetCode Use Cases**
- **Grouping anagrams:** `grouped[sorted_word].append(word)`  
- **Building adjacency lists** in graph problems  

---

## 2 Main Patterns

### 1. Frequency Map
Use a HashMap to **count occurrences** of elements.  
Each unique item is a **key**, and its frequency is the **value**.  

**Why it’s useful:**  
Efficiently tracks counts without rescanning the list — `O(N)` total vs. `O(N²)` if you re-count manually.

Example:
```python
hashmap = {}
nums = [1, 1, 2, 2, 2, 3, 4, 4]

for n in nums:
    if n not in hashmap:
        hashmap[n] = 1
    else:
        hashmap[n] += 1

print(hashmap)
# Output: {1: 2, 2: 3, 3: 1, 4: 2}
```

This is much more efficient than repeatedly calling `list.count()` for every element.

---
### 2. Lookup Map

A **Lookup Map** uses a HashMap to connect **one type of information to another**.  

- **Key:** The element you are iterating over.  
- **Value:** The condition, index, or piece of data you want to return or reference later.  

---

### Why Is It Useful?

It allows your code to **remember information from earlier steps** and **reuse it instantly** — without rescanning the input every time.  
This pattern is extremely common in problems involving lookups, complements, or pair matching.

---

### Example (Two-Sum Problem)
```python
nums = [2, 7, 11, 15]
target = 9
hashmap = {}

for i, n in enumerate(nums):
    complement = target - n
    if complement in hashmap:             # 👈 Lookup check
        print([hashmap[complement], i])   # Output: [0, 1]
        break
    hashmap[n] = i                         # 👈 Store number → index
```

---

### ✅ Rule of Thumb — Lookup Map Pattern

If a problem involves:
- **Finding a match, pair, or complement**
- **Tracking where something was last seen**
- **Mapping one thing to another** (e.g., letter → word, index → value)
- **Checking relationships or constraints between elements**

👉 **Think HashMap (Lookup Map)**  

It’s your **go-to pattern** whenever you need to remember past information to make a constant-time decision later — instead of looping again.  
