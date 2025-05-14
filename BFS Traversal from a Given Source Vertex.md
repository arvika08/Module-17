# Ex. No: 17B - BFS Traversal from a Given Source Vertex

## AIM:
To write a Python program to **print BFS traversal** from a given source vertex.

## ALGORITHM:

**Step 1**: Start the program.

**Step 2**: Create a graph using **adjacency list representation**.

**Step 3**: Add edges between vertices using the `addEdge()` method.

**Step 4**: Implement the `BFS()` function:
- Initialize all vertices as **not visited**.
- Use a **queue** to track vertices for traversal.
- Mark the **starting vertex** as visited and enqueue it.
- Dequeue a vertex, process it, and enqueue all its **adjacent unvisited vertices** while marking them as visited.

**Step 5**: Input the **starting vertex** and perform BFS traversal from it.

**Step 6**: Print the vertices in **BFS order**.

**Step 7**: End the program.

## PYTHON PROGRAM

class Graph:

	# Constructor
	def __init__(self):

		# default dictionary to store graph
		self.graph = defaultdict(list)

	def addEdge(self,u,v):
		self.graph[u].append(v)

	def BFS(self, s):

		# Mark all the vertices as not visited
		visited = [False] * (max(self.graph) + 1)

		# Create a queue for BFS
		queue = []

		# Mark the source node as
		# visited and enqueue it
		queue.append(s)
		visited[s] = True

		while queue:

			s = queue.pop(0)
			print (s, end = " ")

			for i in self.graph[s]:
				if visited[i] == False:
					queue.append(i)
					visited[i] = True

n=int(input())

g = Graph()

g.addEdge(0, 1)

g.addEdge(0, 2)

g.addEdge(1, 2)

g.addEdge(2, 0)

g.addEdge(2, 3)

g.addEdge(3, 3)

print ("Following is Breadth First Traversal"

    " (starting from vertex {})".format(n))
    
g.BFS(n)

## OUTPUT
![image](https://github.com/user-attachments/assets/effbd958-e12e-404f-a4de-19266e9eddd2)


## RESULT
Thus, a Python program to **print BFS traversal** from a given source vertex is implemented successfully.

