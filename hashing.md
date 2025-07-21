# Hashing

## 📘 Module 3: Hashing – “The Swiss Army Knife of DSA”

***

### 📍1. DECISION DIAGRAM – How to Approach Hashing Problems

```
textCopyEdit                   ┌──────────────┐
                   │  Hash Qn?   │
                   └─────┬────────┘
                         │
          ┌──────────────┴───────────────┐
          ▼                              ▼
   Is it about Frequency / Count?   Is Lookup/Existence needed?
          │                              │
  Use HashMap / HashSet          Use Set or Map for quick access
          │                              │
  ┌───────┴────────────┐        ┌────────┴─────────┐
  ▼                    ▼        ▼                  ▼
Find duplicates     Majority   Subarray with sum   Custom Key Hashing
                    elements     / Anagram check   (e.g., freq string)
```

> 🔍 **Tip**: Hashing helps solve many problems in **O(1)** average time.

***

### 🧠2. FLASHCARD – Mastering Hashing

| Concept                 | Use Case                                        |
| ----------------------- | ----------------------------------------------- |
| 🧮 HashMap              | Frequency counting, mapping indices or elements |
| 🔁 HashSet              | Uniqueness, duplicates, visited tracking        |
| 🔑 Custom Hash Key      | Anagram detection, pattern grouping             |
| 🧩 Composite Keys       | 2D prefix sums, grid-based problems             |
| 📦 Bucket Hashing       | Count sort, frequency bucket                    |
| 🧠 Hashing + Prefix Sum | Subarray with sum K                             |

> 🔖 Mnemonic: **"MAPSK"** – Map, Anagram, Prefix, Set, Keying

***

### 📚3. PROBLEM-SOLVING HEURISTICS

#### ✳️ Pattern 1: Frequency Hashing

**Trigger**: Count occurrences, check majority, detect extra element

```java
javaCopyEditMap<Integer, Integer> freq = new HashMap<>();
for (int n : nums)
    freq.put(n, freq.getOrDefault(n, 0) + 1);
```

***

#### ✳️ Pattern 2: HashSet for Lookup

**Trigger**: Is there a duplicate? Can element `x` be found in previous entries?

```java
javaCopyEditSet<Integer> seen = new HashSet<>();
for (int n : nums) {
    if (seen.contains(n)) return true;
    seen.add(n);
}
```

***

#### ✳️ Pattern 3: Subarray Sum = K (Prefix + Hash)

**Trigger**: Sum of subarrays equals target

```java
javaCopyEditMap<Integer, Integer> prefixSumFreq = new HashMap<>();
prefixSumFreq.put(0, 1);
int sum = 0, count = 0;

for (int n : nums) {
    sum += n;
    count += prefixSumFreq.getOrDefault(sum - k, 0);
    prefixSumFreq.put(sum, prefixSumFreq.getOrDefault(sum, 0) + 1);
}
```

***

#### ✳️ Pattern 4: Grouping Anagrams (Custom Hash Key)

**Trigger**: Grouping strings based on character set

```java
javaCopyEditMap<String, List<String>> map = new HashMap<>();
for (String word : words) {
    char[] chars = word.toCharArray();
    Arrays.sort(chars);  // key = sorted word
    String key = new String(chars);
    map.computeIfAbsent(key, x -> new ArrayList<>()).add(word);
}
```

***

### 🔄4. MISTAKES TO AVOID

| Mistake                                          | Tip                                          |
| ------------------------------------------------ | -------------------------------------------- |
| Using wrong key (e.g., object instead of string) | Define proper hash keys                      |
| Missing initialization                           | Always `map.put(0,1)` in prefix sum problems |
| Modifying map while iterating                    | Use iterator or extra storage                |
| Using HashMap when order matters                 | Use `LinkedHashMap` or `TreeMap`             |

***

### 🧩5. CURATED PROBLEM SET

#### ✅ Easy (10)

1. Two Sum (LC 1) 🔗 HashMap
2. Check for Duplicates (LC 217)
3. Isomorphic Strings (LC 205)
4. Intersection of Two Arrays (LC 349)
5. First Unique Character (LC 387)
6. Ransom Note (LC 383)
7. Happy Number (LC 202)
8. Valid Anagram (LC 242)
9. Number of Good Pairs
10. Count Frequencies of All Elements

***

#### 🟡 Medium (10)

1. Subarray Sum Equals K (LC 560)
2. Group Anagrams (LC 49)
3. Longest Substring with K Distinct Characters
4. Continuous Subarray Sum (LC 523)
5. Longest Consecutive Sequence (LC 128)
6. Equal Row and Column Pairs
7. Count Subarrays with Equal 0s and 1s
8. Word Pattern (LC 290)
9. Find All Anagrams in a String (LC 438)
10. Longest Harmonious Subsequence (LC 594)

***

#### 🔴 Hard (10)

1. Count Distinct Elements in Every Window
2. Longest Subarray with Equal Number of 0s and 1s
3. Maximum Size Subarray Sum Equals K
4. Sum of Distances in Tree (LC 834)
5. Maximum XOR of Two Numbers (LC 421)
6. Subarrays with K Different Integers
7. Distinct Characters in All Substrings
8. Minimum Window Subsequence
9. Longest Palindrome by Rearranging
10. Minimum Operations to Make Array Beautiful

***

### ❓6. QUIZ – HASH IT OUT

> Pick the best tool:

1. **"Check if any duplicates exist"**\
   a. HashSet ✅\
   b. Stack\
   c. Queue
2. **"Group words that are anagrams"**\
   a. HashMap with Sorted Key ✅\
   b. Stack\
   c. Recursion
3. **"Find number of subarrays summing to K"**\
   a. Prefix Sum + HashMap ✅\
   b. DP\
   c. Two Pointers
4. **"Find longest consecutive sequence"**\
   a. Sort + Scan\
   b. HashSet + Smart Traversal ✅\
   c. BFS

***

### 🧠7. FEYNMAN REFLECTION PROMPTS

* How can a HashMap help in subarray sum problems?
* Why use a sorted string as a key in anagram grouping?
* Can we replace HashMap with Trie in grouping tasks?
* How to handle collisions in custom hash keys?
