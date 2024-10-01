
# Exceptions

## Question

You are given `n` pairs of integers. For each pair, perform integer division and print the result. If an exception occurs (e.g., division by zero or invalid input), print the corresponding error message.

### Input Format

- The first line contains an integer, `n`, the number of test cases.
- The next `n` lines each contain two space-separated values, `a` and `b`.

### Constraints

- 1 <= n <= 10
- The numbers `a` and `b` can be any valid integers.

### Output Format

- For each test case, print the result of `a // b`. If an exception occurs, print the appropriate error message.

### Example

**Input:**

```
3
1 0
2 $
3 1
```

**Output:**

```
Error Code: integer division or modulo by zero
Error Code: invalid literal for int() with base 10: '$'
3
```

---

## Solution

```python
for _ in range(int(input())):
    try:
        a, b = input().split()
        print(int(a)//int(b))
    except ZeroDivisionError as e:
        print(f'Error Code: {e}')
    except ValueError as v:
        print(f"Error Code: {v}")
```

## Solution Explanation

- The program reads the number of test cases (`n`) and processes each test case one by one.
- It attempts to divide the two input values (`a` and `b`) as integers using `//`.
- If a `ZeroDivisionError` occurs (division by zero), the corresponding error message is printed.
- If a `ValueError` occurs (e.g., invalid input), the appropriate error message is displayed.
