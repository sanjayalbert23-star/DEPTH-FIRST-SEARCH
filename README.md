# EXPERIMENT 3: IMPLEMENT BREADTH FIRST SEARCH TRAVERSAL OF A GRAPH

**Name:** Sanjay A  
**Register Number:** 212225040367

## AIM

To implement Breadth First Search (BFS) traversal of a graph using Python 3.

## THEORY

Breadth First Search (BFS) is a graph traversal algorithm that visits vertices level by level, starting from a selected vertex. It visits all adjacent vertices before moving to the next level. BFS uses a queue data structure to maintain the order of traversal.

A visited array or set is used to prevent visiting the same vertex more than once, especially when the graph contains cycles.

## ALGORITHM

1. Create a graph using an adjacency list.
2. Read the number of vertices and edges.
3. Read the edges and add them to the graph.
4. Select vertex `A` as the starting vertex.
5. Insert the starting vertex into the queue and mark it as visited.
6. Remove a vertex from the front of the queue and add it to the traversal path.
7. Insert all its unvisited neighbouring vertices into the queue and mark them as visited.
8. Repeat until the queue becomes empty.
9. Display the BFS traversal path.

## PROGRAM

```python
from collections import deque, defaultdict

def bfs(graph, start, visited, path):
    queue = deque()
    queue.append(start)
    visited[start] = True

    while queue:
        node = queue.popleft()
        path.append(node)

        for neighbour in graph[node]:
            if not visited[neighbour]:
                visited[neighbour] = True
                queue.append(neighbour)

    return path


graph = defaultdict(list)

n, e = map(int, input().split())

for i in range(e):
    u, v = input().split()
    graph[u].append(v)
    graph[v].append(u)

start = 'A'
path = []
visited = defaultdict(bool)

traversedpath = bfs(graph, start, visited, path)
print(traversedpath)
```

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

## OUTPUT SCREENSHOT

<img width="638" height="565" alt="Screenshot 2026-10-29 104411" src="https://github.com/user-attachments/assets/360ed83a-6977-40ab-942a-c3db2e0d4503" />

## RESULT

Thus, a graph was constructed and Breadth First Search traversal was successfully implemented using Python 3.

