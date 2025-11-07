Basics of Coding Intervies
This file contains all the useful tricks/fundamentals of solving coding interviews

Loops
Both While and For Loops act as the gateway of solving a problem, we provide our core logic withn and they are repeated until the desired output is met

For Loops
We typically use a for loop for when we are going over an array

Here are a the 3 main variations:
nums = [1,2,3,4,5]
1) for n in nums: - This is when we need to read the data in the array for some computation and NOT than changing the array
2) for i in range(len(nums)): - This is when we want to change the data in the array and NOT just read the data
3) for i, n in enumerate(nums): - This is when you want to change the data in the array BUT you can automatically get the data as well
4) for x, y in zip(array1, array2) - This is when we want to read the data of 2 arrays at the same time


While Loops
We typically use a While Loop for when a condition is true

While <condition>: 

Tracking State:
We typically create variables that are responsible for tracking any change within each iteration of our for/while loops

Counting Variables:
count = 0
for n in nums:
    if n > 10:
        count += 1
Used to count how many times a condition is true

Running Sum Variable:
running_sum = 0
for n in nums:
  running_sum += nums
Used to keep track of the total sum at of each element at every iteration

Min/Max Tracking Variable
min-val = float('inf')
max_val = float('inf')
for n in nums:
  min_val = min(min_val, n)
  max_val = max(max_val, n)
This allows you to keep track of the smallest or larget number encountered at every iteration

