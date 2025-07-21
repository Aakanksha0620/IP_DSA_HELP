# String

## 📘 Module 2: Strings – “From Characters to Champions”

***

### 📍1. DECISION DIAGRAM – How to Approach String Problems

```
textCopyEdit                  ┌────────────┐
                  │ String Qn? │
                  └─────┬──────┘
                        │
         ┌──────────────┴──────────────┐
         ▼                             ▼
     Is order important?        Need to modify/validate?
         │                             │
     Substring/Pattern?         Palindrome/Anagram/Valid?
         │                             │
 ┌───────┴───────┐            ┌────────┴─────────┐
 ▼               ▼            ▼                  ▼
Sliding Window  Hash Map   Two Pointers      Stack
                              (reverse)     (balance check)
```

> 🔍 **Tip**: Use character counts = Hash Map, Pattern Matching = Sliding Window / KMP

***

### 🧠2. FLASHCARD – Mastering Strings

| Concept              | Use Case                                             |
| -------------------- | ---------------------------------------------------- |
| 🪟 Sliding Window    | Substrings with constraints (length, chars, repeats) |
| 🔢 Hash Map / Set    | Frequency, uniqueness, anagrams                      |
| 🔁 Two Pointers      | Palindrome check, reverse in-place                   |
| 📚 Stack             | Balanced parentheses, decoding, string builders      |
| 🔤 Trie              | Word search, autocomplete                            |
| 💥 KMP / Z-Algorithm | Pattern Matching                                     |

> 🔖 Mnemonic: "**SHAKTiS**" – Sliding, Hash, Anagram, KMP, Trie, Stack

***

### 📚3. PROBLEM-SOLVING HEURISTICS

#### ✳️ Pattern 1: Sliding Window

**Trigger**: "longest/shortest substring", "no repeating characters", "at most/at least K distinct"

```java
javaCopyEditint left = 0;
Map<Character, Integer> map = new HashMap<>();
for (int right = 0; right < s.length(); right++) {
    map.put(...); // Expand window
    while (invalidCondition) {
        map.remove(...); // Shrink window
        left++;
    }
    // Update result
}
```

***

#### ✳️ Pattern 2: Two Pointers

**Trigger**: Palindrome, reverse string, comparison between ends

```java
javaCopyEditint l = 0, r = s.length() - 1;
while (l < r) {
    if (s.charAt(l) != s.charAt(r)) return false;
    l++; r--;
}
return true;
```

***

#### ✳️ Pattern 3: Hash Map / Set

**Trigger**: Anagrams, repeated characters, character count

```java
javaCopyEditint[] freq = new int[26]; // or Map<Character, Integer>
for (char c : s.toCharArray()) freq[c - 'a']++;
```

***

#### ✳️ Pattern 4: Stack

**Trigger**: Valid parentheses, decode string, remove adjacent duplicates

```java
javaCopyEditStack<Character> stack = new Stack<>();
for (char c : s.toCharArray()) {
    if (condition) stack.push(c);
    else stack.pop();
}
```

***

#### ✳️ Pattern 5: Trie

**Trigger**: Prefix-based search, dictionary problems

```java
javaCopyEditclass TrieNode {
    TrieNode[] children = new TrieNode[26];
    boolean isEnd = false;
}
```

***

### 🔄4. MISTAKES TO AVOID

| Mistake                                | Tip                                   |
| -------------------------------------- | ------------------------------------- |
| Using `==` for strings                 | Use `.equals()` in Java               |
| Index out of bounds                    | Always check substring limits         |
| Not resetting counts in sliding window | Clear map when shrinking              |
| Incorrect character encoding           | Use `char - 'a'` safely for lowercase |

***

### 🧩5. CURATED PROBLEM SET

#### ✅ Easy (10)

1. Reverse a String (LC 344)
2. Valid Palindrome (LC 125)
3. Implement strStr() (LC 28)
4. Valid Anagram (LC 242)
5. First Unique Character (LC 387)
6. Detect Capital (LC 520)
7. Count Vowels in Substring
8. Remove Duplicates
9. Excel Sheet Column Number (LC 171)
10. Longest Common Prefix (LC 14)

***

#### 🟡 Medium (10)

1. Longest Substring Without Repeating Characters (LC 3) 🔗 Sliding Window
2. Group Anagrams (LC 49) 🔗 HashMap
3. Longest Palindromic Substring (LC 5)
4. Permutation in String (LC 567)
5. Minimum Window Substring (LC 76)
6. Decode String (LC 394)
7. String Compression (LC 443)
8. Palindromic Substrings (LC 647)
9. Word Break (LC 139)
10. Multiply Strings (LC 43)

***

#### 🔴 Hard (10)

1. Longest Duplicate Substring
2. Edit Distance (LC 72)
3. Regular Expression Matching (LC 10)
4. Wildcard Matching (LC 44)
5. Minimum Number of Operations to Convert String A to B
6. Count Different Palindromic Subsequences
7. Minimum Insertions to Make Palindrome
8. Serialize and Deserialize String
9. Build a Trie and Search Engine
10. Word Ladder II (LC 126)

***

### ❓6. QUIZ – STRING SENSE

> Choose the best approach:

1. **"Find longest substring with no repeating characters"**\
   a. Hash Map\
   b. Sliding Window ✅\
   c. Recursion
2. **"Are two strings anagrams?"**\
   a. Hash Map ✅\
   b. Trie\
   c. DP
3. **"Decode ‘3\[a]2\[bc]’ into ‘aaabcbc’"**\
   a. Two Pointers\
   b. Stack ✅\
   c. Recursion
4. **"Find longest palindrome in string"**\
   a. Sliding Window\
   b. DP ✅\
   c. Stack

***

### 🧠7. FEYNMAN REFLECTION PROMPTS

* Why does a HashMap help in sliding window problems?
* How do you track character count efficiently?
* What’s the difference between a Trie and a HashMap?
* How can you check for a palindrome in O(1) space?
