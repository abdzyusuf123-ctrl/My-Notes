# Two Pointers

---

## What Are Two Pointers?

Two Pointers is an algorithm that uses **two variables** (which are indexes or references to elements) to iterate through an input list.

Two Pointers typically:
- Start at a specific position (depending on the problem)
- Move based on a specific condition (depending on the problem)
- Help us make decisions during iteration (depending on the problem)

---

## Opposite Direction Two Pointers

This is a pattern where:
- The **left pointer** starts at the first element’s index
- The **right pointer** starts at the last element’s index

### Logic
- The left pointer starts at the beginning
- The right pointer starts at the end
- At each iteration, pointers are moved based on a condition  
  - Left pointer is incremented  
  - Right pointer is decremented
- Repeat until the pointers meet or the left pointer moves past the right pointer

### Python Syntax
```python
s = list("reverse")
l = 0
r = len(s) - 1

while l <= r:
    s[l], s[r] = s[r], s[l]
    r -= 1
    l += 1
```

### When Is It Useful?
- When you have a **sorted list**
- When you need to **compare elements from both ends**
- Common use cases: reversing arrays, palindrome checks, pair comparisons

---

## Same Direction Two Pointers

This is a pattern where:
- Both pointers start at the **same direction**
- The list is processed primarily using the **right pointer**
- The active range is between the left and right pointers

### Logic
- The left pointer starts at the beginning
- The right pointer starts at the beginning
- At each iteration:
  - The right pointer moves forward
  - Based on a condition, the left pointer may move
- Repeat until the right pointer reaches the end of the list

### Python Syntax
```python
nums = [1, 2, 3, 4]
l = 0

for r in range(len(nums)):
    print(nums[l : r + 1])
```

### When Is It Useful?
- When you need to **track a range or window** in a list
- Common use cases: sliding window problems, subarray tracking



