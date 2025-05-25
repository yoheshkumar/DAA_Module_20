# EX:2D - BACKTRACKING - GRAPH COLORING PROBLEM
## DATE:

## AIM:
To solve the Graph Coloring Problem using backtracking, assigning colors to the vertices of a graph such that no two adjacent vertices share the same color while minimizing the number of colors used.

## Algorithm

1. Represent the graph as an adjacency matrix and create an array to store colors for each vertex (initially zero).
2. Begin assigning colors to vertices starting from the first vertex.
3. Before assigning a color to a vertex, verify that no adjacent vertex has the same color.
4. Try all colors for each vertex. If no color is valid, backtrack and change the previous vertex’s color.
5. If all vertices are successfully colored, print the colors assigned. Otherwise, print that no solution exists.

## Program:

```
# Program to implement Graph Coloring Problem using backtracking.

# DEVELOPED BY: YOHESH KUMAR R.M
# REGISTER NUMBER : 212222240118

class Graph:
    def __init__(self,vertices):
        self.V=vertices
        self.Graph=[[0 for column in range(vertices)]for row in range(vertices)]
    def isSafe(self,v,colour,c):
        for i in range(self.V):
            if self.graph[v][i]==1 and colour[i]==c:
                return False
        return True
    def graphColourUtil(self,m,colour,v):
        if v==self.V:
            return True
        for c in range(1,m+1):
            if self.isSafe(v,colour,c):
                colour[v]=c
                if self.graphColourUtil(m,colour,v+1):
                    return True
                colour[v]=c
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

![image](https://github.com/user-attachments/assets/3a638ea4-29c2-4dcf-b54b-906097917f8d)

## Result:

The Graph Coloring program executed successfully, and the colors were assigned to the vertices such that no two adjacent vertices share the same color.
