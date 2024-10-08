
# Collections.Counter()

## Question

You are given a list of shoe sizes in a store and a number of customer purchase requests. For each purchase, the customer requests a specific shoe size and is willing to pay a certain amount of money. Write a Python program to determine how much money the store earns by fulfilling the customer requests.

### Input Format

- The first line contains an integer `x`, the number of shoes.
- The second line contains the list of `x` space-separated integers, representing the available shoe sizes in the store.
- The third line contains an integer `n`, the number of customers.
- The next `n` lines contain two space-separated integers, representing the shoe size and price the customer is willing to pay.

### Output Format

- Output the total amount of money earned by fulfilling the customer requests.

### Example

**Input:**

```
10
2 3 4 5 6 8 7 6 5 18
6
6 55
6 45
6 55
4 40
18 60
10 50
```

**Output:**

```
200
```

---

## Solution

```python
x = int(input())
sizes = list(map(int, input().split()))
dict1 = {}
sales = 0
for s in sizes:
    if s in dict1:
        dict1[s] += 1
    else:
        dict1[s] = 1
for c in range(int(input())):
    size, amt = map(int, input().split())
    if size in dict1 and dict1[size] > 0:
        sales += amt
        dict1[size] -= 1
print(sales)
```

## Solution Explanation

- The program first reads the available shoe sizes and stores them in a dictionary `dict1`, where the keys are shoe sizes and the values are the number of shoes available in each size.
- For each customer request, the program checks if the requested shoe size is available and, if so, reduces the available stock for that size and adds the amount the customer is willing to pay to the total sales.
- The program outputs the total sales at the end.
