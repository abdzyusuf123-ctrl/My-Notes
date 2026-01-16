# Core Logic & Memory & Global Conditon for Every DS/A

Below, this file outlines how the following **Data Structures / Algorithms** (and their main patterns) use the **3 core** principles that are integral to all coding interview problems.

---

## Core Logic

Most coding interview questions will have a **core logic** (in the form of a `for` or `while` loop) that performs some computation repeatedly until the desired output for a test case is met.

The path to finding what that core logic is comes from identifying which **algorithm** to use.

---

## Memory

Most coding interview questions will also require you to keep track of some data (for instance, tracking the maximum sum), which is then updated and reused by the core logic to help produce the desired output.

The path to finding which kind of **memory** to use comes from identifying which **data structure** to use.

---

## Global Condition
Most coding interview questions will also maintain a condition that must be true at each iteration and if that condition is false after an iteration then the something is wrong with your code

It is important for every problem to:
- Know the **Global Condition**
- Identify what breaks the **Global Condition**
- Understand what is required to fix the **Global Condition**

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
For each element encountered, we use the memory to increase its frequency, and if we haven’t encountered it before, we assign it a value of `1`. - **For Loop**

**Global Conditon**  
After each iteration, in our map we should have the correct amount of frequency for each element we encountered

---

### Lookup Map

**Memory:**  
We use it to remember relationships between problem-specific patterns and elements.

**Core Logic:**  
For each element encountered, we use the map to look up its specific pattern and decide if that element meets the required condition. - **For Loop**

**Global Conditon**  
After each iteration, in our map we should have the correct pattern matching the each element we encountered

---

## Stack

### Monotonic Stack

**Memory:**  
We use it to remember (push) all relevant elements (relevant based on the problem) and forget (skip/pop) everything else.

**Core Logic:**  
For each element encountered, we use the memory to decide—under specific conditions (depending on the problem) — when to push or pop the stack. - **For Loop + Inner While Loop**

**Global Conditon**  
After each iteration, in our stack we should contain all the relevant elements (in increasing/decreasing order) and upon popping an element we should never process it again

---

### Pattern Stack

**Memory:**  
We use it to remember (push) unprocessed data and remove (pop) it when we find its matching pair (based on the problem’s condition).

**Core Logic:**  
For each element encountered, we decide whether to remove (pop) unprocessed data because its match was found (the current data), or add (push) the current data because its matching pair has not yet been found. - **For Loop**

**Global Conditon**  
After each iteration, in our stack we should contain all the relevant elements and pop only when we find its matching pair

---

## Two Pointers

### Opposite Direction Two Pointers

**Memory:**  
We use it to remember the current indexes of the two elements we are comparing.

**Core Logic:**  
While the pointers have not met, we compare both elements using the pointers and decide to move one or both pointers based on a specific condition. **While Loop**

**Global Conditon**  
After each iteration, both pointers should only be moved under specific conditions until they meet


---

### Same Direction Two Pointers

**Memory:**  
We use it to remember the current range of elements between the two pointers.

**Core Logic:**  
For each element encountered, we move the right pointer forward and only move the left pointer when a condition is met. **For Loop + Inner While Loop OR Just While Loop**

**Global Conditon**  
After each iteration, the left pointer should only be moved under specific conditions until the right pointer has reached the end of the array/string

---

## Sliding Window

### Fixed-Size Sliding Window
**Memory:**  
We use it to remember the conditional-based summary of what is currently in the window

**Core Logic:**  
For each element encountered, we move the right pointer forward and we only move the left pointer if the number of elements in the window exceeds a certain length. **For Loop**

**Global Conditon**  
After each iteration, the window should shrink only if the number of elements has exceeded the specific size and grow if it less than the specific size

---

### Variable Size Sliding Window
**Memory:**  
We use it to remember the conditional-based summary of what is currently in the window

**Core Logic:**  
For each element encountered, we move the right pointer forward and we only move the left pointer if the number of elements in the window violate a condition. **For + Inner While Loop**

**Global Conditon**  
After each iteration, the window should shrink only if the number of elements has broken a specific conditional number and grow if it less than a specific conditional number

---

## Queues

### Conditional Queues
**Memory:**  
We use it to remember all the relevant elements or summary of elements that fit the specific condition of a problem

**Core Logic:**  
For each element encountered, we add it to our queue. While the global condition of queue is false, we remove the oldest element from queue. **For + Inner While Loop**

**Global Conditon**  
After each iteration, the queue should only contain all the element/summary of elements that fit the specifc condition of a problem

---

### BFS Queues
**Memory:**  
We use it to remember all the nodes of a specific level in our tree

**Core Logic:**  
For each node in our tree, we take the size of the level (number of nodes) and we then remove all nodes in that level, we then add its child nodes into the queue **For + Inner While Loop**

**Global Conditon**  
After each iteration, the queue should only contain the nodes of the next tree level.

---

## Heaps

### Min/Max Heaps
**Memory:**  
We use it to remember all the elements and their order of smallest to largest and vice-versa

**Core Logic:**  
For each element we encounter, we push it to the heap, if the heap length is greater/less than the conditional value in the problem, we pop the element in the heap **For + Inner While Loop**

**Global Conditon**  
After each iteration, the heap should correctly store the relationships of elements in smallest to largest and vice-versa.




