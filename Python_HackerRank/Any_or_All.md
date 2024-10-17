
# Any or All

## Question

You are given a space-separated list of integers. Write a Python program to check whether all the integers are non-negative and if at least one of them is a palindrome (reads the same forward and backward).

### Input Format

- The first line contains an integer `n`, the number of integers in the list.
- The second line contains the `n` space-separated integers.

### Output Format

- Print `True` if all integers are non-negative and at least one is a palindrome. Otherwise, print `False`.

### Example

**Input:**

```
5
12 9 61 5 14
```

**Output:**

```
True
```

---

## Solution

```python
n = input().strip()
ls = list(input().split())
tf_ls = [int(e) >= 0 for e in ls]
tfp_ls = [e[::-1] == e for e in ls]
print(all(tf_ls) and any(tfp_ls))
```

## Solution Explanation

- The program first reads the input and converts the list of integers into a list of strings.
- It creates two lists: one for checking if all integers are non-negative (`tf_ls`) and another for checking if any of the integers is a palindrome (`tfp_ls`).
- The result is `True` if all integers are non-negative and at least one is a palindrome; otherwise, `False`.
