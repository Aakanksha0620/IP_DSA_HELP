# Binary Search

## 📘 Module 13: Binary Search – “Divide the Search Space to Conquer the Solution”

***

### 📍1. DECISION DIAGRAM – When to Use Binary Search

```
textCopyEdit                        ┌──────────────┐
                        │  Problem Qn? │
                        └─────┬────────┘
                              │
        ┌────────────────────┴──────────────────────┐
        ▼                                            ▼
    Is the input sorted?                   Can we search over a range/answer?
        │                                            │
  Use Standard Binary Search              Use Binary Search on Answer
        │                                            │
  ┌─────┴────────────┐                   ┌───────────┴─────────────┐
  ▼                  ▼                   ▼                         ▼
 Search for element   Lower/Upper Bound   Min/max satisfying condition
    (Classic)             (Boundaries)    (Min days, max size, etc.)
```

***

### 🧠2. FLASHCARD – Binary Search Core Types

| Type                     | Usage                                  |
| ------------------------ | -------------------------------------- |
| 🔍 Classic Binary Search | Find exact match                       |
| ⬆️ Lower Bound (First ≥) | Smallest index where condition holds   |
| ⬇️ Upper Bound (Last ≤)  | Largest index where condition holds    |
| 🎯 Search on Answer      | Find optimal min/max using BS          |
| 🔁 Infinite BS           | Use `start < end` or `start + 1 < end` |
| 📦 Sorted/Rotated Array  | Modified binary search logic           |

> 🔖 Mnemonic: **"CLUES"** – Classic, Lower Bound, Upper Bound, Edge, Search Space

***

### 📚3. TEMPLATE – Classic Binary Search

#### ✳️ Iterative Template

```java
javaCopyEditint binarySearch(int[] arr, int target) {
    int low = 0, high = arr.length - 1;
    while (low <= high) {
        int mid = low + (high - low) / 2;
        if (arr[mid] == target) return mid;
        else if (arr[mid] < target) low = mid + 1;
        else high = mid - 1;
    }
    return -1;
}
```

***

#### ✳️ Lower Bound (First ≥ target)

```java
javaCopyEditint lowerBound(int[] arr, int target) {
    int low = 0, high = arr.length;
    while (low < high) {
        int mid = low + (high - low) / 2;
        if (arr[mid] < target) low = mid + 1;
        else high = mid;
    }
    return low;
}
```

***

#### ✳️ Binary Search on Answer (Monotonic Predicate)

```java
javaCopyEditint binarySearchAnswer(int low, int high) {
    while (low < high) {
        int mid = low + (high - low) / 2;
        if (condition(mid)) high = mid;
        else low = mid + 1;
    }
    return low;
}
```

***

### 🔄4. MISTAKES TO AVOID

| Mistake                                | Fix                                                |
| -------------------------------------- | -------------------------------------------------- |
| `mid = (low + high)/2` causes overflow | Use `mid = low + (high - low)/2`                   |
| Infinite loop                          | Use correct `<=`, `<`, update `low/high` correctly |
| Confusing lower vs upper bound         | Lower → `high = mid`, Upper → `low = mid + 1`      |
| Off-by-one errors                      | Practice writing edge conditions carefully         |

***

### 🧩5. CURATED PROBLEM SET

#### ✅ Easy (10)

1. Binary Search (LC 704)
2. Guess Number Higher or Lower (LC 374)
3. Square Root (LC 69)
4. First Bad Version (LC 278)
5. Search Insert Position (LC 35)
6. Is Perfect Square (LC 367)
7. Find Smallest Letter Greater Than Target (LC 744)
8. Find Peak Element (LC 162)
9. Search in Sorted Array
10. Kth Missing Positive Number (LC 1539)

***

#### 🟡 Medium (10)

1. Find Minimum in Rotated Sorted Array (LC 153)
2. Search in Rotated Sorted Array (LC 33)
3. Find First and Last Position of Element (LC 34)
4. Capacity to Ship Packages Within D Days (LC 1011)
5. Koko Eating Bananas (LC 875)
6. Median of Two Sorted Arrays (LC 4)
7. Find K Closest Elements (LC 658)
8. Minimum Days to Make Bouquets (LC 1482)
9. Search a 2D Matrix (LC 74)
10. Successful Pairs of Spells and Potions (LC 2300)

***

#### 🔴 Hard (10)

1. Aggressive Cows (GFG)
2. Allocate Minimum Number of Pages
3. Split Array Largest Sum (LC 410)
4. Minimize Max Distance to Gas Station (LC 774)
5. Minimum Number of Days to Make m Bouquets
6. Find in Mountain Array (LC 1095)
7. Maximum Value at a Given Index in Bounded Array (LC 1802)
8. K-th Smallest Pair Distance (LC 719)
9. Capacity To Ship Packages With Constraints
10. Distance Value Between Two Arrays

***

### ❓6. QUIZ – BINARY CHECK

1. **"Which condition ensures loop stops?"**\
   a. `low <= high`\
   b. `low < high ✅`\
   c. `low == high`
2. **"What’s the safest mid formula?"**\
   a. `(low + high)/2`\
   b. `low + (high - low)/2 ✅`\
   c. `low >> 1`
3. **"Find min time to finish task" → Use?**\
   a. Greedy\
   b. DP\
   c. Binary Search on Answer ✅
4. **"What happens if you don’t update low/high?"**\
   a. Nothing\
   b. Stack Overflow\
   c. Infinite Loop ✅

***

### 🧠7. FEYNMAN REFLECTION PROMPTS

* Why does binary search run in O(log n)?
* When does binary search fail?
* Can binary search be applied to unsorted input?
* Why is binary search useful even in **non-array** problems?
