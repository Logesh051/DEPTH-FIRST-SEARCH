# Experiment No. 3: Implement Breadth First Search (BFS) Traversal of a Graph

## Name: LOGESH.N.A

## Register Number: 212223240078

## AIM

To implement Breadth First Search (BFS) traversal of a graph using Python 3.

---

## THEORY

Breadth First Search (BFS) is a graph traversal technique that visits all the nodes at the current level before moving to the next level.

Unlike trees, graphs may contain cycles. To avoid visiting the same node multiple times, a Boolean visited array is used.

BFS uses a Queue data structure for traversal. Starting from the source node, all adjacent unvisited nodes are visited first, then their neighbors are visited level by level until all reachable nodes are traversed.

---

## ALGORITHM

1. Construct a graph with nodes and edges.
2. Breadth First Search uses a Queue for traversal.
3. Insert the start node into the Queue.
4. Find its neighboring nodes and check whether they are visited.
5. If a node is not visited, add it to the Queue and mark it as visited.
6. Repeat the process until the Queue becomes empty and all nodes are visited.

---

## PROCEDURE

1. Create a graph using adjacency list representation.
2. Read the number of vertices and edges.
3. Insert edges into the graph.
4. Select the starting node.
5. Insert the starting node into the queue.
6. Mark the node as visited.
7. Visit all adjacent unvisited nodes and add them to the queue.
8. Continue until the queue becomes empty.
9. Display the BFS traversal path.

---

## PROGRAM

```python
from collections import deque
from collections import defaultdict

def bfs(graph,start,visited,path):
    queue = deque()
    path.append(start)
    queue.append(start)
    visited[start] = True

    while len(queue) != 0:
        tmpnode = queue.popleft()

        for neighbour in graph[tmpnode]:
            if visited[neighbour] == False:
                path.append(neighbour)
                queue.append(neighbour)
                visited[neighbour] = True

    return path

graph = defaultdict(list)

v,e = map(int,input().split())

for i in range(e):
    u,v = map(str,input().split())
    graph[u].append(v)
    graph[v].append(u)

if '0' in graph:
    start = '0'
else:
    start = 'A'

path = []

visited = defaultdict(bool)

traversedpath = bfs(graph,start,visited,path)

print(traversedpath)
```

---

## SAMPLE INPUT

```text
7 9
A B
A C
A F
C E
C F
C D
D E
D G
G F
```

## SAMPLE OUTPUT

```text
['A', 'B', 'C', 'F', 'E', 'D', 'G']
```

---

## SAMPLE INPUT

```text
5 6
0 1
0 2
1 2
1 3
2 4
3 4
```

## SAMPLE OUTPUT

```text
['0', '1', '2', '3', '4']
```

---

## RESULT

Thus, a graph was constructed and implementation of Breadth First Search (BFS) traversal for the same graph was done successfully.
