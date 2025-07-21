# Bit Manipulation

## 📘 Module 12: Bit Manipulation – “Think in Binary. Solve in Constant Time.”

***

### 📍1. DECISION DIAGRAM – When to Use Bit Manipulation

```
textCopyEdit                        ┌──────────────┐
                        │  Problem Qn? │
                        └─────┬────────┘
                              │
      ┌──────────────────────┴──────────────────────┐
      ▼                                              ▼
  Does it involve numbers?               Does it involve sets or toggling?
 (Power of 2, odd/even, XOR, etc.)         (Subset, inclusion, bit masks)
      │                                              │
 Use AND/OR/XOR/SHIFT                         Use bitmasks and operations
      │                                              │
  ┌───┴────┐                                  ┌───────┴────────┐
  ▼        ▼                                  ▼                ▼
Count bits,        Power of 2?      Subsets/DP           XOR Tricks
toggle i-th bit     Use (n & n-1)   (e.g. TSP, Key Lock)  (Missing numbers)
```

***

### 🧠2. FLASHCARD – Core Bit Operators

| Operator | Symbol | Meaning                 |
| -------- | ------ | ----------------------- |
| AND      | `&`    | 1 if both bits are 1    |
| OR       | \`     | \`                      |
| XOR      | `^`    | 1 if bits are different |
| NOT      | `~`    | Flip bits               |
| SHIFT L  | `<<`   | Multiply by 2ⁿ          |
| SHIFT R  | `>>`   | Divide by 2ⁿ            |

> 🔖 Mnemonic: **"AXON"** – AND, XOR, OR, NOT (easy to remember using neurons)

***

### 📚3. COMMON TRICKS & TEMPLATES

#### ✳️ Check if Number is Power of 2

```java
javaCopyEditboolean isPowerOfTwo(int n) {
    return n > 0 && (n & (n - 1)) == 0;
}
```

***

#### ✳️ Count Set Bits (Brian Kernighan's Algo)

```java
javaCopyEditint countBits(int n) {
    int count = 0;
    while (n > 0) {
        n &= (n - 1);
        count++;
    }
    return count;
}
```

***

#### ✳️ Get i-th Bit

```java
javaCopyEditint getBit(int n, int i) {
    return (n >> i) & 1;
}
```

***

#### ✳️ Set i-th Bit

```java
javaCopyEditint setBit(int n, int i) {
    return n | (1 << i);
}
```

***

#### ✳️ Unset (Clear) i-th Bit

```java
javaCopyEditint clearBit(int n, int i) {
    return n & ~(1 << i);
}
```

***

#### ✳️ XOR Trick – Find Single Element

```java
javaCopyEditint findSingle(int[] nums) {
    int xor = 0;
    for (int num : nums) xor ^= num;
    return xor;
}
```

***

### 🔄4. MISTAKES TO AVOID

| Mistake                     | Tip                                                      |
| --------------------------- | -------------------------------------------------------- |
| Forgetting 0-based indexing | Bits are from 0 to 31                                    |
| Using signed right shift    | Use `>>>` in Java for unsigned shift                     |
| Overflow in shifts          | Shifting too far gives 0                                 |
| Using XOR like AND          | XOR works for _canceling duplicates_, not filtering ones |

***

### 🧩5. CURATED PROBLEM SET

#### ✅ Easy (10)

1. Count 1 Bits (LC 191)
2. Power of Two (LC 231)
3. Single Number (LC 136)
4. Determine if Bit is Set
5. XOR from 1 to N
6. Count number of bits to flip to convert A to B
7. Parity of Integer (Odd/Even using LSB)
8. Reverse Bits (LC 190)
9. Find ith Bit Set
10. Toggle ith Bit

***

#### 🟡 Medium (10)

1. Subsets using Bitmask (LC 78)
2. Maximum XOR of Two Numbers (LC 421)
3. Subset Sum with Bitmasking
4. Count Bits for Numbers 0 to n (LC 338)
5. Hamming Distance (LC 461)
6. Bitwise AND of Numbers Range (LC 201)
7. Total Hamming Distance (LC 477)
8. Longest Nice Subarray (LC 2401)
9. Minimum XOR Value Pairs
10. Number of Steps to Reduce Binary to Zero (LC 1404)

***

#### 🔴 Hard (10)

1. XOR of all subarrays
2. XOR Triplets (LC 1442)
3. Maximum XOR with Element in Array (LC 1707)
4. XOR of Subarrays in a Range
5. TSP with Bitmask DP
6. XOR DP on Trees
7. Count Set Bits in Range 1 to N
8. Shortest Path with Alternating Colors (LC 1129)
9. Find XOR of Sum of All Pairs
10. XOR Matrix Construction

***

### ❓6. QUIZ – BITS OF WISDOM

1. **"Check if n is power of 2"**\
   a. `(n % 2 == 0)`\
   b. `(n & (n - 1)) == 0 ✅`\
   c. `(n >> 1) == 1`
2. **"Find number with single occurrence"**\
   a. AND\
   b. OR\
   c. XOR ✅
3. **"Number of set bits in 1001"**\
   a. 1\
   b. 2 ✅\
   c. 3
4. **"Unset 3rd bit from right in number n"**\
   a. `n & ~(1 << 2) ✅`\
   b. `n | ~(1 << 2)`\
   c. `n ^ ~(1 << 2)`

***

### 🧠7. FEYNMAN REFLECTION PROMPTS

* What does `(n & (n-1))` really do?
* Why does XOR help find unique elements?
* How does bitmasking help generate all subsets?
* How is Bit Manipulation different from Arithmetic Optimization?

<figure><img src=".gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>
