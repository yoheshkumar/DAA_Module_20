# EX:2B - BACKTRACKING - NQUEEN PROBLEM
## DATE:

## AIM:
To solve the N-Queen problem using backtracking, which places N queens on an N*N chessboard such that no two queens threaten each other.


## Algorithm


1. Create an N x N chessboard and take user input for N, the number of queens to be placed.
2. Create a 2D list board filled with 0s to represent the chessboard where 1 indicates a queen is placed.
3. Starting from column 0, attempt to place a queen in every row of the current column and move recursively to the next column.
4. For each attempted cell, verify that no other queen exists in the same row, upper-left diagonal, or lower-left diagonal.
5. If a valid configuration is found, print the board. If no solution exists, backtrack and try other possibilities. Display a message if no configuration is 
   possible.

## Program:

```
# Program to implement N-Queen problem using backtracking

# DEVELOPED BY: YOHESH KUMAR R.M
# REGISTER NUMBER: 212222240118

global N
N = int(input())
 
def printSolution(board):
    for i in range(N):
        for j in range(N):
            print(board[i][j], end = " ")
        print()
 
def isSafe(board, row, col):
 
    # Check this row on left side
    for i in range(col):
        if board[row][i] == 1:
            return False
 
    # Check upper diagonal on left side
    for i, j in zip(range(row, -1, -1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
 
    # Check lower diagonal on left side
    for i, j in zip(range(row, N, 1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
 
    return True
 
def solveNQUtil(board, col):
      if col>=N:
          return True
      for i in range(N):
          if isSafe(board, i, col):
              board[i][col]=1
              if solveNQUtil(board, col+1):
                  return True
              board[i][col]=0
      return False

def solveNQ():
    board = [ [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0]]
 
    if solveNQUtil(board, 0) == False:
        print ("Solution does not exist")
        return False
 
    printSolution(board)
    return True
 
# Driver Code
solveNQ()
```

## Output:

![image](https://github.com/user-attachments/assets/a3d682a0-2860-421f-9e2f-979a77a695a8)


## Result:

The N-Queens program executed successfully, and a valid board configuration was generated.
