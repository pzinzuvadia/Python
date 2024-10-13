
# The Captain's Room

## Question

You are given a list of room numbers where some room numbers are repeated and one room number (the captain's room) appears only once. Write a Python program to find the captain's room number.

### Input Format

- The first line contains an integer `n`, the size of each group.
- The second line contains the room numbers of all the groups' members and the captain.

### Output Format

- Print the room number of the captain.

### Example

**Input:**

```
5
1 2 3 6 4 5 2 3 6 4 5
```

**Output:**

```
1
```

---

## Solution

```python
n = int(input())
s = list(map(int, input().split()))
dict1 = {}
for i in s:
    if i in dict1:
        dict1[i] += 1
    else:
        dict1[i] = 1
for i in dict1.items():
    if i[1] == 1:
        print(i[0])
```

## Solution Explanation

- The program first reads the room numbers and stores the count of each room number in a dictionary.
- It then checks which room number appears exactly once (the captain's room) and prints it.
