
# itertools.permutations()

## Question

You are given a string `S` and an integer `k`. Use the `itertools.permutations()` function to generate all possible permutations of size `k` from the string `S`. Print the permutations in lexicographically sorted order, one per line.

### Input Format

- The first line contains the string `S` and the integer `k`, separated by a space.

### Output Format

- Print each permutation on a new line.

### Example

**Input:**

```
HACK 2
```

**Output:**

```
AC
AH
AK
CA
CH
CK
HA
HC
HK
KA
KC
KH
```

---

## Solution

```python
from itertools import permutations

string, k = input().split()
str_ls = list(string)
str_ls.sort()
ls = permutations(str_ls, int(k))
for i in ls:
    for j in i:
        print(j, end = '')
    print()
```

## Solution Explanation

- The program reads the input string `S` and integer `k` using `input()`.
- The string is converted to a list and sorted in lexicographical order.
- The `itertools.permutations()` function generates all possible permutations of size `k` from the sorted string.
- The result is printed, one permutation per line.
