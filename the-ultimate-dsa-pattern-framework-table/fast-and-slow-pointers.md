# Fast & Slow Pointers

## 🔷 Pattern #3: Fast & Slow Pointers (also called Floyd’s Tortoise & Hare)

### 💡 Core Idea

Use **two pointers moving at different speeds** (typically one moves 2 steps, the other 1 step). If there's a cycle, they’ll **eventually meet** inside it.

***

### 🧠 When to Use This Pattern?

Use Fast & Slow Pointers when:

* You need to **detect cycles** (in arrays, linked lists, graphs)
* You want to **find the middle** of a linked list
* You're asked to **remove a cycle** or find its **starting point**

***

### 🧠 Pneumonic

> **"Fast chases slow; if there's a loop, they’ll meet and show!"**

***

## ✅ Classic Questions

#### Use Cases:

| Problem Type                      | Pattern Application                            |
| --------------------------------- | ---------------------------------------------- |
| Detect cycle in a linked list     | Use slow & fast pointers, detect meeting point |
| Find middle of linked list        | Fast moves 2x, slow ends up at the middle      |
| Linked list cycle length or start | Once they meet, calculate steps or rewind      |
| Find happy number                 | Use value -> sum of squares chain as path      |
| Detect cycle in array             | Fast & slow index simulation                   |

***

### 🟢 Easy Example: Find Middle of Linked List

```java
javaCopyEditpublic ListNode findMiddle(ListNode head) {
    ListNode slow = head, fast = head;
    while (fast != null && fast.next != null) {
        slow = slow.next;
        fast = fast.next.next;
    }
    return slow; // slow is now at the middle
}
```

***

### 🟡 Medium Example: Detect Cycle in a Linked List

```java
javaCopyEditpublic boolean hasCycle(ListNode head) {
    ListNode slow = head, fast = head;
    while (fast != null && fast.next != null) {
        slow = slow.next;
        fast = fast.next.next;
        if (slow == fast) return true;
    }
    return false;
}
```

***

### 🔴 Hard Example: Start of the Cycle in Linked List

**Step-by-step:**

1. Detect if there's a cycle using fast/slow.
2. Once they meet, put one pointer at head and move both 1 step at a time.
3. Where they meet again is the start of the cycle.

```java
javaCopyEditpublic ListNode detectCycle(ListNode head) {
    ListNode slow = head, fast = head;

    while (fast != null && fast.next != null) {
        slow = slow.next;
        fast = fast.next.next;
        if (slow == fast) {
            ListNode entry = head;
            while (entry != slow) {
                entry = entry.next;
                slow = slow.next;
            }
            return entry;
        }
    }
    return null;
}
```

***

## 📘 Tips

| Use It When…                      | Don't Use When…                         |
| --------------------------------- | --------------------------------------- |
| There’s movement in a path        | You need prefix/suffix handling         |
| You want cycle/midpoint detection | You’re working with unordered sets/maps |

***

### 🧩 Practice Problems (30)

#### ✅ Easy (10)

1. Find Middle of Linked List
2. Happy Number
3. Linked List Cycle
4. Palindrome Linked List
5. Move Zeroes (variation)
6. Intersection of Two Linked Lists
7. Reverse Linked List
8. Remove Duplicates from Sorted List
9. Remove Linked List Elements
10. Delete Node in a Linked List

***

#### 🟡 Medium (10)

1. Linked List Cycle II (start of cycle)
2. Find the Duplicate Number (cycle in array)
3. Remove N-th Node From End
4. Reorder List
5. Odd Even Linked List
6. Middle of the Linked List (again!)
7. Add Two Numbers (Linked Lists)
8. Split Linked List in Parts
9. Swap Nodes in Pairs
10. Detect Loop in Circular Array

***

#### 🔴 Hard (10)

1. Circular Array Loop
2. Merge K Sorted Lists (Fast pointer for merging logic)
3. Copy List with Random Pointer
4. Reverse Nodes in K-Group
5. Linked List in Binary Tree
6. Maximum Twin Sum of a Linked List
7. Minimum Number of Operations to Make Array Complementary
8. Longest Cycle in a Graph
9. Longest Palindromic Sublist in Linked List
10. Find Length of Cycle in Linked List

***

### 🔁 Summary Table

| Use Fast & Slow When...               | Result                       |
| ------------------------------------- | ---------------------------- |
| Detecting cycles in linked list/array | O(n) with no extra space     |
| Finding midpoint                      | One pass, no counting        |
| Finding loop entry                    | Meet point + reset 1 pointer |
