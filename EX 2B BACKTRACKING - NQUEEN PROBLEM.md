# EX 2B BACKTRACKING - NQUEEN PROBLEM
## AIM:
To solve the N-Queen problem using backtracking, which places N queens on an N*N chessboard such that no two queens threaten each other.

## Algorithm:
```
1. Input the value of N (board size and number of queens).
2. Create an N × N board initialized with 0.
3. Define isSafe(board, row, col) to check if placing a queen is valid.
4. Define the recursive function solveNQUtil(board, col) to place queens in each column.
5. If all columns are filled, return True.
6. For each row, if placing a queen is safe, place it and recurse to the next column.
7. If recursion fails, backtrack by removing the queen.
8. If no valid row is found in a column, return False.
9. Define solveNQ() to initialize the board and call solveNQUtil.
10. If a solution is found, print the board; otherwise, print "Solution does not exist".
```

## Program:
```
Developed by: Kamali E
Register Number: 212222110015

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
        if isSafe(board,i,col):
            board[i][col]=1
            if solveNQUtil(board, col+1)==True:
                return True
            board[i][col]=0
    return False
        
def solveNQ():
    board = [ [0, 0, 0, 0],
              [0, 0, 0, 0],
              [0, 0, 0, 0],
              [0, 0, 0, 0]]
              
    if solveNQUtil(board, 0) == False:
        print ("Solution does not exist")
        return False
 
    printSolution(board)
    return True
 
# Driver Code
solveNQ()

```

## Output:
![Screenshot 2025-04-29 113548](https://github.com/user-attachments/assets/914d40d3-aafb-4fdd-980f-8cdd8a85c1d8)

## Result:
The N-Queens program executed successfully, and a valid board configuration was generated.
