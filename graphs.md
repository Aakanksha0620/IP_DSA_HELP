# Graphs

## 📘 Module 15: Graphs – “Mastering Connections, Traversals, and Structures”

***

### 📍1. DECISION DIAGRAM – When to Use BFS/DFS

```
textCopyEdit                      ┌──────────────┐
                      │  Problem Qn? │
                      └─────┬────────┘
                            │
         ┌──────────────────┴────────────────────┐
         ▼                                       ▼
    Is there a relationship?              Is there a grid or matrix?
 (Dependencies, paths, friends, etc.)         (2D movement)
         │                                       │
   Graph with adjacency list/matrix        Graph as matrix/grid
         │                                       │
 ┌───────┴────────┐                  ┌───────────┴───────────┐
 ▼                ▼                  ▼                       ▼
 Use BFS/DFS    Use Dijkstra/Topo     Use BFS for shortest   Use DFS for island counting
 Traversal       Sort, Cycle Check     distance (grids)       or connected components
```

***

### 🧠2. FLASHCARD – Graph Essentials

| Concept                 | Use Case                             |
| ----------------------- | ------------------------------------ |
| 🌐 Adjacency List       | Efficient for sparse graphs          |
| 🧱 Adjacency Matrix     | Dense graphs, fast lookup            |
| 🔁 DFS                  | Depth-based traversal, components    |
| 🔄 BFS                  | Shortest path in unweighted graphs   |
| 🪜 Topological Sort     | Order of dependencies (DAG only)     |
| 🔥 Flood Fill           | Matrix traversal (DFS/BFS)           |
| 🔍 Cycle Detection      | DFS with visited stack or Union Find |
| 🔃 Connected Components | DFS/BFS or Disjoint Set Union (DSU)  |

> 🔖 Mnemonic: **"GABDTCTC"** – Graph, AdjList, BFS, DFS, Topo, Cycle, Traversal, Components

***

### 📚3. GRAPH REPRESENTATION

#### ✳️ Adjacency List (Undirected)

```java
javaCopyEditList<List<Integer>> graph = new ArrayList<>();
for (int i = 0; i < n; i++) graph.add(new ArrayList<>());
graph.get(u).add(v);
graph.get(v).add(u);
```

***

#### ✳️ DFS Template

```java
javaCopyEditvoid dfs(int node, boolean[] visited, List<List<Integer>> graph) {
    visited[node] = true;
    for (int neighbor : graph.get(node)) {
        if (!visited[neighbor]) {
            dfs(neighbor, visited, graph);
        }
    }
}
```

***

#### ✳️ BFS Template

```java
javaCopyEditvoid bfs(int start, List<List<Integer>> graph) {
    Queue<Integer> q = new LinkedList<>();
    boolean[] visited = new boolean[graph.size()];
    q.offer(start); visited[start] = true;
    while (!q.isEmpty()) {
        int node = q.poll();
        for (int neighbor : graph.get(node)) {
            if (!visited[neighbor]) {
                q.offer(neighbor);
                visited[neighbor] = true;
            }
        }
    }
}
```

***

#### ✳️ Topological Sort (BFS - Kahn’s Algorithm)

```java
javaCopyEditint[] indegree = new int[n];
for (List<Integer> edges : graph) {
    for (int v : edges) indegree[v]++;
}
Queue<Integer> q = new LinkedList<>();
for (int i = 0; i < n; i++) if (indegree[i] == 0) q.offer(i);

while (!q.isEmpty()) {
    int node = q.poll();
    for (int neighbor : graph.get(node)) {
        if (--indegree[neighbor] == 0) q.offer(neighbor);
    }
}
```

***

### 🔄4. MISTAKES TO AVOID

| Mistake                        | Tip                                             |
| ------------------------------ | ----------------------------------------------- |
| Ignoring visited check         | May cause infinite loops                        |
| Wrong direction in DAG         | Always watch edge direction                     |
| Revisiting nodes               | Use a visited array or set                      |
| Incorrect graph representation | Use correct list/matrix for dense/sparse graphs |
| BFS for weighted graph         | Use Dijkstra instead                            |

***

### 🧩5. CURATED PROBLEM SET

#### ✅ Easy (10)

1. BFS/DFS of Graph (GFG)
2. Number of Provinces (LC 547)
3. Flood Fill (LC 733)
4. 01 Matrix (LC 542)
5. Island Perimeter (LC 463)
6. Count Number of Islands (LC 200)
7. Matrix Diagonal Traversal
8. Rotten Oranges (LC 994)
9. Find if Path Exists in Graph (LC 1971)
10. Clone Graph (LC 133)

***

#### 🟡 Medium (10)

1. Course Schedule I & II (LC 207, 210)
2. Detect Cycle in Directed Graph (LC 207)
3. Word Ladder I & II (LC 127, 126)
4. All Paths From Source to Target (LC 797)
5. Graph Valid Tree (LC 261)
6. Pacific Atlantic Water Flow (LC 417)
7. Surrounded Regions (LC 130)
8. Number of Enclaves (LC 1020)
9. Path With Minimum Effort (LC 1631)
10. Shortest Path in Binary Matrix (LC 1091)

***

#### 🔴 Hard (10)

1. Alien Dictionary (LC 269)
2. Critical Connections (Tarjan's - LC 1192)
3. Reconstruct Itinerary (LC 332)
4. Shortest Bridge (LC 934)
5. Minimum Genetic Mutation (LC 433)
6. Longest Cycle in Graph
7. Parallel Courses (LC 1136)
8. Find Eventual Safe States (LC 802)
9. Dijkstra’s Algorithm in Grid
10. Count All Cycles in Directed Graph

***

### ❓6. QUIZ – GRASPING GRAPHS

1. **"BFS gives shortest path when…"**\
   ➤ Edge weights are equal ✅\
   ➤ Graph is DAG\
   ➤ Graph is cyclic
2. **"Topological sort applies to…"**\
   ➤ Undirected Graph\
   ➤ DAG ✅\
   ➤ Trees
3. **"DFS is best for…"**\
   ➤ Shortest Path\
   ➤ Connectivity ✅\
   ➤ Level Order
4. **"What detects cycles in directed graphs?"**\
   ➤ Topo sort / DFS with recursion stack ✅\
   ➤ Just BFS

***

### 🧠7. FEYNMAN REFLECTION PROMPTS

* What is the core difference between BFS and DFS?
* Why is a visited array critical in graphs but not always in trees?
* When should you use adjacency matrix vs list?
* How does topological sort prove acyclic property?
