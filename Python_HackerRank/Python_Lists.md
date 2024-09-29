
# Python Lists

## Question

Consider a list (list = []). You can perform the following commands:

1. `insert i e`: Insert integer `e` at position `i`.
2. `print`: Print the list.
3. `remove e`: Delete the first occurrence of integer `e`.
4. `append e`: Insert integer `e` at the end of the list.
5. `sort`: Sort the list.
6. `pop`: Pop the last element from the list.
7. `reverse`: Reverse the list.

Write a program that performs the above commands on a list.

### Input Format

- The first line contains an integer, `N`, denoting the number of commands.
- Each line `i` of the `N` subsequent lines contains one of the commands described above.

### Constraints

- The elements added to the list must be integers.

### Output Format

- For the `print` command, print the list.

### Example

**Input:**

```
12
insert 0 5
insert 1 10
insert 0 6
print
remove 6
append 9
append 1
sort
print
pop
reverse
print
```

**Output:**

```
[6, 5, 10]
[1, 5, 9, 10]
[9, 5, 1]
```

---

## Solution

```python
if __name__ == '__main__':
    N = int(input())
    ls = []
    for _ in range(N):
        cmd = input().split()
        if cmd[0] == 'insert':
            ls.insert(int(cmd[1]), int(cmd[2]))
        if cmd[0] == 'print':
            print(ls)
        if cmd[0] == 'remove':
            ls.remove(int(cmd[1]))
        if cmd[0] == 'append':
            ls.append(int(cmd[1]))
        if cmd[0] == 'sort':
            ls.sort()
        if cmd[0] == 'pop':
            ls.pop()
        if cmd[0] == 'reverse':
            ls.reverse()
```

## Solution Explanation

- The code reads an integer `N`, which is the number of commands to execute.
- It processes each command and modifies the list `ls` accordingly.
- The program executes operations such as inserting elements, removing elements, sorting, reversing, and printing the list.
