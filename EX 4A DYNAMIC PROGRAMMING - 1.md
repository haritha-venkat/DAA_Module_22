# EX 4A DYNAMIC PROGRAMMING - 1
## DATE: 

## AIM:
To find longest common subsequence using Dynamic Programming.

## Algorithm

1. Initialize a 2D table `c` of size `(len(u)+1) x (len(v)+1)` with -1.
2. Set the last row and column of `c` to 0 (base case for empty substrings).
3. Fill `c` from bottom-right to top-left using LCS recurrence: if `u[i]==v[j]`, then `1 + c[i+1][j+1]`, else `max(c[i+1][j], c[i][j+1])`.
4. Starting from `c[0][0]`, trace through the table to find one LCS by following the character matches or max direction.
5. Print matching characters during trace as the LCS result.

## Program:
```
/*
Program to implement the longest common subsequence using Dynamic Programming

.
Developed by: haritha shree
Register Number:  212222230046
*/
def lcs(u, v):
    """Return c where c[i][j] contains length of LCS of u[i:] and v[j:]."""
    c = [[-1]*(len(v) + 1) for _ in range(len(u) + 1)]
    for i in range(len(u) + 1):
        c[i][len(v)] = 0
    for j in range(len(v)):
        c[len(u)][j] = 0
 
    for i in range(len(u) - 1, -1, -1):
        for j in range(len(v) - 1, -1, -1):
            if u[i] == v[j]:
                c[i][j] = 1 + c[i + 1][j + 1]
            else:
                c[i][j] = max(c[i + 1][j], c[i][j + 1])
    return c
 
def print_lcs(u, v, c):
    """Print one LCS of u and v using table c."""
    i = j = 0
    while not (i == len(u) or j == len(v)):
        if u[i] == v[j]:
            print(u[i], end='')
            i += 1
            j += 1
        elif c[i][j + 1] > c[i + 1][j]:
            j += 1
        else:
            i += 1
 
u = input()
v = input()
c = lcs(u, v)
print_lcs(u, v, c)
```

## Output:

![Screenshot 2025-05-16 182232](https://github.com/user-attachments/assets/88d56109-1a36-49a8-a2cc-b7dee0132634)


## Result:
Thus the program was executed successfully for computing the length of longest common subsequence.
