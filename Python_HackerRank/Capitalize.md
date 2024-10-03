
# Capitalize!

## Question

You are given a string `s`. Your task is to capitalize each word in `s`. A word is defined as a sequence of alphabetic characters, separated by spaces.

### Function Signature

```python
def solve(s: str) -> str:
```

### Input Format

- A single string `s`.

### Constraints

- 0 < len(s) < 1000
- The string contains only alphanumeric characters and spaces.

### Output Format

- Return the string with each word capitalized.

### Example

**Input:**

```
hello world
```

**Output:**

```
Hello World
```

---

## Solution

```python
def solve(s):

    ls = list(s)
    for i in range(len(ls)):
        if i == 0 and ls[i] != ' ':
            ls[i] = ls[i].upper()
        if ls[i] == ' ' and i != len(ls) - 1:
            ls[i+1] = ls[i+1].upper()
    return ''.join(ls)

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    s = input()

    result = solve(s)

    fptr.write(result + '\n')

    fptr.close()
```

## Solution Explanation

- The function `solve` converts the input string `s` into a list of characters.
- It iterates through each character, capitalizing the first letter of each word by checking if the current character is a space and capitalizing the next character.
- The `''.join(ls)` function combines the modified characters back into a string and returns the result.
