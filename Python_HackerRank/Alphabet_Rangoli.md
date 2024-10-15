
# Alphabet Rangoli

## Question

You are given an integer `n`. Write a Python function to print an alphabet rangoli of size `n`. The rangoli should be created using lowercase English letters, and the letters should form a symmetric pattern.

### Input Format

- A single integer `n` denoting the size of the rangoli.

### Output Format

- Print the alphabet rangoli pattern.

### Example

**Input:**

```
5
```

**Output:**

```
--------e--------
------e-d-e------
----e-d-c-d-e----
--e-d-c-b-c-d-e--
e-d-c-b-a-b-c-d-e
--e-d-c-b-c-d-e--
----e-d-c-d-e----
------e-d-e------
--------e--------
```

---

## Solution

```python
def print_rangoli(size):

    import string
    chr = string.ascii_lowercase
    for i in range(2*size-1):
        if i == 0 or i == 2*size-2:
            print((chr[size-1]).center(4*size-3, '-'))
        elif i < size:
            suf = chr[size-1-i:size]
            str = (suf[::-1])[:len(suf)-1] + suf
            new_str = '-'.join(str)
            print(new_str.center(4*size-3, '-'))
        else:
            suf = chr[i-size+1:size]
            str = (suf[::-1])[:len(suf)-1] + suf
            new_str = '-'.join(str)
            print(new_str.center(4*size-3, '-'))

if __name__ == '__main__':
    n = int(input())
    print_rangoli(n)
```

## Solution Explanation

- The function starts by importing the lowercase alphabet characters using the `string` module.
- It then constructs the rangoli by generating the appropriate characters for each row and joining them with hyphens.
- The pattern is printed symmetrically, with the outermost rows containing fewer characters and the middle row containing the full sequence from `a` to the corresponding letter for the given size.
