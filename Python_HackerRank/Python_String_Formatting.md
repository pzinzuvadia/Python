
# Python String Formatting

## Question

Given an integer `n`, print its decimal, octal, hexadecimal, and binary values in a formatted style.

### Function Signature

```python
def print_formatted(n: int):
```

### Input Format

- A single integer `n`.

### Constraints

- `1 <= n <= 99`

### Output Format

- Print `n` lines where each line contains the decimal, octal, hexadecimal (capitalized), and binary representation of the integer.
- Each value should be right-aligned according to the width of the binary representation of `n`.

### Example

**Input:**

```
17
```

**Output:**

```
    1     1     1     1
    2     2     2    10
    3     3     3    11
    4     4     4   100
    5     5     5   101
    6     6     6   110
    7     7     7   111
    8    10     8  1000
    9    11     9  1001
   10    12     A  1010
   11    13     B  1011
   12    14     C  1100
   13    15     D  1101
   14    16     E  1110
   15    17     F  1111
   16    20    10 10000
   17    21    11 10001
```

---

## Solution

```python
def print_formatted(n):
    width = len(bin(n)[2:])
    for i in range(1, n+1):
        dec = str(i)
        oc = oct(i)[2:]
        hx = hex(i)[2:].upper()
        bi = bin(i)[2:]
        print(f"{dec:>{width}} {oc:>{width}} {hx:>{width}} {bi:>{width}}")

if __name__ == '__main__':
    n = int(input())
    print_formatted(n)
```

## Solution Explanation

- The `print_formatted` function takes an integer `n` and prints its decimal, octal, hexadecimal, and binary values.
- The width is determined by the length of the binary representation of `n`.
- The function loops from 1 to `n` and prints the values with appropriate formatting, ensuring that each value is right-aligned.
