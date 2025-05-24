# EX 2A BACKTRACKING - RAT IN MAZE PROBLEM
## AIM:
To implement the Rat in a Maze problem using backtracking and find all possible paths from the start to the destination in a given maze.

## Algorithm:
```
1. Input the maze of size N x N.
2. Create a solution matrix initialized to 0.
3. Define isSafe(x, y) to check if the cell is within bounds and not blocked.
4. Define the recursive function solveMazeUtil(x, y) to explore paths.
4. If destination is reached, mark the path and return True.
5. If current cell is safe, mark it as part of the solution and try moving down and right.
6. If both moves fail, backtrack by unmarking the cell and return False.
7. Call solveMaze() to start from (0, 0) and display the solution or failure message.
``` 
## Program:
```
Developed by: Kamali E
Register Number:  212222110015

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
    sol = [ [ 0 for j in range(4) ] for i in range(4) ]
     
    if solveMazeUtil(maze, 0, 0, sol) == False:
        print("Solution doesn't exist");
        return False
     
    printSolution(sol)
    return True

def solveMazeUtil(maze, x, y, sol):
    if not isSafe(maze,x,y):
        return False
        
    if x== N-1 and y== N-1:
        sol[x][y]=1
        return True
    sol[x][y]=1
    
    if solveMazeUtil(maze,x+1,y,sol):
        return True
        
    if solveMazeUtil(maze,x,y+1,sol):
        return True
        
    sol[x][y]=0
    return False
     
# Driver program to test above function
if __name__ == "__main__":
    # Initialising the maze
    maze = [ [1, 0, 0, 0],
             [1, 1, 0, 1],
             [0, 1, 0, 0],
             [1, 1, 1, 1] ]
              
    solveMaze(maze)
```

## Output:
![Screenshot 2025-04-29 113029](https://github.com/user-attachments/assets/b439db2b-f92c-4a50-92ea-6198118521e5)

## Result:
The Rat in a Maze program executed successfully, and a valid path from the start to the destination was found and display.
