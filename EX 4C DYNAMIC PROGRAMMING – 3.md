# EX 4C DYNAMIC PROGRAMMING – 3
## DATE:

## AIM:
Given a sequence, find the length of the longest palindromic subsequence in it.

## Algorithm

1. Initialize a 2D `dp` table of size `1001 x 1001` with -1 for memoization.
2. Define `lps(s1, s2, n1, n2)` to compute LCS between the string and its reverse.
3. If either string length is 0, return 0 (base case).
4. If characters match, return `1 + lps(...)` for previous indices; else, return max of excluding a character from either string.
5. Call `lps(seq[::-1], seq, n, n)` and print the result as the LPS length.
  

## Program:
```
/*
Program to implement to find the length of the longest palindromic subsequence in it

.
Developed by: HARITHA SHREE
Register Number:  212222230046
*/
dp = [[-1 for i in range(1001)]for j in range(1001)]
def lps(s1, s2, n1, n2):
    if (n1 == 0 or n2 == 0):
        return 0
    if (dp[n1][n2] != -1):
        return dp[n1][n2]
    if (s1[n1 - 1] == s2[n2 - 1]):
        dp[n1][n2] = 1 + lps(s1, s2, n1 - 1, n2 - 1)
        return dp[n1][n2]
    else:
        dp[n1][n2] = max(lps(s1, s2, n1 - 1, n2), lps(s1, s2, n1, n2 - 1))
        return dp[n1][n2]
seq = input()
n = len(seq)
s2 = seq
s2 = s2[::-1]
print(f"The length of the LPS is",lps(s2, seq, n, n))
```

## Output:

![Screenshot 2025-05-16 182708](https://github.com/user-attachments/assets/42e38aab-a2c3-4d66-ab4f-5507e0793073)


## Result:
Thus the program was executed successfully for finding the length of longest palindromic string.
