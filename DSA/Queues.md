# Queues

A **queue** is a data structure that adds items to the back and processes items at the front (**First-In, First-Out**).

In other words, queues are used to process items in the order in which they were found.

---

## Core Queue Operations

A queue supports four basic operations:

| Operation     | Meaning                     |
|---------------|-----------------------------|
| `enqueue(x)`  | Add `x` to the back         |
| `dequeue()`   | Remove from the front       |
| `peek()`      | Look at the front item      |
| `is_empty()`  | Check if the queue is empty |

All operations run in **O(1)** time.

---

## Expiration Queues

An **expiration queue** is a queue that only adds or removes elements under a specific condition.  
All elements in the queue must satisfy a **window constraint** (time, index, etc.).

### How It Works
- At the start of an iteration, process an element
- Unconditionally add the element to the queue
- While the global condition of the queue is false:
  - Remove the oldest element from the queue
  - Update the conditional summary (based on the problem)
- Once complete, the queue is valid again

### Python Syntax
```python
for n in nums:
    q.enqueue(n)
    while global_condition == False:
        q.popleft()
```

---

## BFS Queue

**Breadth-First Search (BFS)** is a traversal technique that explores tree or graph nodes **level by level** using a queue.

### How It Works
- At the start of an iteration, take the size of the queue  
  (this size represents the number of nodes at the current level)
- For exactly that many iterations:
  - Dequeue one node
  - Immediately enqueue its children or neighbors
- When the loop finishes:
  - The current level has been fully processed

### Python Syntax
```python
while q:
    level_size = len(q)
    for _ in range(level_size):
        node = q.popleft()  # dequeue current level node
        for child in node.children:
            q.append(child)
```
