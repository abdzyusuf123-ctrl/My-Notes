# Basics of Coding Interviews

This file contains all the useful tricks and fundamentals for solving coding interviews. 

Remember:
- Loops act as the engine of our core logic that is used to solve the problem and is repeated at every iteration until we get our desired output
- Tracking States act as our memory for every iteration and allow us to pass data from one iteration to another

---

## 🔁 Loops

Both **while** and **for** loops act as the gateway to solving a problem.  
They execute your core logic repeatedly until the desired output is achieved.

---

## 🧮 For Loops

We typically use a `for` loop when we are iterating over an array.

**Main Variations:**

```python
nums = [1, 2, 3, 4, 5]

# 1) Read-only access
for n in nums:
    # Use this when reading data from the array without modifying it
    print(n)

# 2) Index-based access
for i in range(len(nums)):
    # Use this when modifying data in the array
    nums[i] *= 2

# 3) Index and element access
for i, n in enumerate(nums):
    # Use this when you need both index and value
    print(i, n)

# 4) Parallel iteration over two arrays
for x, y in zip(array1, array2):
    # Use this when reading from two arrays simultaneously
    print(x, y)
```

---

## 🔄 While Loops

We typically use a `while` loop when we need to **repeat actions while a condition is true**.

```python
while <condition>:
    # Execute code while condition is True
    ...
```

---

## 🧭 Tracking State

We often create **state variables** to track changes within each iteration of a loop.

### Counting Variable
```python
count = 0
for n in nums:
    if n > 10:
        count += 1
```
Used to count how many times a condition is true.

---

### Running Sum Variable
```python
running_sum = 0
for n in nums:
    running_sum += n
```
Used to keep track of the total sum of elements during each iteration.

---

### Min/Max Tracking Variable
```python
min_val = float('inf')
max_val = float('-inf')

for n in nums:
    min_val = min(min_val, n)
    max_val = max(max_val, n)
```
Used to track the smallest or largest number encountered during iteration.

---


