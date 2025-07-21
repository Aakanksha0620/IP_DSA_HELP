# Greedy Algorithms

## 📘 Module 10: Greedy Algorithms – “Always Pick the Best… for Now”

***

### 📍1. DECISION DIAGRAM – When to Use Greedy

```
textCopyEdit                    ┌──────────────┐
                    │  Problem Qn? │
                    └─────┬────────┘
                          │
        ┌─────────────────┴────────────────────┐
        ▼                                      ▼
Can local decisions lead to optimum?     Problem asks for max/min/cost?
  (e.g., pick lowest/highest value)     (activity selection, coin change)
        │                                      │
 Try Greedy Strategy                     Try Greedy + Sort or Heap
        │                                      │
  ┌─────┴────────────┐               ┌─────────┴─────────┐
  ▼                  ▼               ▼                   ▼
Sort by end time     Use heap       Use custom logic     Check feasibility
(Activity selection) (Interval merge) (Frequency, deadlines)
```

> 🔍 Tip: Use greedy when you're choosing **"best for the current step"** and it leads to global optimum **without backtracking**.

***

### 🧠2. FLASHCARD – Greedy Essentials

| Concept                    | Use Case                         |
| -------------------------- | -------------------------------- |
| ⏳ Activity Selection       | Pick task with earliest end time |
| 💰 Fractional Knapsack     | Take max value/weight ratio      |
| 🎟️ Huffman Coding         | Greedy + heap for compression    |
| 🔢 Coin Change             | Greedy if denominations allow    |
| 📆 Interval Problems       | Sort + pick wisely               |
| 📈 Increasing Subsequences | Greedy + binary search           |

> 🔖 Mnemonic: **"ASCHIC"** – Activity, Scheduling, Coin, Huffman, Intervals, Choices

***

### 📚3. GREEDY STRATEGY PATTERNS

#### ✳️ Activity Selection (Earliest Finish First)

```java
javaCopyEditArrays.sort(activities, (a, b) -> a.end - b.end);
int count = 1, lastEnd = activities[0].end;

for (int i = 1; i < n; i++) {
    if (activities[i].start >= lastEnd) {
        count++;
        lastEnd = activities[i].end;
    }
}
```

***

#### ✳️ Huffman Encoding

```
textCopyEdit1. Use Min-Heap to store characters by frequency
2. While heap has more than one node:
   - Remove 2 min freq nodes
   - Create new node with sum of freqs
   - Push new node into heap
3. Final node is root of Huffman Tree
```

***

#### ✳️ Job Scheduling with Deadlines

```java
javaCopyEdit1. Sort jobs by profit descending
2. Use array to mark time slots up to deadline
3. If free slot found, assign and add profit
```

***

### 🔄4. MISTAKES TO AVOID

| Mistake                       | Tip                                                    |
| ----------------------------- | ------------------------------------------------------ |
| Assuming greedy always works  | Prove greedy optimality or use DP                      |
| Forgetting sort order         | Sorting by wrong field breaks logic                    |
| Using greedy for 0/1 Knapsack | Use DP instead                                         |
| Not handling edge cases       | Handle tie-breakers and intervals with equal start/end |

***

### 🧩5. CURATED PROBLEM SET

#### ✅ Easy (10)

1. Activity Selection Problem (GFG)
2. Minimum Platforms (GFG)
3. Assign Cookies (LC 455)
4. Non-overlapping Intervals (LC 435)
5. Can Place Flowers (LC 605)
6. Lemonade Change (LC 860)
7. Max Units on a Truck (LC 1710)
8. Minimize the Heights I (GFG)
9. Is Subsequence (LC 392)
10. Distribute Candies (LC 575)

***

#### 🟡 Medium (10)

1. Jump Game (LC 55)
2. Gas Station (LC 134)
3. Task Scheduler (LC 621)
4. Partition Labels (LC 763)
5. Queue Reconstruction by Height (LC 406)
6. Minimum Number of Arrows to Burst Balloons (LC 452)
7. Merge Intervals (LC 56)
8. Buy and Sell Stock II (LC 122)
9. Reorganize String (LC 767)
10. Minimum Swaps to Group All 1s Together (LC 1703)

***

#### 🔴 Hard (10)

1. Trapping Rain Water (LC 42) – tricky greedy + two pointers
2. Candy Distribution (LC 135)
3. Remove Duplicate Letters (LC 316)
4. IPO (LC 502)
5. Create Sorted Array through Instructions (LC 1649)
6. Minimum Cost to Hire K Workers (LC 857)
7. Strong Password Checker (LC 420)
8. Maximum Performance of a Team (LC 1383)
9. Path with Minimum Effort (LC 1631)
10. Minimum Cost to Connect Sticks (LC 1167)

***

### ❓6. QUIZ – GREEDY INTUITION CHECK

1. **"Select max number of non-overlapping activities"**\
   a. DFS\
   b. Sort by end time ✅\
   c. BFS
2. **"Is greedy valid for 0/1 Knapsack?"**\
   a. Yes\
   b. No ✅\
   c. Depends on values
3. **"When does greedy fail in coin change?"**\
   a. When all denominations are multiples\
   b. When greedy doesn't lead to fewest coins ✅\
   c. Never
4. **"When is Huffman Coding used?"**\
   a. Compression ✅\
   b. Sorting\
   c. Searching

***

### 🧠7. FEYNMAN REFLECTION PROMPTS

* How do you prove a greedy algorithm is optimal?
* Why does sorting matter before greedy steps?
* When is greedy better than DP? When is it not?
* Can you reduce a DP problem into a greedy one?
