
# Text Wrap

## Question

You are given a string `S` and width `w`. Your task is to wrap the string into a paragraph of width `w`.

### Function Signature

```python
def wrap(string: str, max_width: int) -> str:
```

### Input Format:

- The first line contains a string, `S`.
- The second line contains the width, `w`.

### Constraints:

- `0 < len(S) < 1000`
- `0 < w < len(S)`

### Output Format:

- Output the wrapped text, with each line having a maximum width of `w`.

### Example:

**Input:**

```
ABCDEFGHIJKLIMNOQRSTUVWXYZ
4
```

**Output:**

```
ABCD
EFGH
IJKL
IMNO
QRST
UVWX
YZ
```

---

## Solution

```python
def wrap(string, max_width):
    r = ''
    for i, e in enumerate(string):
        if i != 0 and i % max_width == 0:
            r += '\n' + e
        else:
            r += e
    return r

if __name__ == '__main__':
    string, max_width = input(), int(input())
    result = wrap(string, max_width)
    print(result)
```

## Solution Explanation

- The `wrap` function loops through the string and checks whether the current character index is a multiple of `max_width`. If so, it inserts a newline character (`\n`) to wrap the text.
- Otherwise, it continues appending the characters to the result string.
- The function returns the wrapped text in the desired format.
