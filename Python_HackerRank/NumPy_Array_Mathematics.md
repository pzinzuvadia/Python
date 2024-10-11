
# NumPy Array Mathematics

## Question

You are given two integer matrices `A` and `B` of size `n x m`. Using NumPy, perform the following operations on the matrices:
1. Addition (`A + B`)
2. Subtraction (`A - B`)
3. Multiplication (`A * B`)
4. Integer (floor) division (`A // B`)
5. Modulo (`A % B`)
6. Power (`A ** B`)

Write a Python program that reads the matrices, performs the above operations, and prints the results.

### Input Format

- The first line contains two integers `n` and `m`, representing the dimensions of the matrices.
- The next `n` lines contain the elements of matrix `A`.
- The following `n` lines contain the elements of matrix `B`.

### Output Format

- Print the result of each operation in the given order, one result per line.

### Example

**Input:**

```
1 4
1 2 3 4
5 6 7 8
```

**Output:**

```
[[ 6  8 10 12]]
[[-4 -4 -4 -4]]
[[ 5 12 21 32]]
[[0 0 0 0]]
[[1 2 3 4]]
[[    1    64  2187 65536]]
```

---

## Solution

```python
import numpy as np
n, m = map(int, input().split())
ls = []
lb = []
for i in range(n):
    ls.append(list(map(int, input().split())))
a = np.array(ls)
for j in range(n):
    lb.append(list(map(int, input().split())))
b = np.array(lb)

print(np.add(a, b))
print(np.subtract(a, b))
print(np.multiply(a, b))
print(np.floor_divide(a, b))
print(np.mod(a, b))
print(np.power(a, b))
```

## Solution Explanation

- The program first reads the dimensions `n` and `m`, then reads the two matrices `A` and `B`.
- It stores both matrices as NumPy arrays.
- The six operations (addition, subtraction, multiplication, integer division, modulo, and power) are performed using NumPy functions, and the results are printed.
