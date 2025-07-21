# The Ultimate DSA Pattern Framework Table

### 🧠 The Ultimate DSA Pattern Framework Table (All 25 Patterns)

| #  | **Pattern**                   | **When to Use**                                           | **Typical Problems**                            | **Complexity Benefit**            |
| -- | ----------------------------- | --------------------------------------------------------- | ----------------------------------------------- | --------------------------------- |
| 1  | **Two Pointers**              | Sorted arrays, reverse, sum problems, moving ends         | 2Sum, Reverse String, Remove Duplicates         | O(n) vs O(n²)                     |
| 2  | **Sliding Window**            | Subarrays, strings, max/min sum, longest unique substring | Max Sum Subarray, Anagrams in String            | O(n) vs O(n²)                     |
| 3  | **Fast & Slow Pointers**      | Detecting cycles                                          | Linked List Cycle, Happy Number                 | O(n) with O(1) space              |
| 4  | **Merge Intervals**           | Overlapping intervals                                     | Merge Intervals, Insert Interval                | O(n log n)                        |
| 5  | **Cyclic Sort**               | Numbers in range \[1...n]                                 | Missing Number, Duplicate Number                | O(n)                              |
| 6  | **In-place Reversal**         | Reverse arrays, linked list sections                      | Reverse LL, Reverse Words in String             | O(n), O(1) space                  |
| 7  | **Tree BFS**                  | Level order traversal                                     | Binary Tree Level Order                         | O(n)                              |
| 8  | **Tree DFS**                  | All paths, root-to-leaf, subtree recursion                | Path Sum, Diameter of Tree                      | O(n)                              |
| 9  | **Two Heaps**                 | Median, balance two halves                                | Median of Data Stream, Sliding Window Median    | O(log n) per insertion            |
| 10 | **Subsets (Backtracking)**    | All combinations/subsets                                  | Subsets, Combination Sum                        | O(2ⁿ)                             |
| 11 | **Modified Binary Search**    | Rotated arrays, condition-based search                    | Search Rotated Array, First/Last Position       | O(log n)                          |
| 12 | **Bitwise Tricks**            | XOR-based unique values, toggling bits                    | Single Number, Missing Number                   | O(n), O(1)                        |
| 13 | **Top K Elements (Heap)**     | K-largest/frequent, near-real-time ranking                | Top K Frequent, Kth Largest                     | O(n log k)                        |
| 14 | **K-way Merge**               | Merge k sorted lists, arrays, streams                     | Merge K Sorted Lists, Smallest Range Covering K | O(n log k)                        |
| 15 | **0/1 Knapsack (DP)**         | Choose or skip items, one-time pick                       | Knapsack, Target Sum                            | O(n × sum)                        |
| 16 | **Unbounded Knapsack (DP)**   | Reuse items unlimited times                               | Coin Change, Rod Cutting                        | O(n × sum)                        |
| 17 | **Fibonacci Pattern (DP)**    | Recurrence-based with overlapping subproblems             | Climbing Stairs, House Robber                   | O(n), O(1) space                  |
| 18 | **Palindromic Substrings**    | Substring logic with DP/memoization                       | Longest Palindromic Substring                   | O(n²)                             |
| 19 | **LCS / DP Grid**             | Compare strings for longest match, edit distance          | LCS, Edit Distance                              | O(m×n)                            |
| 20 | **Topological Sort (Graph)**  | Scheduling, order of tasks                                | Course Schedule, Alien Dictionary               | O(V + E)                          |
| 21 | **Union Find (Disjoint Set)** | Detect connected components, cycles                       | Graph Valid Tree, Redundant Connection          | O(α(n)) amortized                 |
| 22 | **Backtracking**              | Explore all solutions with constraint pruning             | N-Queens, Sudoku Solver                         | O(kⁿ), pruned with backtracking   |
| 23 | **Trie Pattern**              | Prefix-based matching, autocomplete, dictionary           | Word Search, Replace Words                      | O(m) insert/search                |
| 24 | **Greedy**                    | Choose local optimal to get global optimum                | Activity Selection, Jump Game                   | Varies (often O(n log n) or O(n)) |
| 25 | **Monotonic Stack/Queue**     | Next Greater Element, histogram/bar-based problems        | Largest Rectangle, Stock Span                   | O(n)                              |

***

#### 📘 Summary by Category

| **Category**              | **Patterns**                                                         |
| ------------------------- | -------------------------------------------------------------------- |
| **Array & String**        | Two Pointers, Sliding Window, Cyclic Sort, In-Place Reversal         |
| **Linked List**           | Fast & Slow Pointers, Reversal                                       |
| **Tree & Recursion**      | Tree BFS, Tree DFS, Backtracking, Fibonacci DP                       |
| **Heap & Priority**       | Top K Elements, Two Heaps, K-way Merge                               |
| **DP & Combinatorics**    | 0/1 Knapsack, Unbounded Knapsack, LCS, Palindrome, Fibonacci Pattern |
| **Graph**                 | BFS/DFS, Topological Sort, Union Find                                |
| **Trie & Prefix Search**  | Trie Pattern                                                         |
| **Greedy & Optimization** | Greedy, Monotonic Stack                                              |
| **Bit Manipulation**      | Bitwise Tricks                                                       |
| **Advanced Arrays**       | Merge Intervals, Modified Binary Search                              |

<figure><img src="../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

#### 🧭 How to Use the Diagram

* When you see a question, ask: "What is the **structure** of the input?" (sorted array, string, graph, tree, etc.)
* Then ask: "What is the **goal**?" (max sum, all subsets, detect cycle, etc.)
* Follow that branch on the mind map to get the matching pattern!

<figure><img src="../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>
