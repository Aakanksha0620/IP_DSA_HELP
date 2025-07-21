# Heaps & Priority Queues

## 📘 Module 8: Heaps & Priority Queues – “Think Top K, Think Heap”

***

### 📍1. DECISION DIAGRAM – When to Use Heaps

```
textCopyEdit                    ┌──────────────┐
                    │  Problem Qn? │
                    └─────┬────────┘
                          │
        ┌─────────────────┴──────────────────┐
        ▼                                    ▼
  Do you need min/max frequently?     Do you need top/bottom K elements?
        │                                    │
   Use Min/Max Heap                    Use PriorityQueue or Custom Heap
        │                                    │
  ┌─────┴─────────────┐             ┌────────┴──────────┐
  ▼                   ▼             ▼                   ▼
 Heapify, Insert     Extract       Sort-like logic     Dynamic Stream
```

> 🔍 Tip: Use heaps when you want **constant access to extreme values (min/max)** in dynamic datasets.

***

### 🧠2. FLASHCARD – Heaps Made Simple

| Concept              | Use Case                               |
| -------------------- | -------------------------------------- |
| 🔼 Min-Heap          | Smallest on top (default in Java)      |
| 🔽 Max-Heap          | Largest on top (via custom comparator) |
| 📊 PriorityQueue     | Java’s implementation of heap          |
| 🛠️ Heapify          | Convert array to valid heap in O(n)    |
| ⚖️ Top K Elements    | Always track k largest/smallest        |
| 🔁 Custom Comparator | Sort based on custom logic             |

> 🔖 Mnemonic: **"Hi PQ SCaM"** — Heapify, PriorityQueue, Sort, Custom, Max

***

### 📚3. HEAP TEMPLATES & USAGE

#### ✳️ Java Min-Heap

```java
javaCopyEditPriorityQueue<Integer> minHeap = new PriorityQueue<>();
```

***

#### ✳️ Java Max-Heap

```java
javaCopyEditPriorityQueue<Integer> maxHeap = new PriorityQueue<>((a, b) -> b - a);
```

***

#### ✳️ Top K Elements (Max-Heap or Min-Heap)

```java
javaCopyEditPriorityQueue<Integer> pq = new PriorityQueue<>(); // minHeap for K largest
for (int num : nums) {
    pq.offer(num);
    if (pq.size() > k) pq.poll(); // remove smallest to retain top k
}
```

***

#### ✳️ Custom Object Comparator

```java
javaCopyEditPriorityQueue<Pair> pq = new PriorityQueue<>((a, b) -> a.freq - b.freq);
```

***

### 🔄4. MISTAKES TO AVOID

| Mistake                                  | Tip                                         |
| ---------------------------------------- | ------------------------------------------- |
| Forgetting custom comparator for MaxHeap | Java default is MinHeap only                |
| Not controlling heap size                | Use `pq.size() > k` logic in Top K problems |
| Polling too soon                         | Add elements first, then prune heap         |
| Confusing full sort vs partial top K     | Heap gives partial order, not full sorted   |

***

### 🧩5. CURATED PROBLEM SET

#### ✅ Easy (10)

1. Kth Largest Element in a Stream (LC 703)
2. Merge K Sorted Lists (LC 23)
3. Top K Frequent Elements (LC 347)
4. Find K Closest Elements (LC 658)
5. Last Stone Weight (LC 1046)
6. Minimum Cost to Connect Ropes
7. Sort Characters by Frequency (LC 451)
8. Seat Reservation Manager
9. Max Heap Implementation using Array
10. Design a Min Stack using 2 heaps

***

#### 🟡 Medium (10)

1. Kth Largest Element in Array (LC 215)
2. Task Scheduler (LC 621)
3. Sliding Window Median
4. Reorganize String (LC 767)
5. Dijkstra's Algorithm (Shortest Path)
6. Frequency Sort (LC 347)
7. Smallest Range Covering Elements from K Lists (LC 632)
8. Median from Data Stream (LC 295)
9. Top K Frequent Words (LC 692)
10. Find Median in Running Stream

***

#### 🔴 Hard (10)

1. Trapping Rain Water II (LC 407)
2. Skyline Problem (LC 218)
3. Maximum Frequency Stack (LC 895)
4. Merge K Sorted Arrays
5. Minimum Interval to Include Each Query
6. The Kth Smallest Prime Fraction
7. Shortest Distance from All Buildings
8. Find K Pairs with Smallest Sums
9. Cheapest Flights Within K Stops
10. Minimum Time to Complete Tasks with Cooldown

***

### ❓6. QUIZ – HEAP UP!

1. **"Find top 5 frequent elements"**\
   a. Sort\
   b. Heap ✅\
   c. BFS
2. **"Kth largest in array of 1M numbers"**\
   a. Full sort\
   b. Min-Heap of size K ✅\
   c. HashMap
3. **"Reorganize string without same adjacent characters"**\
   a. Stack\
   b. Max-Heap + Greedy ✅\
   c. Trie
4. **"Dynamic median of streaming data"**\
   a. Merge Sort\
   b. 2 Heaps (Max+Min) ✅\
   c. HashSet

***

### 🧠7. FEYNMAN REFLECTION PROMPTS

* Why do we prefer heaps over sorting for Top-K problems?
* How does the size of the heap affect time complexity?
* What’s the difference between MinHeap and PriorityQueue?
* Can heap be used for dynamic sorting?
