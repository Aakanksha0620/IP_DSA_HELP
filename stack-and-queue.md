# Stack & Queue

## 📘 Module 5: Stack & Queue – “Mastering Linear Control Flow”

***

### 📍1. DECISION DIAGRAM – Stack vs Queue

```
textCopyEdit                    ┌──────────────┐
                    │  Problem Qn? │
                    └──────┬───────┘
                           │
      ┌────────────────────┴────────────────────┐
      ▼                                         ▼
  LIFO behavior needed?                  FIFO behavior?
   (Reverse, undo, nested)         (Level order, scheduling)
      │                                         │
 Use Stack                                 Use Queue
      │                                         │
  ┌───┴───────────────┐              ┌──────────┴──────────────┐
  ▼                   ▼              ▼                         ▼
Monotonic/            Expression   BFS traversal          Circular Queue /
Next Greater            Parsing      in Trees             Sliding Window
```

> 🔍 **Tip**: Use Stack when you need to **remember history**, and Queue when you need to **process in order**.

***

### 🧠2. FLASHCARD – Stack & Queue Essentials

| Concept                       | Use Case                                              |
| ----------------------------- | ----------------------------------------------------- |
| 🔁 Stack (LIFO)               | Reverse, Parentheses, Infix → Postfix, Function calls |
| 🧾 Monotonic Stack            | Next Greater/Smaller Element                          |
| 📚 Queue (FIFO)               | Level Order Traversal, Scheduling                     |
| 🌀 Deque (Double-Ended Queue) | Sliding Window Max/Min                                |
| ⏳ Stack + Recursion           | DFS traversal                                         |
| 🧠 Queue + Visited            | BFS traversal in Graphs, Grids                        |

> 🔖 Mnemonic: "**SMaQDe** – Stack, Monotonic, Queue, Deque"

***

### 📚3. PROBLEM-SOLVING HEURISTICS

#### ✳️ Stack Template (Balanced Brackets / Infix to Postfix)

```java
javaCopyEditStack<Character> stack = new Stack<>();
for (char c : s.toCharArray()) {
    if (isOpening(c)) stack.push(c);
    else if (isClosing(c)) {
        if (stack.isEmpty() || !isMatching(stack.pop(), c))
            return false;
    }
}
return stack.isEmpty();
```

***

#### ✳️ Monotonic Stack (Next Greater Element)

```java
javaCopyEditStack<Integer> stack = new Stack<>();
for (int i = n - 1; i >= 0; i--) {
    while (!stack.isEmpty() && arr[i] >= stack.peek()) stack.pop();
    result[i] = stack.isEmpty() ? -1 : stack.peek();
    stack.push(arr[i]);
}
```

***

#### ✳️ Queue Template (BFS)

```java
javaCopyEditQueue<TreeNode> queue = new LinkedList<>();
queue.offer(root);
while (!queue.isEmpty()) {
    TreeNode node = queue.poll();
    // process node
    if (node.left != null) queue.offer(node.left);
    if (node.right != null) queue.offer(node.right);
}
```

***

#### ✳️ Deque (Sliding Window Max)

```java
javaCopyEditDeque<Integer> dq = new LinkedList<>();
for (int i = 0; i < nums.length; i++) {
    while (!dq.isEmpty() && dq.peekFirst() <= i - k) dq.pollFirst();
    while (!dq.isEmpty() && nums[dq.peekLast()] < nums[i]) dq.pollLast();
    dq.offerLast(i);
    if (i >= k - 1) result.add(nums[dq.peekFirst()]);
}
```

***

### 🔄4. MISTAKES TO AVOID

| Mistake                            | Tip                                        |
| ---------------------------------- | ------------------------------------------ |
| Pushing before popping correctly   | Always handle stack top before pushing new |
| Infinite loops in BFS              | Maintain `visited` set                     |
| Incorrect Deque window maintenance | Carefully update start and end             |
| Not handling empty stack           | Always check `.isEmpty()` before `.pop()`  |

***

### 🧩5. CURATED PROBLEM SET

#### ✅ Easy (10)

1. Valid Parentheses (LC 20)
2. Min Stack (LC 155)
3. Implement Queue using Stack (LC 232)
4. Implement Stack using Queues (LC 225)
5. Reverse a String using Stack
6. Evaluate Postfix Expression
7. Next Greater Element I (LC 496)
8. Circular Queue Design
9. Remove All Adjacent Duplicates (LC 1047)
10. Basic Calculator II

***

#### 🟡 Medium (10)

1. Next Greater Element II (LC 503)
2. Daily Temperatures (LC 739)
3. Sliding Window Maximum (LC 239)
4. Asteroid Collision (LC 735)
5. Simplify Path (LC 71)
6. Decode String (LC 394)
7. Evaluate Reverse Polish Notation (LC 150)
8. Design Circular Deque (LC 641)
9. Number of Recent Calls (LC 933)
10. Largest Rectangle in Histogram (LC 84)

***

#### 🔴 Hard (10)

1. Trapping Rain Water (LC 42) 🔗 Stack
2. Basic Calculator (LC 224) 🔗 Stack
3. Remove K Digits (LC 402)
4. Expression Evaluation with Precedence
5. Maximal Rectangle (LC 85)
6. Exclusive Time of Functions (LC 636)
7. Shortest Subarray with Sum ≥ K
8. Sum of Subarray Minimums
9. Asteroid Collision with Directions
10. Sliding Window Median

***

### ❓6. QUIZ – STACK & QUEUE MASTERY

1. **"Track max value in last K elements of stream"**\
   a. Stack\
   b. Deque ✅\
   c. Priority Queue
2. **"Convert infix to postfix expression"**\
   a. Queue\
   b. Stack ✅\
   c. Set
3. **"Evaluate `3 + (2 * 2)`"**\
   a. Stack ✅\
   b. Greedy\
   c. DP
4. **"BFS traversal of tree"**\
   a. Stack\
   b. Recursion\
   c. Queue ✅

***

### 🧠7. FEYNMAN REFLECTION PROMPTS

* When is stack preferred over recursion and vice versa?
* Why does BFS use a queue and DFS use a stack?
* What’s the trick behind monotonic stacks?
* How does Deque help in O(n) sliding window?

<figure><img src=".gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>
