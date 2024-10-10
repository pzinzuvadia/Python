
# NumPy Concatenate

## Question

You are given two integer matrices, `n x p` and `m x p`, and you need to concatenate them along the axis 0 using NumPy. Write a Python program to read the matrices, concatenate them, and print the result.

### Input Format

- The first line contains three integers `n`, `m`, and `p`, representing the number of rows in the first matrix, the number of rows in the second matrix, and the number of columns in both matrices.
- The next `n` lines contain the elements of the first matrix.
- The following `m` lines contain the elements of the second matrix.

### Output Format

- Print the concatenated matrix.

### Example

**Input:**

```
4 3 2
1 2
1 2
1 2
1 2
3 4
3 4
3 4
```

**Output:**

```
[[1 2]
 [1 2]
 [1 2]
 [1 2]
 [3 4]
 [3 4]
 [3 4]]
```

---

## Solution

```python
import numpy as np

n, m, p = map(int, input().split())
lsn = []
lsm = []
for i in range(n):
    lsn.append(list(map(int, input().split())))
for j in range(m):
    lsm.append(list(map(int, input().split())))

arr_n = np.array(lsn)
arr_m = np.array(lsm)

print(np.concatenate([arr_n, arr_m], axis=0))
```

## Solution Explanation

- The program first reads the dimensions `n`, `m`, and `p`, then reads the first and second matrices.
- It stores the first matrix in `arr_n` and the second matrix in `arr_m` as NumPy arrays.
- The `np.concatenate()` function is used to concatenate the two arrays along axis 0, and the result is printed.
