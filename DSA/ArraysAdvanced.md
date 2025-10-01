# Arrays Advanced

---

## Prefix Sum Array

### The Problem
Imagine needing to calculate the sum of specific ranges in an array **thousands of times**.  

Example:
```python
nums = [2, 4, 6, 8, 10]
# Sum from index 1 to 3 → 4 + 6 + 8 = 18
```

You could loop through each range and sum values — but for **large arrays** and **many queries** (e.g., 1–50, 2–23, 5–49), this becomes inefficient because you repeatedly calculate overlapping sums.  

---

### The Solution: Prefix Sum Array
A **Prefix Sum Array** stores the cumulative total of elements up to each index.  

Example:
```
nums      = [2,   4,   6,   8,   10]
prefixSum = [2,   6,  12,  20,   30]
```

Step-by-step:
- `prefixSum[0] = nums[0] = 2`  
- `prefixSum[1] = nums[0] + nums[1] = 2 + 4 = 6`  
- `prefixSum[2] = nums[0] + nums[1] + nums[2] = 12`  

👉 Each entry represents the **“total so far”**.  

---

### Why Is It Useful?
- **Building** a prefix sum array takes one pass: **O(N)**.  
- **Retrieving** the sum of any subarray range is **O(1)**.  

---

### Using Pointers for Range Sum
To calculate the sum between two indexes (`l` → `r`):  

1. Set left pointer: `prefixSum[l-1]`  
2. Set right pointer: `prefixSum[r]`  
3. Subtract: `prefixSum[r] - prefixSum[l-1]`  

Example: sum between **index 1 and 3**  
```
prefixSum[3] = 20  
prefixSum[0] = 2  
Sum = 20 - 2 = 18
```

---

### ✨ Rule of Thumb
- For a range sum `l → r`, always subtract `prefixSum[l-1]`, unless `l == 0`.  
- `prefixSum[r]` contains everything up to `r`.  
- `prefixSum[l-1]` contains everything before `l`.  
- Subtracting clears out the extra part.  

---

### Building a Prefix Sum Array
Step-by-step:  

1. Start with an empty array of size `n`:  
   ```python
   prefix = [0] * len(nums)
   ```

2. Set the first element:  
   ```python
   prefix[0] = nums[0]
   ```

3. Build prefix sums with a loop:  
   ```python
   for i in range(1, len(nums)):
       prefix[i] = prefix[i-1] + nums[i]
   ```

Example:
```python
nums = [2, 4, 6, 8, 10]
prefix = [0] * len(nums)

prefix[0] = nums[0]
for i in range(1, len(nums)):
    prefix[i] = prefix[i-1] + nums[i]

print(prefix)  # [2, 6, 12, 20, 30]
```
