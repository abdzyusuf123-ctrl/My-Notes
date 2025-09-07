# Python Stack: Concise Syntax Cheatsheet

A fast refresher for LeetCode-style stack problems. Copy-paste directly into GitHub.

---

## Core ops (list-backed)

```python
stack = []          # create
stack.append(x)     # push
x = stack.pop()     # pop (O(1))
top = stack[-1]     # peek (requires non-empty)
if not stack: ...   # empty?
stack.clear()       # wipe
```

**Safe guard for pop/peek**

```python
while stack and condition_using(stack[-1]):
    stack.pop()
```

(Using `stack and ...` avoids `IndexError` when the stack is empty.)

---

## Looping (index + value)

```python
# Left -> Right
for i, v in enumerate(arr):
    ...

# Right -> Left (no copying)
for i in range(len(arr) - 1, -1, -1):
    v = arr[i]
    ...
```

`enumerate(arr)` yields `(index, value)`; you choose the variable names.

---

## What to store

* **Indices** (need distances/lookups): `stack.append(i)`
* **Values** (only compares): `stack.append(v)`
* **Tuples** (extra state): `stack.append((v, meta))`

---

## Monotonic stack patterns

**Next greater to the right (strict)**

```python
# keep arr[stack] decreasing
while stack and arr[i] > arr[stack[-1]]:
    j = stack.pop()
    # resolve j with i
stack.append(i)
```

**Greater-or-equal variant**

```python
while stack and arr[i] >= arr[stack[-1]]:
    ...
```

**Direction**

* Next to the **right** -> scan **left -> right**
* Next to the **left** -> scan **right -> left**

---

## Defaults & leftovers

```python
n = len(arr)
res = [0] * n      # or [-1] * n depending on the problem
# Usually no cleanup needed; leftovers keep the default.
```

---

## Sentinel trick (force final flush)

```python
arr.append(-float('inf'))  # or 0 for histogram heights
```

---

## When to use `while` vs single pop

* Use **`while`** when one incoming item can resolve **multiple** stack tops (monotonic stacks).
* Use a **single pop** for one-to-one matches (e.g., valid parentheses).


---

## Common pitfalls -> fixes

* Forgetting the empty guard -> use `while stack and ...`
* Wrong comparator -> choose `>` vs `>=` to match the problem
* Storing values when you need distances -> store **indices**
* Reverse scan with copying -> use `range(len(arr) - 1, -1, -1)` (avoid reversing lists)

---

**Rule of thumb:** when the prompt says “for each element, find the next \_\_\_,” reach for a **monotonic stack**; pick the direction and comparator, store **indices**, and use a **`while`** pop loop.
