# Sliding Window

Sliding Window is a variation of the **Two Pointer** technique that allows us to keep a memory of a specific conditional summary (minimum value, maximum value, minimum sum, maximum sum, etc.) within a range of elements (the window).

---

## How Is It Created?

Sliding Window is essentially the **Same-Direction Two Pointer** technique.

- Assign the left pointer to `0`
- Loop through the list using the right pointer

```python
nums = [1, 2, 3]
l = 0
for r in range(len(nums)):
    ...
```

---

## How Does It Move?

- The **right pointer** moves naturally as we loop through the list
- The **left pointer** only moves when a specific condition is met

**Pointer Movement Meaning:**
- Move left pointer → **Shrink window**
- Move right pointer → **Expand window**

---

## Why Is It Useful?

It allows us to find a **range of elements** that meet a specific condition, depending on the problem.

---

## Fixed-Size Sliding Window

The window must always contain a **fixed number of elements**, and its size never changes.  
The movement of the window is **not conditional**.

### Logic
- Move the right pointer (via a `for` loop)
- If the window size exceeds the fixed size:
  - Move the left pointer to shrink the window

### Core Formula
```text
window_size = right - left + 1
```

This formula is used at every iteration to track the window size.

### Core Code
```python
l = 0
for r in range(len(nums)):
    if r - l + 1 > k:
        # remove nums[l] from the window
        l += 1
    if r - l + 1 == k:
        # compute
        ...
```

---

## Variable-Size Sliding Window

The window does **not** have a fixed size.  
It can grow or shrink dynamically based on specific conditions.

### Logic
- Move the right pointer (via a `for` loop)
- Move the left pointer **while** the window violates a specific condition
- The left pointer may move multiple times per iteration

### Core Code
```python
l = 0
for r in range(len(nums)):
    # include nums[r] in the summary
    while # specific condition where the window violates the constraint:
        # remove nums[l] from the window
        l += 1
```

---

## Summary

Sliding Window is a key technique for solving problems where you need to evaluate **conditions within a continuous subarray or substring** of the input list.
