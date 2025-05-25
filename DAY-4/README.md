# EX 6D BRUTE FORCE ALGORITHM

### DATE: 20/05/2025

## AIM:
To write a python program using brute force method of searching for the given substring in the main string.

## Algorithm:

1. Calculate the length of the main string and the substring.
2. Iterate through the main string from index 0 to len(string) - len(sub).
3. At each position, check if the substring matches the slice of the main string of the same length.
4. If it matches, print the index where the substring is found.
5. Call the match function with inputs str1 and str2.
   
## Program:
```
# To implement the program using brute force method of searching for the given substring in the main string.
# Developed by: SUJITHRA B K N
# Register Number: 212222230153

def match(string,sub):
    l = len(string)
    ls = len(sub)
    start = sub[0]
    for i in range(l-ls+1):
        if string[i:i+ls]==sub:
            print(f"Found at index {i}")

str1=input()
str2=input()
```

## Output:

![image](https://github.com/user-attachments/assets/efc9f0ee-3f6f-400e-8bf7-2b4a45710700)

## Result:
Thus the above program was executed successfully for searching the substring at respective index.
