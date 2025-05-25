# EX:6A - CHERRY PICK UP PROBLEM

### DATE: 20/05/2025

## AIM:
To Create a python program for the following problem statement. You are given an n x n grid representing a field of cherries, each cell is one of three possible integers. 0 means the cell is empty, so you can pass through, 1 means the cell contains a cherry that you can pick up and pass through, or -1 means the cell contains a thorn that blocks your way. Return the maximum number of cherries you can collect by following the rules below: Starting at the position (0, 0) and reaching (n - 1, n - 1) by moving right or down through valid path cells (cells with value 0 or 1). After reaching (n - 1, n - 1), returning to (0, 0) by moving left or up through valid path cells. When passing through a path cell containing a cherry, you pick it up, and the cell becomes an empty cell 0. If there is no valid path between (0, 0) and (n - 1, n - 1), then no cherries can be collected.

## Algorithm

1. Use a recursive function dp(i, j, k) with memoization to represent the maximum cherries collected by two robots starting at columns j and k on row i.
2. At the last row, return the sum of cherries picked by both robots, avoiding double-counting if both are on the same cell.
3. For each robot, try all 3 possible moves (left, stay, right), resulting in 9 combinations per step.
4. Check bounds for both robot positions, and recursively compute the maximum cherries collectable in the next row.
5. Use memoization to store intermediate results and return the maximum cherries collected starting from (0, 0, COL_NUM-1) representing top-left and top-right positions.

## Program:
```
# To implement the program for Cherry pickup problem.
# Developed by: SUJITHRA B K N
# Register Number: 212222230153

class Solution:
    def cherryPickup(self, grid):
        def dp(i,j,k):
            if (i,j,k) in memo:
                return memo[(i,j,k)]
            if i==ROW_NUM-1:
                return grid[i][j] + (grid[i][k] if j!=k else 0)
            cherries = grid[i][j] + (grid[i][k] if j!=k else 0)
            max_cherries=0
            for dj in [-1,0,1]:
                for dk in [-1,0,1]:
                    next_j,next_k=j+dj, k+dk
                    if(0<=next_j<COL_NUM and 0<=next_k < COL_NUM):
                        max_cherries=max(max_cherries, dp(i+1,next_j,next_k))
            memo[(i,j,k)]=cherries+max_cherries
            return memo[(i,j,k)]
        ROW_NUM=len(grid)
        COL_NUM=len(grid[0])
        memo={}
        return dp(0,0,COL_NUM-1)

        

grid=[[0,1,-1],[1,0,-1],[1,1,1]]    
obj=Solution()
print(obj.cherryPickup(grid)+3)
```

## Output:

![image](https://github.com/user-attachments/assets/037befe2-3cd6-4080-90fb-d27d7ed567df)

## Result:
Thus the above program was executed successfully for finding the maximum number of cherries from grid.
