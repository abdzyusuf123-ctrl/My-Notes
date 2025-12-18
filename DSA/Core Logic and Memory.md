# Core Logic and Memory for Every DS/A

Below, this file outlines how the following **Data Structures / Algorithms** (and their main patterns) use the two principles that are integral to all coding interview problems.

---

## Core Logic

Most coding interview questions will have a **core logic** (in the form of a `for` or `while` loop) that performs some computation repeatedly until the desired output for a test case is met.

The path to finding what that core logic is comes from identifying which **algorithm** to use.

---

## Memory

Most coding interview questions will also require you to keep track of some data (for instance, tracking the maximum sum), which is then updated and reused by the core logic to help produce the desired output.

The path to finding which kind of **memory** to use comes from identifying which **data structure** to use.

---

## Common Memory Tools

1) **Max/Min Counters** – A variable that stores the largest or smallest conditional value / element encountered  
2) **Counter** – A variable that tracks progress each time a condition is met or an element is found  
3) **Running Accumulators** – A variable that stores calculations at each iteration  
4) **Pointers** – A variable that stores the positions of elements  
5) **Result List** – A list that stores the final processed data and accumulates it with each iteration  

---

## Core Logic Tools

1) **For Loop** – A loop that iterates over the input list of the problem  
2) **While Loop** – A loop that iterates based on a specific condition related to the problem  

---

## HashMap

### Frequency Map

**Memory:**  
We use it to remember the occurrence of all relevant elements in a list (the element is the key and the frequency is the value).

**Core Logic:**  
For each element encountered, we use the memory to increase its frequency, and if we haven’t encountered it before, we assign it a value of `1`.

---

### Lookup Map

**Memory:**  
We use it to remember relationships between problem-specific patterns and elements.

**Core Logic:**  
For each element encountered, we use the map to look up its specific pattern and decide if that element meets the required condition.

---

## Stack

### Monotonic Stack

**Memory:**  
We use it to remember (push) all relevant elements (relevant based on the problem) and forget (skip/pop) everything else.

**Core Logic:**  
For each element encountered, we use the memory to decide—under specific conditions (depending on the problem)—when to push or pop the stack.

---

### Pattern Stack

**Memory:**  
We use it to remember (push) unprocessed data and remove (pop) it when we find its matching pair (based on the problem’s condition).

**Core Logic:**  
For each element encountered, we decide whether to remove (pop) unprocessed data because its match was found (the current data), or add (push) the current data because its matching pair has not yet been found.

---

## Two Pointers

### Opposite Direction Two Pointers

**Memory:**  
We use it to remember the current indexes of the two elements we are comparing.

**Core Logic:**  
While the pointers have not met, we compare both elements using the pointers and decide to move one or both pointers based on a specific condition.

---

### Same Direction Two Pointers

**Memory:**  
We use it to remember the current range of elements between the two pointers.

**Core Logic:**  
For each element encountered, we move the right pointer forward and only move the left pointer when a condition is met.
