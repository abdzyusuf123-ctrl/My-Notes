HashMap
It is a data structure that allows you:
- Store Key Value pairs
- Allows you to instantly look up each value based on its key O(1)

Python's tricks:
In Python, hashmaps are known as dictionaries:
// Create a hashmap (dictionary)
student = { "name": "Alice", "age": 22, "grade": "A" }

/Adding a new key to the hashmap
hashmap = {}
x = "I am a key X!"
message = "I am a value!"
hashmap[x] = message
hashmap = {"I am a key X!" : "I am a value!"}

//Checking if something is in the hashmap already
y = "I am a key Y!"
x = "I am a key X!"
if y not in hashmap:
  hashmap[y] = "I am a value!"
hashmap = {"I am a key X!" : "I am a value!",  "I am a key Y!": "I am a value!" }

Shortcut Methods
Python gives you a few handy tools for this:

1️⃣ .get() — returns a default if the key doesn’t exist
hashmap[key] = hashmap.get(key, 0) + 1

2️⃣ defaultdict(int) — automatically handles missing keys
from collections import defaultdict
hashmap = defaultdict(int)
for n in nums:
    hashmap[n] += 1

2 Main Patterns:
Frequency Map
You count the occurance of something in a list and store it as the key and how often it comes up is the value
It is very useful and efficient for when a problem requires you to keep track of how often something comes up

Example Use Case (count how many times each number comes up in nums):
hashmap = {}
nums = [1,1,2,2,2,3,4,4]
for n in nums:
    if n not in hashmap:
        hashmap[n] = 1
    else:
        hashmap[n] += 1
print(hashmap) //Will give us: {1: 2, 2: 3, 3: 1, 4: 2}
This is much more efficient O(1) then going through each number in the list and counting then restarting again for every number O(N)

✅ Rule of Thumb
If the question talks about frequency, duplicates, or comparing lists - your first thought should be hashmap (frequency map)




