# Tries

## 📘 Module 9: Tries – “The Autocomplete Brain of DSA”

***

### 📍1. DECISION DIAGRAM – When to Use Tries

```
textCopyEdit                    ┌──────────────┐
                    │  Problem Qn? │
                    └─────┬────────┘
                          │
      ┌───────────────────┴────────────────────┐
      ▼                                        ▼
  Is it about strings?                Is prefix/pattern matching needed?
     (word search, dictionary)           (autocomplete, startsWith)
      │                                        │
  Consider Trie                         Use Trie Search
      │                                        │
  ┌───┴───────────────┐             ┌──────────┴──────────────┐
  ▼                   ▼             ▼                         ▼
 Build Trie        Search Word   Prefix Check        Wildcard / Regex Search
```

> 🔍 Tip: Use **Trie** when prefix queries, word searches, or dictionary manipulations are needed in real time.

***

### 🧠2. FLASHCARD – Trie Essentials

| Concept            | Use Case                                              |
| ------------------ | ----------------------------------------------------- |
| 📚 TrieNode        | Stores character, links to children, end-of-word flag |
| 🔠 Insert          | Build dictionary                                      |
| 🔍 Search          | Check full word                                       |
| 🔎 startsWith      | Check prefix existence                                |
| 🧩 Word Dictionary | Wildcard (e.g. ‘.’) search                            |
| 🧠 Bit Trie        | Fast integer XOR and binary prefix problems           |

> 🔖 Mnemonic: **"ISSWBW"** – Insert, Search, StartsWith, Wildcard, Bitwise

***

### 📚3. TRIE OPERATIONS & TEMPLATES

#### ✳️ TrieNode Definition

```java
javaCopyEditclass TrieNode {
    TrieNode[] children = new TrieNode[26];
    boolean isEndOfWord = false;
}
```

***

#### ✳️ Insert a Word

```java
javaCopyEditvoid insert(String word) {
    TrieNode node = root;
    for (char ch : word.toCharArray()) {
        int i = ch - 'a';
        if (node.children[i] == null) node.children[i] = new TrieNode();
        node = node.children[i];
    }
    node.isEndOfWord = true;
}
```

***

#### ✳️ Search for a Word

```java
javaCopyEditboolean search(String word) {
    TrieNode node = root;
    for (char ch : word.toCharArray()) {
        int i = ch - 'a';
        if (node.children[i] == null) return false;
        node = node.children[i];
    }
    return node.isEndOfWord;
}
```

***

#### ✳️ startsWith (Prefix Check)

```java
javaCopyEditboolean startsWith(String prefix) {
    TrieNode node = root;
    for (char ch : prefix.toCharArray()) {
        int i = ch - 'a';
        if (node.children[i] == null) return false;
        node = node.children[i];
    }
    return true;
}
```

***

### 🔄4. MISTAKES TO AVOID

| Mistake                     | Tip                                                 |
| --------------------------- | --------------------------------------------------- |
| Not handling null children  | Always initialize child nodes properly              |
| Confusing word vs prefix    | Use `isEndOfWord` flag for full words only          |
| Using HashMap unnecessarily | Arrays (size 26) are faster if alphabet is fixed    |
| Bit Trie errors             | Binary strings require max 32 children for integers |

***

### 🧩5. CURATED PROBLEM SET

#### ✅ Easy (10)

1. Implement Trie (Prefix Tree) (LC 208)
2. Search Suggestions System (LC 1268)
3. Word Dictionary (LC 211)
4. Replace Words (LC 648)
5. Implement startsWith() in Trie
6. Prefix Count
7. Count Words Equal To/Starting With
8. Longest Word with All Prefixes (GFG)
9. Autocomplete System (LC 642 - base problem)
10. Shortest Unique Prefix

***

#### 🟡 Medium (10)

1. Word Search II (LC 212)
2. Palindrome Pairs (LC 336)
3. Maximum XOR of Two Numbers (LC 421)
4. Stream of Characters (LC 1032)
5. Prefix and Suffix Search (LC 745)
6. Phone Directory (GFG)
7. Word Squares (LC 425)
8. Distinct Substrings in a String
9. Longest Common Prefix using Trie
10. Delete Words with Given Prefix

***

#### 🔴 Hard (10)

1. XOR Queries in Trie
2. Count Pairs with XOR in Range
3. Longest XOR Path in a Tree (Trie + DFS)
4. Maximum XOR with Element in Array
5. Count Distinct Substrings using Trie
6. Minimum XOR Sum of Two Arrays
7. Search Word in Grid using Trie
8. Multi-pattern Matching
9. Suffix Trie for Pattern Matching
10. Bitwise Trie – Find AND/OR/XOR in Range

***

### ❓6. QUIZ – TRIE TACTICS

1. **"Best structure for autocomplete?"**\
   a. HashSet\
   b. Trie ✅\
   c. Heap
2. **"How to find all words with prefix 'app'?"**\
   a. DFS from prefix node ✅\
   b. Search whole list\
   c. Binary search
3. **"Check if input string matches pattern with '.' wildcard"**\
   a. Stack\
   b. Regex\
   c. Trie + Backtracking ✅
4. **"Find max XOR pair in array"**\
   a. Sort + compare\
   b. Bit Trie ✅\
   c. BST

***

### 🧠7. FEYNMAN REFLECTION PROMPTS

* Why is a Trie better than HashMap for prefix queries?
* How does backtracking work with Trie during DFS?
* Can Tries be used for numbers instead of characters?
* What is the tradeoff between Trie and Ternary Search Tree?
