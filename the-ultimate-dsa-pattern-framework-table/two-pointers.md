# Two Pointers

#### 🔹 Pattern 1: Two Pointers

**Used when:** You deal with sorted arrays, linked lists, or problems where you compare elements from two ends or adjacent elements.

**Core idea:** Have two pointers moving toward each other (or one chasing another) to reduce time complexity from O(n²) → O(n)

**🧠 Pneumonic to Remember:**

> **"Two fingers walk faster"** – instead of nested loops, use two walkers moving smartly.

***

**🟢 Easy Example: Check if a pair exists in sorted array**

**Problem:** Given sorted array, find if a pair exists that sums to a target.

```java
public boolean hasPair(int[] nums, int target) {
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

**🟡 Medium Example: Container With Most Water**

**Problem:** Maximize area between two heights.

```java
public int maxArea(int[] height) {
    int max = 0, left = 0, right = height.length - 1;
    while (left < right) {
        int h = Math.min(height[left], height[right]);
        max = Math.max(max, h * (right - left));
        if (height[left] < height[right]) left++;
        else right--;
    }
    return max;
}
```

***

**🔴 Hard Example: Trapping Rain Water**

```java
public int trap(int[] height) {
    int left = 0, right = height.length - 1;
    int leftMax = 0, rightMax = 0, result = 0;
    
    while (left < right) {
        if (height[left] < height[right]) {
            leftMax = Math.max(leftMax, height[left]);
            result += leftMax - height[left];
            left++;
        } else {
            rightMax = Math.max(rightMax, height[right]);
            result += rightMax - height[right];
            right--;
        }
    }
    return result;
}
```

***

### 🧩 30 Practice Problems for Two Pointers

#### ✅ Easy (10):

1. Remove Duplicates from Sorted Array
2. Reverse a String
3. Palindrome String
4. Square of Sorted Array
5. Merge Two Sorted Arrays
6. Move Zeros to End
7. Intersection of Two Arrays II
8. Find the Difference of Two Strings
9. Rotate Array (2 pointers + reverse trick)
10. Is Subsequence?

#### 🟡 Medium (10):

1. Container With Most Water
2. 3Sum
3. Sort Colors (Dutch National Flag)
4. Partition Labels
5. Backspace String Compare
6. Shortest Unsorted Subarray
7. Remove N-th Node From End
8. Longest Substring Without Repeating Characters (2 pointers variation)
9. Minimum Window Substring (with sliding window)
10. Two Sum II - Input Sorted

#### 🔴 Hard (10):

1. Trapping Rain Water
2. 4Sum
3. Minimum Operations to Reduce X to Zero
4. Maximize Distance to Closest Person
5. Longest Mountain in Array
6. Sliding Window Maximum (Deque + 2P)
7. Find the Longest Palindromic Substring
8. Median of Two Sorted Arrays
9. Longest Subarray with Sum K
10. Subarrays with Product Less than K
