
# Text Alignment

## Question

In this challenge, you are required to print a pattern using the letter 'H'. The size of the letter is determined by an integer `n` provided as input.

### Input Format

- A single integer `n`, denoting the size of the pattern.

### Constraints

- `1 <= n <= 100`

### Output Format

- Output the pattern using the letter 'H'.

### Example

**Input:**

```
5
```

**Output:**

```
    H    
   HHH   
  HHHHH  
 HHHHHHH 
HHHHHHHHH
  HHHHH                 HHHHH
  HHHHH                 HHHHH
  HHHHH                 HHHHH
  HHHHH                 HHHHH
  HHHHH                 HHHHH
  HHHHH                 HHHHH
  HHHHHHHHHHHHHHHHHHHHHHHHHHH
  HHHHHHHHHHHHHHHHHHHHHHHHHHH
  HHHHHHHHHHHHHHHHHHHHHHHHHHH
  HHHHHHHHHHHHHHHHHHHHHHHHHHH
  HHHHH                 HHHHH
  HHHHH                 HHHHH
  HHHHH                 HHHHH
  HHHHH                 HHHHH
  HHHHH                 HHHHH
    H                     H
     HHH                 HHH
      HHHHHHHHHHHHHHHHHHHHH
```

---

## Solution

```python
n = int(input())
c = 'H'

# Top Left Cone
for i in range(n):
    print((c*i).rjust(n-1)+c+(c*i).ljust(n-1))

# Upper 2 Pillars
for i in range(n+1):
    print((c*n).center(n*2) + (c*n).center(n*6))

# Centeral
for i in range((n+1)//2):
    print((c*n*5).center(n*6))

# Lower 2 pillars
for i in range(n+1):
    print((c*n).center(n*2) + (c*n).center(n*6))

# Lower Cone
for i in range(n):
    print(((c*(n-1-i)).rjust(n)+ c + (c*(n-1-i)).ljust(n)).rjust(n*6))
```

## Solution Explanation

- The code prints various parts of the 'H' pattern using loops:
  - The top cone is printed with increasing `H`s, aligned to the left.
  - The two pillars are printed in the upper and lower sections.
  - The central section contains five repetitions of 'H' printed in the center.
  - The lower cone is printed with decreasing `H`s, aligned to the right.
