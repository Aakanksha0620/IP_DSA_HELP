# Sliding Window

## 🔶 Pattern #2: Sliding Window

### 🧠 Intuition

Sliding Window is used when you're asked to process **contiguous blocks** (subarrays or substrings) — especially when you care about the **maximum, minimum, or specific count** in a window of elements.

***

### 🚪 When to Use Sliding Window

Use it if:

* You’re working with **arrays or strings**
* You’re looking for:
  * Max/min subarray sum
  * Longest substring with conditions
  * Count of subarrays with some property

***

### 🧠 Pneumonic

> **“Window Slide to Optimize the Ride!”**\
> Instead of recalculating everything every time (like brute force), we **slide a fixed or dynamic window** over the array/string to reuse previous work.

***

## ✳️ Types of Sliding Window

| Type    | Window Size          | Example Problem                   |
| ------- | -------------------- | --------------------------------- |
| Fixed   | Constant window size | Max sum of K-sized subarray       |
| Dynamic | Size can grow/shrink | Longest substring without repeats |

***

### 🟢 Easy Example: Max Sum Subarray of Size K (Fixed Window)

**Problem:** Find the max sum of a subarray of size `k`

#### 🔍 Brute Force:

Time: O(n×k) – check all windows

#### ✅ Optimized (Sliding Window):

```java
javaCopyEditpublic int maxSum(int[] nums, int k) {
    int maxSum = 0, windowSum = 0;
    for (int i = 0; i < k; i++) windowSum += nums[i];
    maxSum = windowSum;
    
    for (int i = k; i < nums.length; i++) {
        windowSum += nums[i] - nums[i - k]; // slide window
        maxSum = Math.max(maxSum, windowSum);
    }
    return maxSum;
}
```

***

### 🟡 Medium Example: Longest Substring Without Repeating Characters (Dynamic Window)

**Problem:** Given a string, return the length of the longest substring with no repeating characters.

```java
javaCopyEditpublic int lengthOfLongestSubstring(String s) {
    Set<Character> set = new HashSet<>();
    int left = 0, maxLen = 0;

    for (int right = 0; right < s.length(); right++) {
        while (set.contains(s.charAt(right))) {
            set.remove(s.charAt(left++));
        }
        set.add(s.charAt(right));
        maxLen = Math.max(maxLen, right - left + 1);
    }
    return maxLen;
}
```

***

### 🔴 Hard Example: Minimum Window Substring

**Problem:** Find the smallest window in `s` that contains all characters of `t`

```java
javaCopyEditpublic String minWindow(String s, String t) {
    if (s.length() < t.length()) return "";

    Map<Character, Integer> map = new HashMap<>();
    for (char c : t.toCharArray()) map.put(c, map.getOrDefault(c, 0) + 1);

    int left = 0, matched = 0, minLen = Integer.MAX_VALUE, minStart = 0;
    Map<Character, Integer> window = new HashMap<>();

    for (int right = 0; right < s.length(); right++) {
        char c = s.charAt(right);
        window.put(c, window.getOrDefault(c, 0) + 1);

        if (map.containsKey(c) && window.get(c).intValue() == map.get(c).intValue()) {
            matched++;
        }

        while (matched == map.size()) {
            if (right - left + 1 < minLen) {
                minLen = right - left + 1;
                minStart = left;
            }

            char leftChar = s.charAt(left++);
            window.put(leftChar, window.get(leftChar) - 1);
            if (map.containsKey(leftChar) && window.get(leftChar) < map.get(leftChar)) {
                matched--;
            }
        }
    }

    return minLen == Integer.MAX_VALUE ? "" : s.substring(minStart, minStart + minLen);
}
```

***

## 🔁 Pattern Summary

| Feature           | Fixed Window               | Dynamic Window                           |
| ----------------- | -------------------------- | ---------------------------------------- |
| Constant `k` size | Max/Min sum, averages      | Sliding by fixed amount                  |
| Grows/Shrinks     | Conditions met or violated | Unique characters, target met, etc.      |
| Key Tools         | Sum, HashSet, HashMap      | Two pointers (left/right), window counts |

***

### 🧩 Practice Problems (30)

#### ✅ Easy (10)

1. Max Sum Subarray of Size K
2. Average of Subarray of Size K
3. Number of Subarrays of Size K with Average ≥ Threshold
4. Maximum Consecutive Ones
5. Count Good Substrings of Size 3
6. Longest Substring of All Vowels in Order
7. Binary Subarrays With Sum
8. Count Occurrences of Anagrams
9. Remove All Adjacent Duplicates in String
10. Check If Word Contains All Vowels

***

#### 🟡 Medium (10)

1. Longest Substring Without Repeating Characters
2. Fruits Into Baskets
3. Longest Repeating Character Replacement
4. Permutation in String
5. Longest Substring with At Most K Distinct Characters
6. Minimum Size Subarray Sum
7. Subarray Product Less Than K
8. Count Number of Nice Subarrays
9. Longest Substring with At Least K Repeating Characters
10. Find All Anagrams in a String

***

#### 🔴 Hard (10)

1. Minimum Window Substring
2. Sliding Window Maximum
3. Count Distinct Elements in Every Window
4. Smallest Range Covering Elements from K Lists
5. Maximum Number of Occurrences of Substring
6. Count Subarrays With Exactly K Different Integers
7. Max Number of Vowels in Substring of Given Length
8. Subarrays With K Different Integers
9. Longest Substring with Equal Letter Counts
10. Longest Subarray of 1's After Deleting One Element
