# EX 3B Hamiltonian Circuit Problem
## DATE: 07/05/2025
## AIM:
To write a python program to check whether Hamiltonian path exits in the given graph.

## Algorithm
1. Input: An adjacency matrix adj of a graph with N vertices.
2. Initialize: Start the path with the first vertex and set the rest to -1.
3. Recursive Check: Use is_hamiltonian_path to try adding all unvisited adjacent vertices to the path.
4. Base Case: If all N vertices are included in the path, return True.
5. Output: If a Hamiltonian path exists, return True; otherwise, return False.

## Program:
```
/*
Program to implement to check whether Hamiltonian path exits in the given graph.
Developed by: Sakthi Navaneetha 
Register Number:  212222040138
*/

def Hamiltonian_path(adj, N):
    
    def is_hamiltonian_path(path, pos):
        if pos == N:
            return True
        
        for v in range(N):
            if adj[path[pos - 1]][v] == 1 and v not in path:
                path[pos] = v
                
                if is_hamiltonian_path(path, pos + 1):
                    return True
                
                path[pos] = -1
        
        return False

    path = [-1] * N
    
    path[0] = 0
    
    if not is_hamiltonian_path(path, 1):
        return False
    
    return True
adj = [ [ 0, 1, 1, 1, 0 ] ,
        [ 1, 0, 1, 0, 1 ],
        [ 1, 1, 0, 1, 1 ],
        [ 1, 0, 1, 0, 0 ] ]
 
N = len(adj)
 
if (Hamiltonian_path(adj, N)):
    print("YES")
else:
    print("NO")
```

## Output:

![image](https://github.com/user-attachments/assets/8a2f1826-76be-4a18-afbc-4d2019975387)


## Result:
The Hamiltonian path program executed successfully, and it determined whether a Hamiltonian path exists in the given graph.
