# Ex. No: 17C - DFS Traversal from a Given Source Vertex

## AIM:
To write a Python program to **print DFS traversal** from a given source vertex.

## ALGORITHM:

**Step 1**: Start the program.

**Step 2**: Create a graph using **adjacency list representation**.

**Step 3**: Add edges between vertices using the `addEdge()` method.

**Step 4**: Implement the `DFSUtil()` function to **recursively visit** and print each unvisited vertex:
- Mark the current vertex as **visited**.
- Recursively call `DFSUtil` for each **unvisited adjacent vertex**.

**Step 5**: In the `DFS()` function:
- Initialize an empty set for visited vertices.
- Call `DFSUtil()` starting from the given vertex.

**Step 6**: Input the **starting vertex** and perform DFS traversal.

**Step 7**: Print the vertices in **DFS order**.

**Step 8**: End the program.

## PYTHON PROGRAM

from collections import defaultdict

class Graph:

	# Constructor
	def __init__(self):

		self.graph = defaultdict(list)

	def addEdge(self, u, v):
		self.graph[u].append(v)

	def DFSUtil(self, v, visited):
 
		visited.add(v)
		print(v, end=' ')

		for neighbour in self.graph[v]:
			if neighbour not in visited:
				self.DFSUtil(neighbour, visited)
	def DFS(self, v):

		visited = set()

		self.DFSUtil(v, visited)

n=int(input())

g = Graph()

g.addEdge(0, 1)

g.addEdge(0, 2)

g.addEdge(1, 2)

g.addEdge(2, 0)

g.addEdge(2, 3)

g.addEdge(3, 3)

print("Following is DFS from (starting from vertex {})".format(n))

g.DFS(n)

## OUTPUT
![image](https://github.com/user-attachments/assets/9307b697-93fe-4570-9cf3-0194fade5a84)


## RESULT
Thus, a Python program to **print DFS traversal** from a given source vertex is implemented successfully.
