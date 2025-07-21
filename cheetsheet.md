# Cheetsheet

## 📎 DSA Cheatsheet: What Pattern & Data Structure to Use?

| 🔍 **If the Problem Mentions / Involves**  | 🧠 **Use this Pattern**     | 🧺 **Use this Data Structure** | 💡 **Notes**                           |
| ------------------------------------------ | --------------------------- | ------------------------------ | -------------------------------------- |
| "Find a pair that adds to target"          | Two Pointers / Hashing      | Array, HashSet                 | Use two pointers if sorted             |
| "Find longest substring..."                | Sliding Window              | HashMap, HashSet               | Use variable size window               |
| "Check if number is power of 2"            | Bit Manipulation            | -                              | Use `(n & (n-1)) == 0`                 |
| "Find max/min element efficiently"         | Heap / Priority Queue       | MinHeap / MaxHeap              | Use for top-K, scheduling              |
| "Insert/delete in O(1)"                    | Hashing                     | HashMap/Set                    | Good for caches, frequency count       |
| "Parentheses, Balanced string"             | Stack                       | Stack                          | Use for valid expressions              |
| "k-th smallest/largest"                    | Heap / QuickSelect          | MinHeap / MaxHeap              | MinHeap of size k                      |
| "Next greater/smaller element"             | Monotonic Stack             | Stack                          | Store indices for span problems        |
| "Find duplicate/missing element"           | Hashing / XOR               | HashSet / Bit Tricks           | XOR or cycle detection for 1 duplicate |
| "Undo / Reversal"                          | Stack / Recursion           | Stack / Linked List            | Think DFS-style logic                  |
| "Merge intervals, overlapping ranges"      | Sorting + Two Pointers      | ArrayList                      | Sort by start time                     |
| "Shortest path unweighted"                 | BFS                         | Queue + Adjacency List         | Level-wise traversal                   |
| "Shortest path weighted"                   | Dijkstra                    | MinHeap + Graph                | Use PriorityQueue                      |
| "Dependency order"                         | Topological Sort            | Queue + In-degree              | Only works on DAG                      |
| "2D Matrix traversal"                      | BFS / DFS / Backtracking    | Matrix, Queue                  | Flood fill, island problems            |
| "All combinations/subsets"                 | Backtracking / Bitmask      | Recursion / Array              | Choose or skip each element            |
| "Find if cycle exists"                     | DFS / Union-Find            | Visited\[] / DSU               | Check visited state or parent link     |
| "Reversing elements in-place"              | Two Pointers                | Array                          | Swap left and right pointers           |
| "Find median / percentiles"                | Heap                        | MaxHeap + MinHeap              | Dual heap approach                     |
| "Most frequent / Top K frequent"           | Bucket Sort / Heap          | HashMap + PriorityQueue        | Sort by frequency                      |
| "Find peaks / valleys / rotation"          | Binary Search               | Array                          | For sorted rotated arrays              |
| "Prefix/suffix sums"                       | Sliding Window / Prefix Sum | Array                          | Used to speed up range queries         |
| "Range Updates & Queries"                  | Segment Tree / BIT          | Tree / Array                   | Advanced topic                         |
| "Matching prefixes (autocomplete)"         | Trie                        | TrieNode Tree                  | Good for dictionary lookups            |
| "Search in 2D grid"                        | DFS / BFS / Binary Search   | Matrix                         | Word search, path finding              |
| "Permutations / Combinations"              | Backtracking                | Array + Visited\[]             | Track used state                       |
| "Dynamic choices, overlapping subproblems" | Dynamic Programming         | 1D / 2D Array                  | Memoization/tabulation                 |

##

## ✅ DSA Pattern & Data Structure Cheatsheet (Plain Text)

***

### 🔁 Arrays / Hashing / Prefix

| 🧠 Problem Pattern               | 🎯 Pattern             | 📦 Data Structure | 📝 Notes                         |
| -------------------------------- | ---------------------- | ----------------- | -------------------------------- |
| Find pair with sum               | Two Pointers / Hashing | Array, HashSet    | If sorted → two pointers         |
| Subarray sum to K                | Prefix Sum + Hashing   | HashMap           | Track sum and its frequency      |
| Frequency counting               | Hashing                | HashMap, Array    | Classic trick in strings/numbers |
| Longest substring without repeat | Sliding Window         | HashSet, HashMap  | Expand + shrink window           |

***

### 🧮 Math / Bit Manipulation

| 🧠 Problem Pattern             | 🎯 Pattern       | 📦 Data Structure | 📝 Notes            |
| ------------------------------ | ---------------- | ----------------- | ------------------- |
| Check power of 2 / toggle bits | Bit Manipulation | N/A               | `(n & (n-1)) == 0`  |
| Find missing number in range   | XOR Pattern      | Bit Ops           | Use full XOR tricks |
| Subset generation              | Bitmasking       | Bitmask           | Loop 0 to 2^n - 1   |

***

### 🔁 Stack / Queue

| 🧠 Problem Pattern   | 🎯 Pattern      | 📦 Data Structure | 📝 Notes                     |
| -------------------- | --------------- | ----------------- | ---------------------------- |
| Balanced parentheses | Stack           | Stack             | Push for open, pop for close |
| Next greater element | Monotonic Stack | Stack             | Decreasing/Increasing stack  |
| Sliding window max   | Monotonic Queue | Deque             | Maintain max at front        |
| Undo operations      | Stack           | Stack             | Useful in editors, games     |

***

### 🔃 Two Pointers / Sliding Window

| 🧠 Problem Pattern                           | 🎯 Pattern              | 📦 Data Structure | 📝 Notes                          |
| -------------------------------------------- | ----------------------- | ----------------- | --------------------------------- |
| Reverse array/list                           | Two Pointers            | Array, List       | Swap from both ends               |
| Sorted array pair sum                        | Two Pointers            | Array             | Increase/decrease based on target |
| Longest substring/array with at most K chars | Variable Sliding Window | HashMap           | Expand and shrink dynamically     |
| Max sum of fixed size window                 | Fixed Sliding Window    | Array             | Add next, remove previous         |

***

### 📘 Recursion / Backtracking

| 🧠 Problem Pattern        | 🎯 Pattern       | 📦 Data Structure   | 📝 Notes                           |
| ------------------------- | ---------------- | ------------------- | ---------------------------------- |
| Generate all combinations | Backtracking     | Array, Visited\[]   | Use decision tree: pick / not pick |
| N-Queens / Sudoku         | Backtracking     | Matrix + HashSet\[] | Check row, col, diag constraints   |
| Permutations              | Backtracking     | Array + Visited\[]  | Swap or mark-used                  |
| Word Search (2D Grid)     | DFS Backtracking | Matrix              | Mark visited and revert            |

***

### 📐 Sorting / Greedy

| 🧠 Problem Pattern              | 🎯 Pattern             | 📦 Data Structure      | 📝 Notes                  |
| ------------------------------- | ---------------------- | ---------------------- | ------------------------- |
| Activity selection / Max events | Greedy + Sorting       | Array                  | Sort by end time          |
| Merge overlapping intervals     | Sorting + Two Pointers | ArrayList              | Sort, then merge adjacent |
| Min number of platforms         | Sweep Line             | Sort + prefix counters | Count overlaps            |
| Fractional knapsack             | Greedy                 | Sort + math            | Value-to-weight ratio     |

***

### 🧠 Dynamic Programming

| 🧠 Problem Pattern    | 🎯 Pattern    | 📦 Data Structure    | 📝 Notes                  |
| --------------------- | ------------- | -------------------- | ------------------------- |
| Min cost / Max profit | DP (1D or 2D) | Array / Table        | Memo or Tabulate          |
| LCS / LIS / LPS       | DP            | 2D Matrix / 1D array | Based on subproblem table |
| Knapsack / Subset sum | DP            | 2D DP array          | Include/Exclude style     |
| Palindromic substring | DP + 2D Table | Table                | Expand if ends match      |

***

### 🌐 Graphs

| 🧠 Problem Pattern           | 🎯 Pattern               | 📦 Data Structure             | 📝 Notes                      |
| ---------------------------- | ------------------------ | ----------------------------- | ----------------------------- |
| Shortest path unweighted     | BFS                      | Queue + Adjacency List        | First hit gives shortest      |
| Shortest path weighted       | Dijkstra                 | MinHeap + Map                 | Use PriorityQueue             |
| Course schedule / Dependency | Topological Sort         | Queue + In-degree map         | Only for DAG                  |
| Detect cycle in directed     | DFS with recursion stack | Graph + visited\[]            | Back edges = cycle            |
| Number of islands            | DFS / BFS                | Grid + visited\[]\[]          | Count components              |
| Chessboard shortest path     | BFS                      | Matrix + Knight moves         | 8 directions                  |
| Snake and Ladder             | BFS                      | Queue + Map (position → jump) | Treat as graph nodes          |
| Word Ladder                  | BFS                      | Queue + Dictionary            | Transform word each level     |
| Graph Connected Components   | DFS / Union-Find         | Array + parent\[]             | Union by rank + path compress |

***

### 📦 Trees / Tries / Heaps

| 🧠 Problem Pattern            | 🎯 Pattern     | 📦 Data Structure | 📝 Notes                 |
| ----------------------------- | -------------- | ----------------- | ------------------------ |
| Top-K frequent                | Heap + HashMap | PriorityQueue     | Sort by frequency        |
| Autocomplete / Prefix search  | Trie           | TrieNode\[]       | Insert/startsWith/search |
| LCA, Max Depth, Balanced Tree | DFS Traversal  | Recursion         | Postorder useful         |
| Serialize/Deserialize         | BFS / DFS      | Queue or Stack    | Pre/In/Post traversal    |
| Median of stream              | Two Heaps      | MaxHeap + MinHeap | Balance left/right heaps |

***

### 🧩 Advanced / Game-Based Patterns

| 🧠 Problem Pattern          | 🎯 Pattern         | 📦 Data Structure          | 📝 Notes                           |
| --------------------------- | ------------------ | -------------------------- | ---------------------------------- |
| Chessboard Knight min moves | BFS                | Matrix + Queue             | Move in 8 directions               |
| Snake and Ladder min rolls  | BFS                | Queue + Board map          | Map board positions as graph nodes |
| Sliding Puzzle (3x3 board)  | BFS + String state | Queue + HashSet            | Use stringified board state        |
| Minimum jumps to reach end  | Greedy / BFS       | Queue / DP                 | Track maxReach, jumps              |
| Game of Life                | Matrix Marking     | Matrix (in-place update)   | Use 0→2 or 1→3 as temp state       |
| N-Queens                    | Backtracking       | Board + Diag tracking      | Use arrays for columns, diags      |
| Multi-source BFS            | BFS                | Queue with multiple starts | Push all sources at once           |
| Minimum genetic mutation    | BFS                | Queue + Gene dict          | Each gene as node in graph         |

#### 🧭 Input-Based Code Snippet Selector

***

**📥 Input: Array**

| 🔍 Problem Pattern             | 💡 Apply This        | 🔧 Code Idea                                 |
| ------------------------------ | -------------------- | -------------------------------------------- |
| Find pair with sum in sorted   | Two Pointers         | `while (l < r) { sum = arr[l]+arr[r]; }`     |
| Find pair with sum in unsorted | HashSet              | `set.contains(target - num)`                 |
| Subarray sum equals K          | Prefix Sum + HashMap | `map.put(sum, index); map.contains(sum - k)` |
| Kth largest                    | Min Heap (size K)    | `PQ.offer(num); if (PQ.size > k) PQ.poll();` |

***

**📥 Input: String**

| 🔍 Problem Pattern               | 💡 Apply This         | 🔧 Code Idea                                        |
| -------------------------------- | --------------------- | --------------------------------------------------- |
| Longest substring without repeat | Sliding Window        | `while (set.contains(char)) { set.remove(); }`      |
| All anagrams of pattern          | Sliding Window + Freq | `match when freq == 0`                              |
| Is Palindrome                    | Two Pointers          | `while (l < r) if (s[l++] != s[r--]) return false;` |

***

**📥 Input: Linked List**

| 🔍 Problem Pattern | 💡 Apply This        | 🔧 Code Idea                               |
| ------------------ | -------------------- | ------------------------------------------ |
| Detect cycle       | Fast & Slow Pointers | `slow = slow.next; fast = fast.next.next;` |
| Find middle        | Fast & Slow Pointers | `if (fast != null && fast.next != null)`   |
| Reverse list       | Iteration            | `prev = null; while (node != null) {}`     |

***

**📥 Input: Matrix/Grid**

| 🔍 Problem Pattern      | 💡 Apply This | 🔧 Code Idea                       |
| ----------------------- | ------------- | ---------------------------------- |
| Count islands / regions | DFS / BFS     | `dfs(i, j); visited[i][j] = true;` |
| Shortest path in grid   | BFS           | `queue.offer([x, y, steps])`       |
| Knight shortest move    | BFS + 8 dirs  | `for (dir : directions)`           |

***

**📥 Input: Tree**

| 🔍 Problem Pattern           | 💡 Apply This        | 🔧 Code Idea                                      |
| ---------------------------- | -------------------- | ------------------------------------------------- |
| Inorder traversal            | DFS Recursion        | `inorder(root.left); visit; inorder(root.right);` |
| Max depth                    | DFS                  | `1 + max(dfs(left), dfs(right))`                  |
| Lowest Common Ancestor (BST) | Recursion            | `if (p < root && q < root) → left`                |
| Vertical / Top View          | Level-order + Column | `Map<col, List<Node>>`                            |

***

**📥 Input: Graph**

| 🔍 Problem Pattern        | 💡 Apply This     | 🔧 Code Idea                          |
| ------------------------- | ----------------- | ------------------------------------- |
| Shortest path unweighted  | BFS               | `queue.add(start); visited.add()`     |
| Detect cycle (undirected) | Union Find / DFS  | `if (find(u) == find(v)) → cycle`     |
| Topological Sort (DAG)    | Kahn’s Algo       | `if (indegree[v] == 0) queue.add(v);` |
| Connected components      | DFS or Union Find | `dfs(node); visited.add(node)`        |

***

**📥 Input: Dictionary / Word List**

| 🔍 Problem Pattern  | 💡 Apply This      | 🔧 Code Idea                                             |
| ------------------- | ------------------ | -------------------------------------------------------- |
| Word transformation | BFS with word bank | `queue.offer([word, steps]); dict.remove(word)`          |
| Prefix lookup       | Trie               | `curr = curr.children[c - 'a'];`                         |
| Word Search in Grid | DFS + Backtracking | `visited[i][j] = true; dfs(...); visited[i][j] = false;` |

***

**📥 Input: Number**

| 🔍 Problem Pattern   | 💡 Apply This    | 🔧 Code Idea                                  |
| -------------------- | ---------------- | --------------------------------------------- |
| Power of 2           | Bit Manipulation | `(n & (n - 1)) == 0`                          |
| Find missing number  | XOR trick        | `xor = xor ^ i ^ nums[i]`                     |
| Generate all subsets | Bitmasking       | `for (int mask = 0; mask < (1 << n); mask++)` |

***

**📥 Input: Game Board / Puzzle**

| 🔍 Problem Pattern    | 💡 Apply This       | 🔧 Code Idea                                 |
| --------------------- | ------------------- | -------------------------------------------- |
| Snake & Ladder        | BFS                 | `queue.offer(cell + dice); board jump logic` |
| 3x3 Sliding Puzzle    | BFS + State Hashing | `visited.add(boardString);`                  |
| Chessboard Knight BFS | BFS + 8 directions  | `newX = x + dx[i]; newY = y + dy[i]`         |

***

**📥 Input: Range Updates / Queries**

| 🔍 Problem Pattern       | 💡 Apply This       | 🔧 Code Idea                             |
| ------------------------ | ------------------- | ---------------------------------------- |
| Static sum query         | Prefix Sum          | `prefix[i] = prefix[i-1] + A[i]`         |
| Dynamic sum query/update | Segment Tree        | `build(node), update(node), query(node)` |
| Frequency over range     | Binary Indexed Tree | `i += (i & -i)` or `i -= (i & -i)`       |

<figure><img src=".gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>
