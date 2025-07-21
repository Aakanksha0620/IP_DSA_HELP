# Quiz

## 🧪 Pattern-Based Quizzes (with Answers & Explanations)

Each pattern includes:

* 3–5 questions (MCQs or true/false)
* Immediate answers with mini-explanations\
  Perfect for self-checks or team discussions!

***

### 🔁 **1. Sliding Window**

**Q1.** Which of these is the best fit for sliding window?\
A. Rotate matrix\
B. Longest substring with at most K distinct characters\
C. Find LCA in a tree\
D. Merge two sorted lists\
✅ **Answer: B**\
**Explanation:** Sliding window handles subarray/substring with size or constraints.

***

**Q2.** What’s the time complexity of a variable size sliding window approach with HashSet?\
A. O(n²)\
B. O(n)\
C. O(n log n)\
D. O(1)\
✅ **Answer: B**\
**Explanation:** Each character is added/removed from set once.

***

**Q3.** True or False: Sliding window only works on sorted arrays.\
✅ **Answer: False**\
**Explanation:** Works on both sorted/unsorted data — key is consecutive elements.

***

### 👬 **2. Two Pointers**

**Q1.** When are two pointers most effective?\
A. When data is randomized\
B. When array is sorted\
C. When elements are unique\
D. When elements are in reverse\
✅ **Answer: B**

***

**Q2.** Which two-pointer pattern is used in palindrome check?\
✅ **Answer: Move inward from both ends and compare elements**

***

**Q3.** What happens if left pointer passes right pointer?\
A. Array is reversed\
B. Subarray is invalid\
C. End of search\
✅ **Answer: C**

***

### ⏩ **3. Fast & Slow Pointers**

**Q1.** Which is **not** a typical use case?\
A. Linked list cycle\
B. Middle of array\
C. Palindrome string\
D. Min heap\
✅ **Answer: D**

***

**Q2.** In cycle detection, when do we reset one pointer to head?\
✅ **Answer: After slow == fast, reset one to head to find cycle start**

***

### 🔄 **4. Backtracking**

**Q1.** When to use backtracking?\
A. When subproblems are independent\
B. When we want all possible combinations\
✅ **Answer: B**

***

**Q2.** What must always happen during backtracking?\
A. Sorting\
B. Reset the visited/used state\
C. Binary Search\
✅ **Answer: B**

***

**Q3.** Backtracking is best suited when:\
A. Answer must be unique\
B. Answer must include all permutations\
✅ **Answer: B**

***

### 🔍 **5. Binary Search**

**Q1.** Binary Search works on:\
A. Any data\
B. Sorted data\
✅ **Answer: B**

***

**Q2.** When solving "minimum possible answer" style problems, we use:\
A. Binary Search on index\
B. Binary Search on answer space\
✅ **Answer: B**

***

### 📈 **6. Dynamic Programming**

**Q1.** Which two conditions justify DP usage?\
✅ **Answer: Optimal Substructure + Overlapping Subproblems**

***

**Q2.** What is memoization?\
A. Bottom-up table\
B. Top-down + cache\
✅ **Answer: B**

***

**Q3.** True or False: All recursive problems can be solved using DP.\
✅ **Answer: False**\
**Explanation:** Only when the recursion overlaps significantly.

***

### 🧮 **7. Bit Manipulation**

**Q1.** What does `(n & (n - 1)) == 0` check?\
A. If n is prime\
B. If n is power of 2\
✅ **Answer: B**

***

**Q2.** Bitmasking is used when:\
A. We need exact sums\
B. Subsets represented as binary\
✅ **Answer: B**

***

### ⛓ **8. Union Find (Disjoint Set)**

**Q1.** What’s the time complexity of union/find with path compression?\
✅ **Answer: Almost O(1)** (Inverse Ackermann)

***

**Q2.** What’s the goal of union-by-rank?\
A. Make sets smaller\
B. Flatten tree height\
✅ **Answer: B**

***

### 🧠 **9. Graphs (BFS/DFS)**

**Q1.** BFS finds the:\
A. Longest path\
B. All paths\
C. Shortest path (unweighted)\
✅ **Answer: C**

***

**Q2.** DFS is preferred when:\
A. All neighbors at same level\
B. We want to go deep\
✅ **Answer: B**

***

### 🔃 **10. Greedy**

**Q1.** Greedy algorithms work best when:\
A. We need all combinations\
B. Local optimal choices lead to global optimum\
✅ **Answer: B**

***

**Q2.** Which problem is classically solved using greedy?\
A. Longest Increasing Subsequence\
B. Fractional Knapsack\
✅ **Answer: B**

***

**Q3.** True or False: Greedy algorithms always give optimal solutions.\
✅ **Answer: False**\
**Explanation:** Only work when the problem exhibits the **greedy-choice property**.

***

### 📚 **11. Trie**

**Q1.** What’s the average time to search in a trie?\
A. O(1)\
B. O(log N)\
C. O(L), where L = length of word\
✅ **Answer: C**

***

**Q2.** Tries are NOT suitable for:\
A. Prefix search\
B. Suffix search\
✅ **Answer: B**

***

**Q3.** Trie nodes typically store:\
A. Values\
B. Array of characters (children)\
✅ **Answer: B**

***

### ⏫ **12. Heap / Priority Queue**

**Q1.** A min-heap guarantees:\
✅ **Answer: The smallest element is at the top**

***

**Q2.** Which is best for “find top K frequent elements”?\
A. HashMap\
B. Max Heap\
✅ **Answer: B**

***

**Q3.** What’s the time complexity of insertion/deletion in heap?\
✅ **Answer: O(log N)**

***

### 🔢 **13. Bitmasking**

**Q1.** Which pattern is best for representing subsets?\
✅ **Answer: Bitmasking**

***

**Q2.** `mask & (1 << i)` checks:\
✅ **Answer: If bit i is set**

***

**Q3.** `mask | (1 << i)` does what?\
✅ **Answer: Sets the i-th bit in mask**

***

### 🧱 **14. Segment Tree / Fenwick Tree**

**Q1.** Which is better for dynamic range sum queries with updates?\
✅ **Answer: Segment Tree or Binary Indexed Tree (Fenwick Tree)**

***

**Q2.** What’s the time complexity for update/query in Segment Tree?\
✅ **Answer: O(log N)**

***

**Q3.** When is prefix sum array NOT enough?\
✅ **Answer: When frequent updates to elements are required**

***

### 🎮 **15. BFS for Games / Board Problems**

**Q1.** What pattern is best for Snake & Ladder, Knight Moves?\
✅ **Answer: BFS**

***

**Q2.** In BFS grid problems, we track visited states using:\
✅ **Answer: A matrix or HashSet of positions/states**

***

**Q3.** What is key to solving a 3x3 sliding puzzle?\
✅ **Answer: Serialize the board to a string and use BFS**
