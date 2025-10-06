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

### ✅ Rule of Thumb
If a problem involves:
- **Frequencies**
- **Duplicates**
- **Comparing elements or lists**

👉 **Think HashMap (Frequency Map)** first.  
It’s one of the most versatile patterns in problem solving.
