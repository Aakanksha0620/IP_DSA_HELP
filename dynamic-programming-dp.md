# Dynamic Programming (DP)

## 📘 Module 11: Dynamic Programming (DP) – “Divide, Remember, Conquer”

***

### 📍1. DECISION DIAGRAM – When to Use DP

```
textCopyEdit                        ┌──────────────┐
                        │  Problem Qn? │
                        └─────┬────────┘
                              │
        ┌────────────────────┴────────────────────┐
        ▼                                          ▼
 Does it have optimal substructure?       Do you repeat subproblems?
  (Can solution be broken down?)       (Do recursive calls repeat work?)
        │                                          │
      YES                                      YES
        │                                          │
   ┌────┴─────┐                             ┌──────┴─────┐
   ▼          ▼                             ▼            ▼
Top-Down   Bottom-Up                    1D/2D Table   State Compression
(Memo)      (Tab)                      (Tabulation)   (Space Optimize)
```

> 🔍 Tip: Use DP when you notice **overlapping subproblems** and **optimal substructure**.

***

### 🧠2. FLASHCARD – DP Building Blocks

| Concept                    | Description                                      |
| -------------------------- | ------------------------------------------------ |
| 🔁 Overlapping Subproblems | Reuse results of subcalls                        |
| ⚖️ Optimal Substructure    | Problem = best of smaller subproblems            |
| 🧠 Memoization             | Top-down + Cache                                 |
| 📋 Tabulation              | Bottom-up iteration                              |
| 🔢 State Variables         | Define what each state stores                    |
| ⏬ State Transition         | Formula to go from smaller to bigger subproblems |

> 🔖 Mnemonic: **"MOST STS"** – Memoization, Optimal, Substructure, Tabulation, States, Transitions

***

### 📚3. DP PATTERNS & TEMPLATES

#### ✳️ Memoization Template (Top-Down)

```java
javaCopyEditint dp(int i, int j) {
    if (i < 0 || j < 0) return 0;
    if (memo[i][j] != -1) return memo[i][j];
    return memo[i][j] = ...recursive formula...;
}
```

***

#### ✳️ Tabulation Template (Bottom-Up)

```java
javaCopyEditint[][] dp = new int[n+1][m+1];
for (int i = 1; i <= n; i++) {
    for (int j = 1; j <= m; j++) {
        dp[i][j] = ...transition logic...;
    }
}
```

***

#### ✳️ 1D Space Optimization

```java
javaCopyEditint[] prev = new int[n+1];
int[] curr = new int[n+1];
for (...) {
    for (...) {
        curr[i] = ...prev[i-1]...
    }
    prev = curr;
}
```

***

### 🧩4. DP PROBLEM CLASSIFICATION

| Pattern          | Examples                               |
| ---------------- | -------------------------------------- |
| 🧱 1D Linear DP  | Fibonacci, Climbing Stairs             |
| 🔀 Subsequence   | LCS, LIS, Edit Distance                |
| 📦 Knapsack      | 0/1, Unbounded, Subset Sum             |
| 📊 Partition     | Equal Subset Sum, Palindrome Partition |
| 🗺️ Grid DP      | Unique Paths, Min Path Sum             |
| 🎯 Game Strategy | Stone Game, Predict Winner             |
| ⏱️ Scheduling    | Job Scheduling, Burst Balloons         |

***

### 🔄5. MISTAKES TO AVOID

| Mistake                     | Tip                                |
| --------------------------- | ---------------------------------- |
| Recomputing subproblems     | Always use memo table              |
| Incorrect base cases        | Write base condition carefully     |
| Wrong dimension of DP table | Define states explicitly           |
| Copy-paste transitions      | Understand problem structure first |

***

### 🧩6. CURATED PROBLEM SET

#### ✅ Easy (10)

1. Fibonacci Number (LC 509)
2. Climbing Stairs (LC 70)
3. House Robber (LC 198)
4. Min Cost Climbing Stairs (LC 746)
5. Unique Paths (LC 62)
6. Max Subarray Sum (LC 53)
7. Count Ways to Reach Nth Stair
8. Tribonacci Number (LC 1137)
9. Number of Dice Rolls with Target Sum
10. Decode Ways (LC 91)

***

#### 🟡 Medium (10)

1. Longest Common Subsequence (LC 1143)
2. Longest Increasing Subsequence (LC 300)
3. Edit Distance (LC 72)
4. Coin Change (LC 322)
5. 0/1 Knapsack
6. Partition Equal Subset Sum (LC 416)
7. Palindromic Substrings (LC 647)
8. Matrix Chain Multiplication
9. Interleaving Strings (LC 97)
10. Longest Palindromic Subsequence (LC 516)

***

#### 🔴 Hard (10)

1. Burst Balloons (LC 312)
2. Regular Expression Matching (LC 10)
3. Wildcard Matching (LC 44)
4. Palindrome Partitioning II (LC 132)
5. Minimum Cost to Merge Stones (LC 1000)
6. Paint House III (LC 1473)
7. Maximum Profit in Job Scheduling (LC 1235)
8. Number of Longest Increasing Subsequence
9. Scramble String (LC 87)
10. Minimum Insertion Steps to Make Palindrome

***

### ❓7. QUIZ – DP DETECTOR

1. **"Does the problem reuse same subproblems?"**\
   ➤ Yes → Try Memoization or Tabulation ✅\
   ➤ No → May not need DP
2. **"Does greedy fail?"**\
   ➤ Yes → Try DP ✅\
   ➤ No → Try Greedy first
3. **"Fibonacci computation is slow. How to fix?"**\
   ➤ Use Memoization ✅\
   ➤ Use Recursion\
   ➤ Use Brute Force
4. **"Problem involves choice: include/exclude"**\
   ➤ Likely DP ✅\
   ➤ Use Heap

***

### 🧠8. FEYNMAN REFLECTION PROMPTS

* What makes a problem suitable for DP?
* Why do we memoize return values?
* Can you convert a recursive problem into iterative DP?
* When can space be optimized in DP?
