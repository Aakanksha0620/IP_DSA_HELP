# Binary Trees

## 📘 Module 6: Binary Trees – “Branching into Hierarchical Thinking”

***

### 📍1. DECISION DIAGRAM – How to Approach Tree Problems

```
textCopyEdit                      ┌────────────┐
                      │ Tree Qn?  │
                      └─────┬──────┘
                            │
        ┌───────────────────┴────────────────────┐
        ▼                                        ▼
   Is traversal needed?                  Is comparison between nodes?
  (DFS, BFS, Level Order)              (Symmetry, LCA, Same Tree, etc.)
        │                                        │
 Recursive or Iterative DFS?                Use Recursion + Logic
        │                                        │
  ┌─────┴─────┐                         ┌────────┴─────────┐
  ▼           ▼                         ▼                  ▼
 Inorder     Level Order           LCA, Mirror,         Subtree, Path
 Pre/Post    (Queue)               Height/Diameter      Sum, Distance K
```

> 🔍 **Tip**: Trees = Recursion + Patterns. Memorize base + recursive case logic.

***

### 🧠2. FLASHCARD – Binary Tree Essentials

| Concept                   | Use Case                         |
| ------------------------- | -------------------------------- |
| 🔁 DFS (Inorder/Pre/Post) | Visit all nodes recursively      |
| 📊 BFS (Level Order)      | Layer-wise traversal using Queue |
| 🔄 Recursive Traversal    | Tree construction, mirror        |
| 📐 Height & Diameter      | Depth, balance checks            |
| 🔍 LCA                    | Lowest common ancestor           |
| 📦 Serialization          | Store/recreate tree from string  |

> 🔖 Mnemonic: **"Tree HeLP DiSC"** – Traversals, Height, LCA, Path, Diameter, Serialization, Children

***

### 📚3. TRAVERSAL PATTERNS

#### ✳️ Inorder (Left, Root, Right)

```java
javaCopyEditvoid inorder(TreeNode root) {
    if (root == null) return;
    inorder(root.left);
    visit(root);
    inorder(root.right);
}
```

***

#### ✳️ Level Order (Queue)

```java
javaCopyEditQueue<TreeNode> q = new LinkedList<>();
q.offer(root);
while (!q.isEmpty()) {
    TreeNode curr = q.poll();
    if (curr.left != null) q.offer(curr.left);
    if (curr.right != null) q.offer(curr.right);
}
```

***

#### ✳️ LCA (Lowest Common Ancestor)

```java
javaCopyEditTreeNode lowestCommonAncestor(TreeNode root, TreeNode p, TreeNode q) {
    if (root == null || root == p || root == q) return root;
    TreeNode left = lowestCommonAncestor(root.left, p, q);
    TreeNode right = lowestCommonAncestor(root.right, p, q);
    return (left != null && right != null) ? root : (left != null ? left : right);
}
```

***

#### ✳️ Diameter of Binary Tree

```java
javaCopyEditint diameter = 0;
int dfs(TreeNode node) {
    if (node == null) return 0;
    int left = dfs(node.left);
    int right = dfs(node.right);
    diameter = Math.max(diameter, left + right);
    return 1 + Math.max(left, right);
}
```

***

### 🔄4. MISTAKES TO AVOID

| Mistake                       | Tip                                                 |
| ----------------------------- | --------------------------------------------------- |
| Not handling null nodes       | Always add base case `if (node == null)`            |
| Using global state carelessly | Reset shared variables per test case                |
| Confusing Pre/In/Post logic   | Write down traversal orders                         |
| Forgetting depth/height diff  | Depth = root to node; Height = node to deepest leaf |

***

### 🧩5. CURATED PROBLEM SET

#### ✅ Easy (10)

1. Inorder/Preorder/Postorder Traversal (Recursive & Iterative)
2. Maximum Depth of Binary Tree (LC 104)
3. Symmetric Tree (LC 101)
4. Same Tree (LC 100)
5. Invert Binary Tree (LC 226)
6. Count Leaf Nodes
7. Height of Binary Tree
8. Print Nodes at K Distance
9. Sum of All Nodes
10. Path Sum (LC 112)

***

#### 🟡 Medium (10)

1. Binary Tree Level Order Traversal (LC 102)
2. Diameter of Binary Tree (LC 543)
3. Construct Binary Tree from Inorder and Preorder (LC 105)
4. Zigzag Level Order Traversal (LC 103)
5. Right Side View of Tree (LC 199)
6. Lowest Common Ancestor (LC 236)
7. Check for Balanced Binary Tree
8. Path Sum II (LC 113)
9. Flatten Binary Tree to Linked List (LC 114)
10. Sum Root to Leaf Numbers (LC 129)

***

#### 🔴 Hard (10)

1. Serialize and Deserialize Binary Tree (LC 297)
2. Vertical Order Traversal (LC 987)
3. Count Complete Tree Nodes (LC 222)
4. Distance Between Two Nodes in Binary Tree
5. Binary Tree Maximum Path Sum (LC 124)
6. Boundary Traversal of Binary Tree
7. Morris Inorder Traversal
8. Longest ZigZag Path in Binary Tree
9. Recover Binary Search Tree (LC 99)
10. All Nodes Distance K in Binary Tree (LC 863)

***

### ❓6. QUIZ – TREE SMARTS

1. **"Find sum of all left leaf nodes"**\
   a. Level Order\
   b. Inorder\
   c. DFS with Condition ✅
2. **"Find diameter of binary tree"**\
   a. Max Depth\
   b. DFS + Global Max ✅\
   c. BFS
3. **"Build tree from preorder + inorder"**\
   a. Stack\
   b. HashMap + Recursion ✅\
   c. Level Order
4. **"Lowest Common Ancestor of p and q"**\
   a. BFS\
   b. Recursive Search ✅\
   c. Binary Search

***

### 🧠7. FEYNMAN REFLECTION PROMPTS

* What’s the difference between **depth** and **height** in trees?
* How do recursive calls unfold in LCA problems?
* Why is level order BFS better than DFS for layered output?
* What’s the use of serializing a tree?
