# EX 3D Pattern Matching
## DATE: 07/05/2025
## AIM:
To write a python program to implement pattern matching on the given string using Brute Force algorithm.



## Algorithm
1. Input: Read two strings, s1 (text) and s2 (pattern).
2. Loop through s1: Slide the pattern across the text from position 0 to len(s1) - len(s2).
3. Character Matching: At each position, compare characters of s2 with the corresponding substring of s1.


4. Pattern Found: If all characters match, return the starting index.
5. Not Found: If no match is found, return -1.

## Program:
```
/*
Program to implement the Pattern Matching.
Developed by:  Sakthi Navaneetha 
Register Number: 212222040138
*/

def BF(s1,s2):
    len_s1 = len(s1)
    len_s2 = len(s2)

    for i in range(len_s1 - len_s2 + 1):
        j = 0
        while j < len_s2 and s1[i + j] == s2[j]:
            j += 1
        if j == len_s2:
            return i

    return -1
if __name__ == "__main__":
    a1=input() 
    a2=input() 
    b=BF(a1,a2)
    print(b)

```

## Output:

![image](https://github.com/user-attachments/assets/7898b01c-e868-4f40-91f5-907eb624e917)


## Result:
The brute force substring search program executed successfully and returned the starting index of the match or 0 if no match was found.
