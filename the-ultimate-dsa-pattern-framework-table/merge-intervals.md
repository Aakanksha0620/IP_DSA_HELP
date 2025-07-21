# Merge Intervals

## 🔷 Pattern #4: Merge Intervals

### 🧠 Core Idea

When dealing with **time intervals, ranges, or bookings**, you often need to **sort by start time** and then **merge overlapping intervals**.

This pattern is used in:

* Scheduling
* Calendar problems
* Collision detection
* Video streaming, etc.

***

### 💡 When to Use Merge Intervals

Use it if:

* You are given **intervals (start, end)** and asked to:
  * Merge overlaps
  * Insert/fit a new interval
  * Find gaps or free time
  * Remove overlaps
  * Count meeting rooms needed

***

### 🧠 Pneumonic

> **“Sort + Compare = Merge Prepare”**

1. **Sort** all intervals by start time
2. **Compare** current with previous and decide:
   * **Overlap? → Merge**
   * **No Overlap? → Add as-is**

***

### 🟢 Easy Example: Merge Intervals

#### Problem:

Given a list of intervals, merge overlapping ones.

#### Step-by-Step Java Code:

```java
javaCopyEditpublic int[][] merge(int[][] intervals) {
    Arrays.sort(intervals, (a, b) -> a[0] - b[0]); // 1. Sort by start
    List<int[]> result = new ArrayList<>();

    int[] current = intervals[0];
    for (int i = 1; i < intervals.length; i++) {
        int[] next = intervals[i];
        if (current[1] >= next[0]) { // 2. Overlap → merge
            current[1] = Math.max(current[1], next[1]);
        } else {
            result.add(current);     // No overlap → add & move
            current = next;
        }
    }
    result.add(current); // Add the last interval
    return result.toArray(new int[result.size()][]);
}
```

***

### 🟡 Medium Example: Insert Interval

**Problem:** Insert a new interval and merge it into correct place.

#### Java Code:

```java
javaCopyEditpublic int[][] insert(int[][] intervals, int[] newInterval) {
    List<int[]> result = new ArrayList<>();
    int i = 0;

    // Step 1: Add all intervals ending before newInterval starts
    while (i < intervals.length && intervals[i][1] < newInterval[0]) {
        result.add(intervals[i++]);
    }

    // Step 2: Merge all overlapping intervals
    while (i < intervals.length && intervals[i][0] <= newInterval[1]) {
        newInterval[0] = Math.min(newInterval[0], intervals[i][0]);
        newInterval[1] = Math.max(newInterval[1], intervals[i][1]);
        i++;
    }
    result.add(newInterval);

    // Step 3: Add the rest
    while (i < intervals.length) {
        result.add(intervals[i++]);
    }

    return result.toArray(new int[result.size()][]);
}
```

***

### 🔴 Hard Example: Minimum Number of Meeting Rooms

**Problem:** Find minimum rooms required to schedule all intervals (no overlaps per room).

#### Trick:

Use a **min-heap to track end times** of meetings.

```java
javaCopyEditpublic int minMeetingRooms(int[][] intervals) {
    if (intervals.length == 0) return 0;
    Arrays.sort(intervals, (a, b) -> a[0] - b[0]);

    PriorityQueue<Integer> heap = new PriorityQueue<>();
    heap.offer(intervals[0][1]); // add end time

    for (int i = 1; i < intervals.length; i++) {
        if (intervals[i][0] >= heap.peek()) {
            heap.poll(); // reuse room
        }
        heap.offer(intervals[i][1]);
    }

    return heap.size(); // number of rooms needed
}
```

***

### 🔁 Summary Table

| Problem Type                               | Pattern                                  |
| ------------------------------------------ | ---------------------------------------- |
| Merge overlapping intervals                | Sort + compare start/end                 |
| Insert interval into list                  | Same as merge, but extra start/end logic |
| Count meeting rooms                        | Min Heap based on end times              |
| Find common free time (multiple schedules) | Merge + invert intervals                 |
| Remove minimum intervals to avoid overlap  | Greedy with sorting by end time          |

***

### 🧩 Practice Problems (30)

#### ✅ Easy (10)

1. Merge Intervals
2. Interval List Intersections
3. Merge Sorted Intervals
4. Non-overlapping Intervals
5. Find if Any Overlap Exists
6. Merge Overlapping Bookings
7. Find Meeting Overlaps
8. Remove Covered Intervals
9. Insert Interval (simplified)
10. Schedule Non-Overlapping Activities

***

#### 🟡 Medium (10)

1. Insert Interval
2. Employee Free Time
3. Minimum Number of Arrows to Burst Balloons
4. Maximum Number of Non-overlapping Intervals
5. Erase Overlapping Intervals
6. Can Attend All Meetings
7. Minimum Meeting Rooms
8. Find Available Time Slots
9. Video Streaming Buffer Ranges
10. Merge Overlapping Intervals in 2 Lists

***

#### 🔴 Hard (10)

1. Meeting Rooms II
2. Split Intervals to Equal Parts
3. Maximum CPU Load (LeetCode Hard)
4. Project Scheduling With Dependencies
5. Smallest Range Covering Elements from K Lists
6. Range Module
7. Car Pooling
8. Train Platform Scheduling
9. Split Array with Equal Sum Intervals
10. Max Overlap of Intervals

***

### 📘 Pro Tips

* Always sort by **start time**
* Merge if `prev.end >= curr.start`
* If solving for **"how many active intervals at once"**, use:
  * **Heap for end times**
  * **Sweep line technique (event points)**
