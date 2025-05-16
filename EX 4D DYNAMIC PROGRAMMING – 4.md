# EX 4D DYNAMIC PROGRAMMING – 4
## DATE:

## AIM:
To find the minimum number of operations to convert str1 to str2 using Naive recursive method.

## Algorithm

1. If either string is empty, return the length of the other (base case).
2. If last characters of both strings match, set `cost = 0`, else `cost = 1`.
3. Recursively compute three operations: insert, delete, and substitute.
4. Take the minimum of the three operations plus `cost` where applicable.
5. Return the final result as the edit distance between the two strings.

## Program:
```
/*
Program to implement to find the minimum number of operations to convert str1 to str2 using Naive recursive method

.
Developed by: HARITHA SHREE
Register Number:  212222230046
*/
def LD(s, t):
    #########  Add your code here ###########
    if s == "":
        return len(t)
    if t == "":
        return len(s)
    if s[-1] == t[-1]:
        cost = 0
    else:
        cost = 1
    res = min([LD(s[:-1], t)+1, LD(s, t[:-1])+1, LD(s[:-1], t[:-1]) + cost])
    return res
    
str1=input()
str2=input()
print('Edit Distance',LD(str1,str2))
```

## Output:
![Screenshot 2025-05-16 182904](https://github.com/user-attachments/assets/4998bc07-9b8e-4110-aeb4-a67d3095aa2d)



## Result:
Thus the program was executed successfully for finding edit distance between two strings.
