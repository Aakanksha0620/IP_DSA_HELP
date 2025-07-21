# Sliding Window & Two Pointers

## 📘 Module 14: Sliding Window & Two Pointers – “Narrow the Window, Expand the Solution”

***

### 📍1. DECISION DIAGRAM – When to Use

```
textCopyEdit                         ┌──────────────┐
                         │  Problem Qn? │
                         └─────┬────────┘
                               │
            ┌─────────────────┴─────────────────┐
            ▼                                   ▼
 Does it involve substrings, subarrays,       Are elements sorted?
  or a sequence of elements?                  Are two sums involved?
            │                                   │
 Sliding Window (Fixed/Variable)          Two Pointers (Sorted Arrays)
            │                                   │
 ┌──────────┴─────────┐             ┌───────────┴────────────┐
 ▼                    ▼             ▼                        ▼
 Fixed size          Variable size   Opposite direction       Same direction
 (e.g. max sum k)    (e.g. longest substr) (target sum)     (merge intervals)
```

***

### 🧠2. FLASHCARD – Key Use Cases

| Technique               | Common Problems                                 |
| ----------------------- | ----------------------------------------------- |
| 🔲 Fixed Sliding Window | Max sum of size k, avg, product                 |
| 🔳 Variable Window      | Longest substring with k distinct               |
| ⬅️➡️ Two Pointers       | Sorted array sum, reverse, dedup                |
| ↔️ Merge Pointers       | Merge intervals, linked list ops                |
| 🚪 Window Shrinking     | Min window size, smallest subarray with sum ≥ x |

> 🔖 Mnemonic: **"SWiFT"** – Sliding Window Fixed/Variable, Two-pointers

***

### 📚3. PATTERN TEMPLATES

#### ✳️ Fixed Sliding Window (size = k)

```java
javaCopyEditint maxSum(int[] nums, int k) {
    int sum = 0, max = 0;
    for (int i = 0; i < k; i++) sum += nums[i];
    max = sum;
    for (int i = k; i < nums.length; i++) {
        sum += nums[i] - nums[i - k];
        max = Math.max(max, sum);
    }
    return max;
}
```

***

#### ✳️ Variable Sliding Window

```java
javaCopyEditint lengthOfLongestSubstring(String s) {
    Set<Character> set = new HashSet<>();
    int left = 0, right = 0, max = 0;

    while (right < s.length()) {
        if (!set.contains(s.charAt(right))) {
            set.add(s.charAt(right++));
            max = Math.max(max, set.size());
        } else {
            set.remove(s.charAt(left++));
        }
    }
    return max;
}
```

***

#### ✳️ Two Pointers (Sorted Array)

```java
javaCopyEditboolean hasTargetSum(int[] nums, int target) {
    int left = 0, right = nums.length - 1;
    while (left < right) {
        int sum = nums[left] + nums[right];
        if (sum == target) return true;
        else if (sum < target) left++;
        else right--;
    }
    return false;
}
```

***

### 🔄4. MISTAKES TO AVOID

| Mistake                       | Tip                                                       |
| ----------------------------- | --------------------------------------------------------- |
| Misplacing left/right updates | Track window logic carefully                              |
| Not handling duplicates       | Use `Set` or conditional checks                           |
| Window size confusion         | Fixed → keep size constant; variable → adjust dynamically |
| Off-by-one in substrings      | Remember index inclusiveness/exclusiveness                |

***

### 🧩5. CURATED PROBLEM SET

#### ✅ Easy (10)

1. Maximum Sum Subarray of Size K (LC pattern)
2. Contains Duplicate II (LC 219)
3. Find All Anagrams in a String (LC 438)
4. Valid Palindrome II (LC 680)
5. Reverse String using Two Pointers (LC 344)
6. Move Zeroes (LC 283)
7. Merge Two Sorted Arrays (LC 88)
8. Remove Duplicates from Sorted Array (LC 26)
9. Two Sum II – Input Array is Sorted (LC 167)
10. Squares of Sorted Array (LC 977)

***

#### 🟡 Medium (10)

1. Longest Substring Without Repeating Characters (LC 3)
2. Minimum Size Subarray Sum (LC 209)
3. Longest Repeating Character Replacement (LC 424)
4. Fruits into Baskets (LC 904)
5. Longest Substring with At Most K Distinct Chars (LC 340)
6. Permutation in String (LC 567)
7. Minimum Window Substring (LC 76)
8. Sliding Window Maximum (LC 239)
9. Remove Duplicates from Sorted Array II (LC 80)
10. Subarrays with K Different Integers (LC 992)

***

#### 🔴 Hard (10)

1. Median of Two Sorted Arrays (LC 4)
2. Trapping Rain Water (LC 42) – two-pointer variation
3. Longest Substring with At Most 2 Distinct Chars
4. Shortest Subarray with Sum at Least K (LC 862)
5. Minimum Window Subsequence
6. Max Consecutive Ones III (LC 1004)
7. Longest Turbulent Subarray (LC 978)
8. Max Sum of Subarray of Size K with Condition
9. Smallest Range Covering Elements from K Lists (LC 632)
10. Longest Substring After Character Replacement

***

### ❓6. QUIZ – PATTERN SNAPSHOT

1. **"Max sum of k-size window?"**\
   ➤ Fixed Sliding Window ✅
2. **"Longest substring without repeats?"**\
   ➤ Variable Sliding Window ✅
3. **"Sorted array – find pair with target sum?"**\
   ➤ Two Pointers ✅
4. **"Smallest subarray ≥ target sum?"**\
   ➤ Variable Window Shrinking ✅

***

### 🧠7. FEYNMAN REFLECTION PROMPTS

* Why does sliding window give O(n) solutions?
* What’s the difference between fixed and variable windows?
* Why are two pointers only useful on sorted data?
* How can you use these patterns in linked lists?
