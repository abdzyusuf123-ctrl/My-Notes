# Heaps

A **heap** is a data structure that allows you to retrieve the **smallest** element (min-heap) or the **largest** element (max-heap).

A heap achieves this by maintaining a **parent–child relationship** such that:
- In a **min-heap**, the parent node is less than its child nodes
- In a **max-heap**, the parent node is greater than its child nodes

This structure is what makes retrieval **instant**.

---

## How Does It Look?

A heap does not actually look like a tree in memory.  
Instead, it is stored as an array, for example:

```text
[1, 3, 5, 8, 4, 7]
```

This array can be interpreted as a binary tree:

```
        1        (index 0)
      /   \
     3     5     (1, 2)
    / \   /
   8   4 7       (3, 4, 5)
```

---

## Core Operations

| Operation | Meaning         | Time     |
|----------|------------------|----------|
| push     | Add element      | O(log n) |
| pop      | Remove min/max   | O(log n) |
| peek     | Look at min/max  | O(1)     |

---

## Main Pattern: Top K Elements

The main pattern for heaps is retrieving the **top K smallest or largest elements** efficiently.

---

### Python Syntax (Top K Largest Using Min-Heap)

```python
import heapq

heap = []

for x in nums:
    heapq.heappush(heap, x)
    if len(heap) > k:
        heapq.heappop(heap)
```

---

## After All Iterations

- The heap contains the **K largest elements**
- The root of the heap is the **Kth largest** element
- This approach uses a **min-heap**

This same pattern also applies to **min-heap problems** where you want the **K smallest elements**.
