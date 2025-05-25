# EX 6B KNAPSACK PROBLEM

### DATE: 20/05/2025

## AIM:
To demonstrate a python program using dynamic programming for 0/1 knapsack problem.

## Algorithm:

1. Create a 2D table K of size (n+1) x (W+1) to store the maximum value for each subproblem.
2. Initialize the first row and first column of K with 0, representing zero items or zero capacity.
3. Loop through each item i and each capacity w.
4. If the current item's weight is less than or equal to w, choose the maximum between including or excluding the item.
5. Return K[n][W] as the maximum value that can be stored in the knapsack of capacity W.
   
## Program:
```
# To implement the program for 0/1 knapsack problem.
# Developed by: SUJITHRA B K N
# Register Number: 212222230153

def knapSack(W, wt, val, n):
    K = [[0 for x in range(W + 1)] for x in range(n + 1)]
    for i in range(n + 1):
        for w in range(W + 1):
            if i == 0 or w == 0:
                K[i][w] = 0
            elif wt[i-1] <= w:
                K[i][w] = max(val[i-1]+ K[i-1][w-wt[i-1]],K[i-1][w])
            else:
                K[i][w] = K[i-1][w]
 
    return K[n][W]

x=int(input())
y=int(input())
W=int(input())
val=[]
wt=[]
for i in range(x):
    val.append(int(input()))
for y in range(y):
    wt.append(int(input()))

n = len(val)
print('The maximum value that can be put in a knapsack of capacity W is: ',knapSack(W, wt, val, n))
```

## Output:

![image](https://github.com/user-attachments/assets/46f6f10d-bdbd-4e18-91ad-4f35a0e8364c)

## Result:
Thus the program was executed successfully for finding the maximum value that can be put in a knap sack of capacity .
