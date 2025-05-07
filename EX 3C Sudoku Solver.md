# EX 3C Sudoku Solver
## DATE: 07/05/2025
## AIM:
To write a python program to find the solution of sudoku puzzle using Backtracking.


## Algorithm
1. Input: A 9×9 Sudoku board with 0s representing empty cells.
2. Check Validity: Use isPossible to validate a number’s placement by row, column, and 3×3 grid.


3. Recursive Solving: Loop through each cell; when an empty cell is found, try placing numbers 1–9.


4. Backtracking: If a number fits, proceed recursively; if stuck, reset the cell and backtrack.
5. Output: When the board is completely filled correctly, print the solution.

## Program:
```
/*
Program to implement to to find the solution of sudoku puzzle using Backtracking.
Developed by: Sakthi Navaneetha 
Register Number:  212222040138
*/

board = [
    [0, 0, 0, 8, 0, 0, 4, 0, 3],
    [2, 0, 0, 0, 0, 4, 8, 9, 0],
    [0, 9, 0, 0, 0, 0, 0, 0, 2],
    [0, 0, 0, 0, 2, 9, 0, 1, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 7, 0, 6, 5, 0, 0, 0, 0],
    [9, 0, 0, 0, 0, 0, 0, 8, 0],
    [0, 6, 2, 7, 0, 0, 0, 0, 1],
    [4, 0, 3, 0, 0, 6, 0, 0, 0]
]

def printBoard(board):
    for i in range(0, 9):
        for j in range(0, 9):
            print(board[i][j], end=" ")
        print()

def isPossible(board, row, col, val):
    for j in range(0, 9):
        if board[row][j] == val:
            return False

    for i in range(0, 9):
        if board[i][col] == val:
            return False

    startRow = (row // 3) * 3
    startCol = (col // 3) * 3
    for i in range(0, 3):
        for j in range(0, 3):
            if board[startRow+i][startCol+j] == val:
                return False
    return True

def solve():
    
    for i in range(9):
        for j in range(9):
            if board[i][j] == 0:
                for num in range(1, 10):
                    if isPossible(board, i, j, num):
                        board[i][j] = num
                        solve() 
                        board[i][j] = 0 
                return  
    printBoard(board)
solve()
```

## Output:


![image](https://github.com/user-attachments/assets/62a1b216-f6cd-4f7d-9420-9c1e4d8c902b)

## Result:
The Sudoku solver program executed successfully and found the solution for the given puzzle.
