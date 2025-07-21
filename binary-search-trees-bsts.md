# Binary Search Trees (BSTs)

## 📘 Module 7: Binary Search Trees – “Sorted Power in Tree Form”

***

### 📍1. DECISION DIAGRAM – When to Use BSTs

```
textCopyEdit                    ┌──────────────┐
                    │ Tree Problem │
                    └─────┬────────┘
                          │
        ┌─────────────────┴──────────────────┐
        ▼                                    ▼
  Do nodes follow order?            Is there efficient lookup needed?
   (Left < Root < Right)                (min, max, k-th smallest)
        │                                    │
  Use Binary Search Tree             Use Inorder Traversal + Logic
        │                                    │
  ┌─────┴─────────────┐             ┌────────┴──────────┐
  ▼                   ▼             ▼                   ▼
 Search, Insert      Delete     Range Queries     Balanced BSTs
```

> 🔍 Tip: Use BST when you need **sorted dynamic data** with fast search/insert/delete.

***

### 🧠2. FLASHCARD – BST Essentials

| Concept                             | Use Case                                        |
| ----------------------------------- | ----------------------------------------------- |
| 🔍 Search (O(log n))                | Find a node                                     |
| ➕ Insert/Delete                     | Maintain sorted structure                       |
| 🔁 Inorder Traversal                | Always sorted in BST                            |
| 🎯 K-th Smallest/Largest            | Inorder + Counter                               |
| 🔃 Convert Sorted Array/List to BST | Balanced construction                           |
| ⚖️ AVL Trees (Intro)                | Self-balancing BSTs (not covered in-depth here) |

> 🔖 Mnemonic: **"SORTed" – Search, Order, Range, Treeified**

***

### 📚3. OPERATIONS & TEMPLATES

#### ✳️ Search in BST

```java
javaCopyEditTreeNode searchBST(TreeNode root, int val) {
    if (root == null || root.val == val) return root;
    return val < root.val
        ? searchBST(root.left, val)
        : searchBST(root.right, val);
}
```

***

#### ✳️ Insert in BST

```java
javaCopyEditTreeNode insert(TreeNode root, int val) {
    if (root == null) return new TreeNode(val);
    if (val < root.val) root.left = insert(root.left, val);
    else root.right = insert(root.right, val);
    return root;
}
```

***

#### ✳️ Delete in BST

```java
javaCopyEditTreeNode delete(TreeNode root, int key) {
    if (root == null) return null;
    if (key < root.val) root.left = delete(root.left, key);
    else if (key > root.val) root.right = delete(root.right, key);
    else {
        if (root.left == null) return root.right;
        if (root.right == null) return root.left;
        TreeNode min = getMin(root.right);
        root.val = min.val;
        root.right = delete(root.right, min.val);
    }
    return root;
}
```

***

#### ✳️ Get K-th Smallest

```java
javaCopyEditint count = 0, result = -1;
void inorder(TreeNode root, int k) {
    if (root == null) return;
    inorder(root.left, k);
    if (++count == k) result = root.val;
    inorder(root.right, k);
}
```

***

### 🔄4. MISTAKES TO AVOID

| Mistake                   | Tip                                                   |
| ------------------------- | ----------------------------------------------------- |
| Forgetting BST invariant  | Always maintain left < root < right                   |
| Not updating parent links | In deletion, restructure carefully                    |
| Misusing traversal        | Inorder gives sorted values                           |
| Not balancing BST         | Use AVL/Red-Black Trees for balance (intro only here) |

***

### 🧩5. CURATED PROBLEM SET

#### ✅ Easy (10)

1. Search in a Binary Search Tree (LC 700)
2. Insert into a BST (LC 701)
3. Minimum Absolute Difference in BST (LC 530)
4. Range Sum of BST (LC 938)
5. Convert Sorted Array to BST (LC 108)
6. Convert Sorted List to BST (LC 109)
7. Validate BST (LC 98)
8. Floor and Ceil in BST
9. Find Max/Min in BST
10. Inorder Successor in BST

***

#### 🟡 Medium (10)

1. Delete Node in a BST (LC 450)
2. K-th Smallest Element in BST (LC 230)
3. Trim a BST (LC 669)
4. Lowest Common Ancestor in BST (LC 235)
5. BST to Greater Sum Tree (LC 1038)
6. Recover BST (LC 99)
7. Merge Two BSTs
8. Find Mode in BST (LC 501)
9. Two Sum in BST
10. Closest Value in BST (LC 270)

***

#### 🔴 Hard (10)

1. Serialize & Deserialize BST (LC 449)
2. Count BSTs (Catalan Number logic)
3. Construct BST from Preorder (LC 1008)
4. Predecessor and Successor
5. Range Queries on BST
6. Convert BST to DLL (LC 426)
7. Largest BST in a Binary Tree
8. Median of BST
9. Find K-th Largest in BST
10. BST Iterator (LC 173)

***

### ❓6. QUIZ – BST LOGIC

1. **"Find 3rd smallest element in BST"**\
   a. BFS\
   b. Inorder + Counter ✅\
   c. Postorder
2. **"Delete node with 2 children in BST"**\
   a. Replace with parent\
   b. Replace with inorder successor ✅\
   c. Just remove it
3. **"Check if a tree is BST"**\
   a. DFS\
   b. Inorder Traversal + Condition ✅\
   c. Level Order
4. **"Build BST from preorder array"**\
   a. Sort & Build\
   b. Use stack & bounds ✅\
   c. BFS

***

### 🧠7. FEYNMAN REFLECTION PROMPTS

* Why is inorder traversal always sorted in BST?
* What makes BST faster than normal binary trees?
* What breaks the BST property during insertion or deletion?
* Can you optimize search without recursion?
