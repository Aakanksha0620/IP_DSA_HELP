# Cyclic Sort

## 🔷 Pattern #5: Cyclic Sort

### 🧠 Core Idea

If the array contains **n distinct numbers from 1 to n** (or from 0 to n−1), we can place each element at its **correct index**(i.e., `arr[i] = i+1` or `i`), **in-place**, with **O(n)** time and **O(1)** space.

***

### 📦 Use Cases

This pattern is perfect for:

* Finding missing numbers
* Finding duplicate numbers
* Sorting in-place with minimal space
* Detecting corrupt/misplaced values

***

### 🧠 Pneumonic

> **“Place every number at its home!”**

If number `x` belongs at index `x - 1`, and it's not already there — **swap** it.

***

## ✅ Classic Use Pattern

```java
javaCopyEditwhile (i < arr.length) {
    int correct = arr[i] - 1;
    if (arr[i] != arr[correct]) {
        swap(arr, i, correct);
    } else {
        i++;
    }
}
```

***

### 🟢 Easy Example: Sort an Array of 1 to n

```java
javaCopyEditpublic void cyclicSort(int[] arr) {
    int i = 0;
    while (i < arr.length) {
        int correctIndex = arr[i] - 1;
        if (arr[i] != arr[correctIndex]) {
            int temp = arr[i];
            arr[i] = arr[correctIndex];
            arr[correctIndex] = temp;
        } else {
            i++;
        }
    }
}
```

**Input:** `[3, 1, 5, 4, 2]`\
**Output:** `[1, 2, 3, 4, 5]`

***

### 🟡 Medium Example: Find the Missing Number (0 to n)

```java
javaCopyEditpublic int missingNumber(int[] nums) {
    int i = 0;
    while (i < nums.length) {
        int correct = nums[i];
        if (correct < nums.length && nums[i] != nums[correct]) {
            int temp = nums[i];
            nums[i] = nums[correct];
            nums[correct] = temp;
        } else {
            i++;
        }
    }

    for (i = 0; i < nums.length; i++) {
        if (nums[i] != i) return i;
    }
    return nums.length;
}
```

***

### 🔴 Hard Example: Find All Duplicate Numbers

```java
javaCopyEditpublic List<Integer> findDuplicates(int[] nums) {
    int i = 0;
    while (i < nums.length) {
        int correct = nums[i] - 1;
        if (nums[i] != nums[correct]) {
            int temp = nums[i];
            nums[i] = nums[correct];
            nums[correct] = temp;
        } else {
            i++;
        }
    }

    List<Integer> result = new ArrayList<>();
    for (i = 0; i < nums.length; i++) {
        if (nums[i] != i + 1) result.add(nums[i]);
    }
    return result;
}
```

***

### 🔁 Summary Table

| Scenario                               | Use Pattern If…                              |
| -------------------------------------- | -------------------------------------------- |
| Find missing/duplicate/corrupt numbers | Numbers are in range 1 to n or 0 to n        |
| Sort in-place in O(n)                  | Index and value have a mathematical relation |
| Avoid extra space                      | You are allowed to mutate the input          |

***

### 🧩 Practice Problems (30)

#### ✅ Easy (10)

1. Cyclic Sort (Basic)
2. Missing Number (0 to n)
3. Find the First Missing Positive
4. Sort 1 to n Without Extra Space
5. Swap Until Sorted
6. Find Index Mismatch
7. Smallest Missing Positive Number
8. Is Array Properly Positioned?
9. Restore Array to Original
10. Fill in Correct Index

***

#### 🟡 Medium (10)

1. Find All Duplicates in an Array
2. Find All Missing Numbers in an Array
3. Find Duplicate and Missing Number
4. Corrupt Pair (Duplicate + Missing)
5. Repeated and Missing Elements
6. Place Values in Correct Index
7. Detect All Corrupt Elements
8. Count Number of Swaps to Sort
9. Check if Can Be Sorted via Swaps
10. Restore a Permutation Array

***

#### 🔴 Hard (10)

1. First Missing Positive (Leetcode Hard)
2. Sort Array With One Swap
3. Rearrangement via Minimum Swaps
4. Minimum Swaps to Make Array Sorted
5. Detect Cycle in Number Position Mapping
6. Minimum Number of Moves to Equal Array
7. Find K-th Missing Positive Number
8. Find All Displaced Values
9. Sort Array with Cycles
10. Count All Cycles in Index Mapping

***

### 💬 Concept Wrap-Up

| Step        | What to Do                                  |
| ----------- | ------------------------------------------- |
| While i < n | Check if value belongs at current index     |
| If not      | Swap it with the correct index              |
| After sort  | Missing/extra elements will be out of place |
