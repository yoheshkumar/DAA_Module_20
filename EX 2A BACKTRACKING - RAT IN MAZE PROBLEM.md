# EX:2A - BACKTRACKING - RAT IN MAZE PROBLEM
## DATE:

## AIM:
To implement the Rat in a Maze problem using backtracking and find all possible paths from the start to the destination in a given maze.


## Algorithm:

1. Initialize a 2D list maze to represent the grid (with 1 as path and 0 as blocked), and a 2D list sol of the same size filled with 0s to track the solution path.
2. Begin solving from the top-left cell (0, 0) using a recursive function to explore valid paths.
3. At each step, check if the current cell is within bounds and has a value of 1 to confirm it's a valid move.
4. Recursively attempt to move to the right `(x, y+1)` or down `(x+1, y)` to find a path to the goal.
5. If the destination `(N-1, N-1)` is reached, print the solution matrix. If no path is found, backtrack by resetting the cell and return false.

## Program:

```
# Program to implement Rat in a Maze

# DEVELOPED BY: YOHESH KUMAR R.M
# REGISTER NUMBER : 212222240118

N = 4
 
def printSolution( sol ):
     
    for i in sol:
        for j in i:
            print(str(j) + " ", end ="")
        print("")
 
def isSafe( maze, x, y ):
     
    if x >= 0 and x < N and y >= 0 and y < N and maze[x][y] == 1:
        return True
     
    return False
 
def solveMaze( maze ):
     
    # Creating a 4 * 4 2-D list
    sol = [ [ 0 for j in range(4) ] for i in range(4) ]
     
    if solveMazeUtil(maze, 0, 0, sol) == False:
        print("Solution doesn't exist");
        return False
     
    printSolution(sol)
    return True
     
def solveMazeUtil(maze, x, y, sol):
    if x==N-1 and y==N-1 and maze[x][y]==1:
        sol[x][y]=1
        return True
    if isSafe( maze, x, y ):
        sol[x][y]=1
        if solveMazeUtil(maze, x+1, y, sol):
            return True
        if solveMazeUtil(maze, x, y+1, sol):
            return True
        sol[x][y]=0
    return False

if __name__ == "__main__":
    # Initialising the maze
    maze = [ [1, 0, 0, 0],
             [1, 1, 0, 1],
             [0, 1, 0, 0],
             [1, 1, 1, 1] ]
              
    solveMaze(maze)
```

## Output:

![image](https://github.com/user-attachments/assets/805dacaa-304a-46f2-b22f-d346b7703a68)


## Result:

The Rat in a Maze program executed successfully, and a valid path from the start to the destination was found and display.
