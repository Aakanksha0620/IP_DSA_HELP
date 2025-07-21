# Arrays

## 📘 Module 1: Arrays – “Mastering the Foundation of DSA”

***

### 📍1. DECISION DIAGRAM – How to Approach Array Problems

```
textCopyEdit                   ┌──────────────┐
                   │   Array Qn   │
                   └──────┬───────┘
                          │
           ┌──────────────┴──────────────┐
           ▼                             ▼
    Involves Subarray?            Sorted Input or Search?
           │                             │
   ┌───────┴─────────┐           ┌───────┴─────────────┐
   ▼                 ▼           ▼                     ▼
Max/Min/K Sum?    Count Pattern?  Two Sum / Pair?     Search Range?
Sliding Window    Hashing/Prefix  Two Pointers         Binary Search
```

> 🔍 **Tip**: Use the diagram before jumping into code.

***

### 🧠2. FLASHCARD – Mastering Arrays

| Concept           | Use Case                                  |
| ----------------- | ----------------------------------------- |
| 🔄 Prefix Sum     | Range queries, subarray sum               |
| 🪟 Sliding Window | Longest/shortest subarray with conditions |
| 🔢 Two Pointers   | Sorted array, find pair, rearrangement    |
| 🧮 Hash Map       | Count frequencies, duplicates             |
| 📈 Kadane’s Algo  | Maximum subarray sum                      |
| 📦 Partitioning   | Dutch National Flag, rearrangement        |

> 🔖 Mnemonic: “_SH2PK_ – Slide, Hash, Heap, Prefix, Kadane”

***

### 📚3. PROBLEM-SOLVING HEURISTICS

#### ✳️ Pattern 1: Sliding Window

**Trigger**: "longest/shortest subarray", "substring", "sum == K", fixed or variable window\
**Idea**: Expand → Shrink while maintaining invariant

```java
javaCopyEditint i = 0, sum = 0;
for (int j = 0; j < arr.length; j++) {
    sum += arr[j];
    while (sum > K) {
        sum -= arr[i++];
    }
    // update result here
}
```

***

#### ✳️ Pattern 2: Two Pointers

**Trigger**: Sorted input, "find pair", "remove duplicates"\
**Idea**: Start from both ends

```java
javaCopyEditint left = 0, right = arr.length - 1;
while (left < right) {
    int sum = arr[left] + arr[right];
    if (sum == target) return true;
    else if (sum < target) left++;
    else right--;
}
```

***

#### ✳️ Pattern 3: Prefix Sum

**Trigger**: Range sum queries, fixed operations per subarray\
**Idea**: Precompute prefix array

```java
javaCopyEditint[] prefix = new int[n + 1];
for (int i = 1; i <= n; i++)
    prefix[i] = prefix[i-1] + arr[i-1];
```

***

#### ✳️ Pattern 4: Kadane's Algorithm

**Trigger**: Max sum of contiguous subarray\
**Idea**: Running max with reset

```java
javaCopyEditint maxSoFar = arr[0], curr = arr[0];
for (int i = 1; i < arr.length; i++) {
    curr = Math.max(arr[i], curr + arr[i]);
    maxSoFar = Math.max(maxSoFar, curr);
}
```

***

### 🔄4. MISTAKES TO AVOID

| Mistake                      | Tip                                 |
| ---------------------------- | ----------------------------------- |
| Off-by-one errors            | Draw array indices on paper         |
| Not handling negatives       | Initialize with `Integer.MIN_VALUE` |
| Not updating window properly | Track `start` and `end` correctly   |
| Recomputing sums             | Use prefix sums                     |

***

### 🧩5. CURATED PROBLEM SET

#### ✅ Easy (10)

1. Two Sum (Leetcode 1) 🔗 Hash Map
2. Remove Duplicates (LC 26) 🔗 Two Pointers
3. Max Consecutive 1s 🔗 Sliding Window
4. Check if Array is Sorted
5. Find Missing Number 🔗 XOR
6. Reverse Array 🔗 Two Pointers
7. Prefix Sum Array Creation
8. Count Occurrences of Element
9. Subarray with Given Sum (GFG)
10. Check for Duplicates (LC 217) 🔗 Set

***

#### 🟡 Medium (10)

1. Maximum Subarray (LC 53) 🔗 Kadane’s
2. Longest Subarray with Sum K
3. Longest Substring without Repeat 🔗 Sliding Window
4. 3Sum (LC 15)
5. Minimum Size Subarray Sum (LC 209)
6. Merge Intervals 🔗 Sorting + Arrays
7. Sort Colors (LC 75) 🔗 Dutch National Flag
8. Next Permutation
9. Container With Most Water (LC 11)
10. Find Pivot Index (LC 724)

***

#### 🔴 Hard (10)

1. Median of Two Sorted Arrays (LC 4)
2. Maximum Product Subarray (LC 152)
3. Maximum Sum of Two Non-Overlapping Subarrays
4. Subarray Sum Equals K (LC 560)
5. Trapping Rain Water (LC 42)
6. Sliding Window Maximum (LC 239) 🔗 Deque
7. Count of Range Sum
8. Longest Subarray with Ones after K flips
9. Maximum Average Subarray II
10. Circular Subarray Max Sum

***

### ❓6. QUIZ – ARE YOU ARRAY-AWARE?

> Pick the right technique:

1. **"Find the longest subarray with sum ≤ K"**\
   a. Kadane’s\
   b. Sliding Window ✅\
   c. Binary Search
2. **"Find the kth smallest element"**\
   a. Min Heap ✅\
   b. Prefix Sum\
   c. DP
3. **"Reverse array in-place"**\
   a. Stack\
   b. Two Pointers ✅\
   c. Queue
4. **"Find subarray with exactly K distinct elements"**\
   a. Hashing\
   b. Sliding Window + Hash Map ✅\
   c. DFS

***

### 🧠7. FEYNMAN REFLECTION PROMPTS

* Explain Kadane’s Algorithm in your own words.
* What happens if the array has all negatives? How does Kadane handle it?
* When does a prefix sum fail to work?
