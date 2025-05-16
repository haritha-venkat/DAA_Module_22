# EX 4B DYNAMIC PROGRAMMING – 2
## DATE:

## AIM:
To find the longest string (or strings) that is a substring (or are substrings) of two strings..



## Algorithm

1. Initialize a 2D table `lookup` of size `(m+1) x (n+1)` with zeros.
2. Set `maxLength = 0` and `endingIndex = m` to track the longest match.
3. Loop through each `i` in `1 to m` and `j` in `1 to n`, comparing `X[i-1]` and `Y[j-1]`.
4. If characters match, set `lookup[i][j] = lookup[i-1][j-1] + 1`, and update `maxLength` and `endingIndex` if longer substring is found.
5. Return the substring `X[endingIndex - maxLength : endingIndex]` as the longest common substring.


## Program:
```
/*
Program to implement the longest common substring problem

.
Developed by: HARITHA SHREE
Register Number:  212222230046
*/
def LCS(X, Y, m, n):
    maxLength = 0
    endingIndex = m
    lookup = [[0 for x in range(n + 1)] for y in range(m + 1)]
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if X[i - 1] == Y[j - 1]:
                lookup[i][j] = lookup[i - 1][j - 1] + 1
                if lookup[i][j] > maxLength:
                    maxLength = lookup[i][j]
                    endingIndex = i
    return X[endingIndex - maxLength: endingIndex]

X = input()
Y = input()
m = len(X)
n = len(Y)
print('The longest common substring is', LCS(X, Y, m, n))
```

## Output:
![Screenshot 2025-05-16 182457](https://github.com/user-attachments/assets/d5c73852-8f84-466f-a2dd-f87f2d1129c4)



## Result:
Thus the program was executed successfully for finding the longest common substring .
