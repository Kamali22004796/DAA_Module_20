# EX 2D BACKTRACKING - GRAPH COLORING PROBLEM
## AIM:
To solve the Graph Coloring Problem using backtracking, assigning colors to the vertices of a graph such that no two adjacent vertices share the same color while minimizing the number of colors used.

## Algorithm:
```
1. Input the number of vertices V in the graph.
2. Initialize the adjacency matrix graph.
3. Input the maximum number of colors M.
4. Create a list `colour` of size V initialized to 0.
5. Define `isSafe(vertex, colour, c)` to check if color c can be assigned to the vertex.
6. Define the recursive function `graphColourUtil(m, colour, v)` to assign colors to vertices.
7. If all vertices are assigned, return True.
8. Try all colors from 1 to M; if safe, assign and recur. If recursion fails, backtrack.
9. Return False if no color can be assigned to a vertex.
10. Call `graphColouring(m)` to start coloring and print the result or "Solution does not exist".
```

## Program:
```
Developed by: Kamali E
Register Number: 212222110015

class Graph:
    def __init__(self,vertices):
        self.V=vertices
        self.graph=[[0 for row in range(vertices)] for column in range(vertices)]
        
    def isSafe(self,v,colour,c):
        for i in range(v):
            if self.graph[v][i]==1 and colour[i]==c:
                return False
        return True
        
    def graphColourUtil(self,m,colour,v):
        if v==self.V:
            return True 
        for i in range(1,m+1):
            if self.isSafe(v,colour,i):
                colour[v]=i
                if self.graphColourUtil(m,colour,v+1):
                    return True
        return False
        
    def graphColouring(self,m):
        colour=[0]*self.V
        if not self.graphColourUtil(m,colour,0):
            print("No solution Exist")
            return False
        print("Solution exist and Following are the assigned colours:")
        
        for c in colour:
            print(c,end=' ')
        print()
        return True
```

## Output:
![Screenshot 2025-04-29 114410](https://github.com/user-attachments/assets/0f212e79-898e-45dd-bd42-c4cfbf7f32ed)

## Result:
The Graph Coloring program executed successfully, and the colors were assigned to the vertices such that no two adjacent vertices share the same color.
