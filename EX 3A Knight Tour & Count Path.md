# EX 3A Knight Tour & Count Path
## DATE: 07/05/2025
## AIM:
To write a python program to find minimum steps to reach to specific cell in minimum moves by knight


## Algorithm
1. Input: The board size N, starting position knightpos, and target position targetpos.
2. Define isInside(x, y, N): Check if a position (x, y) is within the board bounds.
3. Initialize a Queue: Start from the knight’s position with a distance of 0, and use BFS.
4. BFS Exploration: Explore all 8 possible knight moves and add valid positions to the queue.
5. Output: Return the distance to the target when reached, or infinity if unreachable.

## Program:
```
/*
Program to implement to find minimum steps to reach to specific cell in minimum moves by knight.
Developed by:  Sakthi Navaneetha 
Register Number: 212222040138
*/

class cell:
     
    def __init__(self, x = 0, y = 0, dist = 0):
        self.x = x
        self.y = y
        self.dist = dist

def isInside(x, y, N):
    if (x >= 1 and x <= N and
        y >= 1 and y <= N):
        return True
    return False
def minStepToReachTarget(knightpos,
                         targetpos, N):
     
    # add your code here
    dx = [-2, -1, 1, 2, -2, -1, 1, 2]
    dy = [-1, -2, -2, -1, 1, 2, 2, 1]

    queue = []
    queue.append(cell(knightpos[0], knightpos[1], 0))

    visited = [[False for _ in range(N + 1)] for _ in range(N + 1)]
    visited[knightpos[0]][knightpos[1]] = True

    while len(queue) > 0:
        curr = queue.pop(0)

        if curr.x == targetpos[0] and curr.y == targetpos[1]:
            return curr.dist

        for i in range(8):
            x = curr.x + dx[i]
            y = curr.y + dy[i]

            if isInside(x, y, N) and not visited[x][y]:
                visited[x][y] = True
                queue.append(cell(x, y, curr.dist + 1))

    return float('inf')
    
if __name__=='__main__':
    N = 30
    knightpos = [1, 1]
    targetpos = [30, 30]
    print(minStepToReachTarget(knightpos,
                               targetpos, N))
```

## Output:

![image](https://github.com/user-attachments/assets/068b3593-c4eb-4e4f-9222-be0a09fa8fab)


## Result:
The program executed successfully, and the minimum number of steps for the knight to reach the target was calculated.
