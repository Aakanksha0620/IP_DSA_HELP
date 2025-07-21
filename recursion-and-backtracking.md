# Recursion & Backtracking

## 📘 Module 4: Recursion & Backtracking – “Think Deep, Then Prune Smart”

***

### 📍1. DECISION DIAGRAM – When to Use Recursion or Backtracking

```
textCopyEdit                   ┌──────────────┐
                   │ Problem Qn? │
                   └──────┬──────┘
                          │
         ┌────────────────┴────────────────┐
         ▼                                 ▼
     Is problem reducible?          Do all combinations matter?
         (Divide into subproblems)     (e.g., subsets, permutations)
         │                                 │
      Use Recursion                  Use Backtracking
         │                                 │
  ┌──────┴───────┐               ┌─────────┴─────────┐
  ▼              ▼               ▼                   ▼
 Tree/Divide     Memoizable?    Constraints?     Prune Paths?
  & Conquer     Use DP/Memoize   Use Backtrack    Add Conditions
```

***

### 🧠2. FLASHCARD – Mastering Recursion & Backtracking

| Concept                      | Use Case                                      |
| ---------------------------- | --------------------------------------------- |
| 🔁 Recursion                 | Problems that follow "Do & Recurse" structure |
| 📚 Backtracking              | Try all options, undo choices (e.g., Sudoku)  |
| 🧠 Memoization               | Avoid recomputing overlapping subproblems     |
| 🧩 Permutation / Combination | Choose or don’t choose path                   |
| ⛔ Pruning                    | Cut down invalid states early                 |
| 📐 DFS with constraints      | Board/grid/graph-based exploration            |

> 🔖 Mnemonic: "**ReBeMP** – Recurse, Backtrack, Memoize, Prune"

***

### 📚3. PROBLEM-SOLVING HEURISTICS

#### ✳️ Recursion Template

```java
javaCopyEditvoid recurse(args...) {
    if (base case) return;
    
    // recursive step
    recurse(updated args...);
}
```

***

#### ✳️ Backtracking Template

```java
javaCopyEditvoid backtrack(List<List<Integer>> result, List<Integer> temp, boolean[] used) {
    if (temp.size() == nums.length) {
        result.add(new ArrayList<>(temp));
        return;
    }

    for (int i = 0; i < nums.length; i++) {
        if (used[i]) continue;

        used[i] = true;
        temp.add(nums[i]);

        backtrack(result, temp, used);

        // backtrack
        used[i] = false;
        temp.remove(temp.size() - 1);
    }
}
```

***

### 🔄4. MISTAKES TO AVOID

| Mistake                | Tip                                       |
| ---------------------- | ----------------------------------------- |
| Missing base case      | Always write base case first              |
| Modifying global state | Use `temp.remove()` to undo changes       |
| Infinite recursion     | Use print/logs to trace the call          |
| Incorrect pruning      | Ensure pruning doesn’t skip valid results |

***

### 🧩5. CURATED PROBLEM SET

#### ✅ Easy (10)

1. Factorial Using Recursion
2. Fibonacci Using Recursion
3. Print All Subsets of a Set
4. Generate Binary Strings of Length N
5. Power of a Number (Recursively)
6. Print Numbers from 1 to N
7. Reverse a String Recursively
8. Sum of Digits of a Number
9. Tower of Hanoi
10. Count Ways to Climb Stairs (Recursive)

***

#### 🟡 Medium (10)

1. Subsets (LC 78)
2. Permutations (LC 46)
3. Letter Combinations of a Phone Number (LC 17)
4. Combination Sum (LC 39)
5. Generate Parentheses (LC 22)
6. Palindrome Partitioning (LC 131)
7. Word Search (LC 79)
8. Sudoku Solver (LC 37)
9. N-Queens Problem
10. Restore IP Addresses (LC 93)

***

#### 🔴 Hard (10)

1. Word Break II (LC 140)
2. Regular Expression Matching (LC 10)
3. Unique Paths III (LC 980)
4. Expression Add Operators (LC 282)
5. Matchsticks to Square (LC 473)
6. Crossword Puzzle Solver
7. K-th Permutation Sequence
8. Count All Possible Paths (Obstacle Maze)
9. Remove Invalid Parentheses (LC 301)
10. Partition to K Equal Sum Subsets (LC 698)

***

### ❓6. QUIZ – RECURSION REALITY CHECK

> Pick the right tool:

1. **"Solve N-Queens problem"**\
   a. Recursion\
   b. Backtracking ✅\
   c. BFS
2. **"Generate all permutations of array"**\
   a. Greedy\
   b. DFS\
   c. Backtracking ✅
3. **"Fibonacci with optimization"**\
   a. Simple Recursion\
   b. Recursion + Memoization ✅\
   c. BFS
4. **"Check if string can be broken using dictionary words"**\
   a. Trie\
   b. Backtracking\
   c. DP or Backtracking ✅

***

### 🧠7. FEYNMAN REFLECTION PROMPTS

* What makes recursion different from backtracking?
* When do you need to prune a recursive tree?
* Why is memoization powerful with recursion?
* Can all backtracking problems be solved using iteration?
