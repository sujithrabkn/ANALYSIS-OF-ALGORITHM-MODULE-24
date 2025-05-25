# EX 6C TRAVELLING SALES MAN PROBLEM

### DATE: 20/05/2025

## AIM:
To Solve Travelling Sales man Problem for the following graph.

![436921662-653921a4-3d7b-4691-9b41-735e80f7af0b](https://github.com/user-attachments/assets/8eb45109-005f-4eb1-9bfb-c79e52d57026)

## Algorithm:

1. Create a list of all vertices excluding the starting vertex s.
2. Generate all possible permutations of these vertices to represent every possible tour.
3. For each permutation, calculate the total path weight by summing distances between consecutive cities and returning to the start.
4. Track the minimum path weight among all permutations.
5. Return the minimum path weight as the shortest possible route that visits all cities and returns to the starting point.
   
## Program:
```
# To implement the program for TSP.
# Developed by: SUJITHRA B K N
# Register Number: 212222230153

from sys import maxsize
from itertools import permutations
V = 4
 

def travellingSalesmanProblem(graph, s):
    vertex = [] 
    for i in range(V): 
        if i != s: 
            vertex.append(i) 
    min_path = maxsize 
    next_permutation=permutations(vertex)
    for i in next_permutation:

        current_pathweight = 0
        k = s 
        for j in i: 
            current_pathweight += graph[k][j] 
            k = j 
        current_pathweight += graph[k][s] 
        min_path = min(min_path, current_pathweight) 
         
    return min_path

if __name__ == "__main__":
    graph = [[0, 10, 15, 20], [10, 0, 35, 25],
            [15, 35, 0, 30], [20, 25, 30, 0]]
    s = 0
    print(travellingSalesmanProblem(graph, s))
```

## Output:

![image](https://github.com/user-attachments/assets/83ecdfb1-693f-40d0-bd46-94ae5e9ab2d6)

## Result:
Thus the program was executed successfully for finding the minimum cost to vist all cities.
