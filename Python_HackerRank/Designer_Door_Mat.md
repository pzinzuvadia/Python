
# Designer Door Mat

## Question

You are given the dimensions of a rectangular door mat, and your task is to design the mat using the following specifications:

- The mat has `n` rows and `m` columns (n is always odd and m is 3 times `n`).
- The design should have a central line with the word "WELCOME" and patterns of `.|.` on both sides.

### Input Format

- A single line containing two space-separated integers, `n` and `m`, representing the number of rows and columns, respectively.

### Constraints

- 5 < n < 101
- 15 < m < 303
- `n` is odd and `m` is 3 times `n`

### Output Format

- Output the door mat design.

### Example

**Input:**

```
7 21
```

**Output:**

```
-----.|.-----
---.|..|..|.---
-.|..|..|..|..|.-
-------WELCOME-------
-.|..|..|..|..|.-
---.|..|..|.---
-----.|.-----
```

---

## Solution

```python
n, m = map(int, input().split())
c = '.|.'
for i in range(n):
    if i == n//2:
        print('WELCOME'.center(m, '-'))
    if i < n//2:
        print(((c*i) + c + (c*i)).center(m, '-'))
    if i > n//2:
        print(((c*(n-i-1)) + c + (c*(n-i-1))).center(m, '-'))
```

## Solution Explanation

- The code first reads the dimensions `n` and `m`.
- It then prints the top part of the door mat using `.|.` patterns, followed by the center line with "WELCOME", and finally prints the bottom part of the door mat, which mirrors the top.
- The `center(m, '-')` function centers the patterns and the "WELCOME" text within the width `m`, with hyphens used as padding.
