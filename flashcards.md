# Flashcards

## 🔁 Flashcards with Examples for Every DSA Pattern

Each flashcard includes:

* 📘 **Concept**
* 💡 **When to Use**
* 🧪 **Classic Example**

***

#### 1. **Sliding Window**

**📘 Concept:** A subarray or substring moves over the input to track sums, lengths, or conditions.

**💡 When to Use:** “Longest/shortest substring”, “at most k”, “fixed length window”

**🧪 Example:**\
🟢 _Longest Substring Without Repeating Characters_\
👉 Use HashSet + dynamic window

```java
javaCopyEditint left = 0;
for (int right = 0; right < s.length(); right++) {
    while (set.contains(s.charAt(right))) {
        set.remove(s.charAt(left++));
    }
    set.add(s.charAt(right));
    max = Math.max(max, right - left + 1);
}
```

***

#### 2. **Two Pointers**

**📘 Concept:** Use two indices to scan from both ends or in sync.

**💡 When to Use:** Sorted array, reverse logic, or meet-in-the-middle

**🧪 Example:**\
🟢 _Two Sum in Sorted Array_

```java
javaCopyEditint left = 0, right = arr.length - 1;
while (left < right) {
    int sum = arr[left] + arr[right];
    if (sum == target) return new int[]{left, right};
    else if (sum < target) left++;
    else right--;
}
```

***

#### 3. **Fast & Slow Pointers**

**📘 Concept:** Move one pointer faster to detect cycles or mid-points.

**💡 When to Use:** Linked list cycle, palindrome, middle node

**🧪 Example:**\
🟢 _Detect Cycle in Linked List_

```java
javaCopyEditListNode slow = head, fast = head;
while (fast != null && fast.next != null) {
    slow = slow.next;
    fast = fast.next.next;
    if (slow == fast) return true;
}
```

***

#### 4. **Backtracking**

**📘 Concept:** Make a choice, explore, backtrack if needed.

**💡 When to Use:** Permutations, N-Queens, Sudoku, Word Search

**🧪 Example:**\
🟢 _Generate Subsets_

```java
javaCopyEditvoid backtrack(List<List<Integer>> res, List<Integer> temp, int[] nums, int start) {
    res.add(new ArrayList<>(temp));
    for (int i = start; i < nums.length; i++) {
        temp.add(nums[i]);
        backtrack(res, temp, nums, i + 1);
        temp.remove(temp.size() - 1);
    }
}
```

***

#### 5. **Binary Search**

**📘 Concept:** Divide and conquer in a sorted array or search space.

**💡 When to Use:** Sorted arrays, “min/max possible answer”

**🧪 Example:**\
🟢 _Search in Rotated Sorted Array_

```java
javaCopyEditint mid = left + (right - left) / 2;
if (nums[mid] == target) return mid;
// Determine which side is sorted and adjust accordingly
```

***

#### 6. **Dynamic Programming**

**📘 Concept:** Solve overlapping subproblems with optimal structure.

**💡 When to Use:** “Find min/max ways/cost”, recursion with choices

**🧪 Example:**\
🟢 _Fibonacci with DP_

```java
javaCopyEditdp[0] = 0; dp[1] = 1;
for (int i = 2; i <= n; i++) {
    dp[i] = dp[i - 1] + dp[i - 2];
}
```

***

#### 7. **Greedy**

**📘 Concept:** Make local best choice, hope it leads to global optimum.

**💡 When to Use:** Scheduling, intervals, activity selection

**🧪 Example:**\
🟢 _Minimum Number of Platforms_\
Sort arrivals & departures → two pointer approach.

***

#### 8. **DFS / BFS (Graph Traversal)**

**📘 Concept:** DFS explores deep, BFS explores level-wise.

**💡 When to Use:** Shortest path (BFS), Connected Components (DFS)

**🧪 Example:**\
🟢 _Number of Islands_

```java
javaCopyEditfor (each cell) if (grid[i][j] == 1) {
    dfs(i, j); count++;
}
```

***

#### 9. **Topological Sort**

**📘 Concept:** Order of tasks with dependencies (DAG only)

**💡 When to Use:** Course schedule, build systems

**🧪 Example:**\
🟢 _Kahn's Algorithm (BFS)_

```java
javaCopyEditQueue<Integer> q; int[] indegree;
Add all 0-indegree nodes to q
while (!q.isEmpty()) process and reduce indegrees
```

***

#### 10. **Union Find (Disjoint Set)**

**📘 Concept:** Track components or connectedness using root leader

**💡 When to Use:** Cycle detection, friend circles, Kruskal’s MST

**🧪 Example:**\
🟢 _Detect Cycle in Undirected Graph_

```java
javaCopyEditint find(x) → recursively get root with path compression  
union(x, y) → merge by rank
```

***

#### 11. **Trie**

**📘 Concept:** Tree for prefix-based storage

**💡 When to Use:** Autocomplete, Dictionary search, Prefix count

**🧪 Example:**\
🟢 _StartsWith(word)_

```java
javaCopyEditEach node has children[26], move char by char
```

***

#### 12. **Heap (Priority Queue)**

**📘 Concept:** Access min/max element in O(log n)

**💡 When to Use:** Top-K problems, scheduling, Dijkstra

**🧪 Example:**\
🟢 _Kth Largest Element_

```java
javaCopyEditMinHeap of size k → push/pop until full
```

***

#### 13. **Bitmasking**

**📘 Concept:** Represent subset or state as bits

**💡 When to Use:** Subsets, DP with state, toggling

**🧪 Example:**\
🟢 _Count Set Bits_\
`n & (n-1)` removes lowest set bit

***

#### 14. **Segment Tree / Fenwick Tree**

**📘 Concept:** Preprocess array for fast range queries and updates

**💡 When to Use:** Range sum, min/max, frequency over range

**🧪 Example:**\
🟢 _Range Sum Query_

```java
javaCopyEditBuild tree from leaves up, update with parents
```

***

#### 15. **BFS for Games (Board, Grid, Puzzles)**

**📘 Concept:** Level-wise traversal of grid/game state

**💡 When to Use:** Snake & Ladder, Knight move, Sliding Puzzle

**🧪 Example:**\
🟢 _Knight Minimum Moves (Chessboard)_

```java
javaCopyEditBFS from source, move in 8 directions, track visited
```
