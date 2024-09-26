
# HackerRank Problem: Nested List

**Problem Link:** [HackerRank - Nested List](https://www.hackerrank.com/challenges/nested-list/problem?isFullScreen=true)

## Problem Description

Given the names and grades for several students, determine the second lowest grade. If there are multiple students with the second lowest grade, order their names alphabetically and print each name on a new line.

### Input Format

- The first line contains an integer, *N*, the number of students.
- The next *2N* lines contain the name of a student and their grade.

### Constraints

- 2 <= N <= 5
- There will always be one or more students having the second lowest grade.

### Output Format

- Print the name(s) of any student(s) having the second lowest grade in alphabetical order.

### Sample Input
```
5
Harry
37.21
Berry
37.21
Tina
37.2
Akriti
41
Harsh
39
```

### Sample Output
```
Harry
Berry
```

## Solution

### Code
```python
if __name__ == '__main__':
    ls = []
    for _ in range(int(input())):
        name = input()
        score = float(input())
        ls.append([name, score])
    sorted_ls = sorted(ls, key = lambda x:(x[1], x[0]))
    sec_low = list(set(map(lambda x:x[1], ls)))
    sec_low.sort()
    sec_score = sec_low[1]
    for i in sorted_ls:
        if i[1] == sec_score:
            print(i[0])
```

### Explanation:

1. **Input Gathering:** We first gather the input for `N` students, storing each student's name and score in a list `ls`.
2. **Sorting:** We then sort the list `ls` based on the score first and then by name (to ensure alphabetical order when names are printed).
3. **Find Second Lowest Score:** Using the `set` function, we remove duplicate scores and sort the remaining ones. The second lowest score is accessed using `sec_low[1]`.
4. **Print Names:** Finally, we loop through the sorted list of students and print the names of students who have the second lowest score.

This code efficiently solves the problem while ensuring the names are printed in alphabetical order for the second lowest score.
