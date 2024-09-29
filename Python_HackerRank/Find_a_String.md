
# Find a String

## Question

In this challenge, the user enters a string and a substring. You have to print the number of times the substring occurs in the given string. The string traversal will take place from left to right, not from right to left.

### Function Signature

```python
def count_substring(string: str, sub_string: str) -> int:
```

### Input Format

- The first line of input contains the original string.
- The second line contains the substring.

### Output Format

- Output the integer number indicating the occurrence of the substring in the original string.

### Example

**Input:**

```
ABCDCDC
CDC
```

**Output:**

```
2
```

---

## Solution

```python
def count_substring(string, sub_string):
    cnt = 0
    for i in range(len(string) - len(sub_string) + 1):
        if string[i:i+len(sub_string)] == sub_string:
            cnt += 1
    return cnt

if __name__ == '__main__':
    string = input().strip()
    sub_string = input().strip()
    
    count = count_substring(string, sub_string)
    print(count)
```

## Solution Explanation

- The `count_substring` function iterates through the string and checks if the substring matches the current slice of the string.
- If a match is found, the counter `cnt` is incremented.
- The function returns the count of matches.
