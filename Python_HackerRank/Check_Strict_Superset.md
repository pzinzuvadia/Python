
# Check Strict Superset

## Question

You are given a set `A` and `n` other sets. Your task is to determine whether `A` is a strict superset of all the other `n` sets. A strict superset means that `A` contains all the elements of the other set, and `A` is strictly larger than the other set (i.e., `A` cannot be equal to the other set).

Write a Python program to determine whether `A` is a strict superset of all the other sets.

### Input Format

- The first line contains the elements of set `A`, separated by spaces.
- The second line contains an integer `n`, the number of other sets.
- The next `n` lines each contain the elements of a set, separated by spaces.

### Output Format

- Print `True` if `A` is a strict superset of all the other sets; otherwise, print `False`.

### Example

**Input:**

```
1 2 3 4 5
2
1 2 3
1 2 3 4
```

**Output:**

```
False
```

---

## Solution

```python
a = set(map(int, input().split()))
n = int(input())
ret = []
for i in range(n):
    new_set = set(map(int, input().split()))
    ret.append(a.issuperset(new_set))
print(all(ret))
```

## Solution Explanation

- The program reads the set `A` and the number of other sets `n`.
- For each set, the program checks if `A` is a superset of the set using the `issuperset()` method and stores the result in a list `ret`.
- Finally, the program prints `True` if `A` is a superset of all the sets (i.e., all values in `ret` are `True`); otherwise, it prints `False`.
