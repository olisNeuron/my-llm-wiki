---
title: Trees and Balanced Search Trees
tags: [data-structures, cs61b, bst, b-tree, red-black-tree]
---

# Trees and Balanced Search Trees

一句话核心：**BST 让查找/插入/删除在有序数据上达到对数时间，但会退化；B 树（2-3 树）和红黑树用"保持平衡"的不变量把最坏情况也锁在对数级**。

## 二叉搜索树（BST）

- 定义（BST 性质）：对每个节点 X，左子树所有 key < X，右子树所有 key > X。
- 操作：search、insert、delete（删两个孩子的节点时用前驱/后继替换）。
- 性能：树平衡时 contains/add/delete 为 Θ(log N)；**最坏退化成链表 Θ(N)**（如按有序序列插入）。
- 概念区分：BST 高度是 O(N)（上界），但只有平衡时才是 Θ(log N)；**Big-O ≠ 最坏情况**，最坏情况同样可以用 Θ 描述。

## B 树（2-3 树家族）

- 节点可放多个 key（如最多 L 个），插入时**分裂节点**，从根到叶始终**完美平衡**。
- 两个不变量保证树"矮胖"：所有叶节点深度相同；节点内 key 数量受上下限约束（如 1~L）。
- 高度在 log₂N 与 log(L+1)N 之间 → Θ(log N)；contains/add 都是 O(log N)（L 是常数）。
- 现实意义：数据库、文件系统（磁盘 I/O 友好）。

## 左倾红黑树（LLRB）

- **与 2-3 树一一对应**：红色链接表示"合并进父节点的 key"。
- 不变量：没有节点带两条红链接；没有右红链接；根到每个叶子的黑链接数相同。
- 插入：按 BST 插入，新链接默认红色，然后用 **rotateLeft / rotateRight / 颜色翻转**修复不变量。
- 性能：高度不超过对应 2-3 树的 2 倍 → 操作 O(log N)。

## 关联

- [[Tries]]：另一类按前缀组织的树
- [[Heaps and Priority Queues]]：完全二叉树用数组表示
- [[Sorting]]：BST 中序遍历就是有序输出
- [[CS61B 教材]]：来源与章节地图

## 来源

[[raw/CS61B/15.-bsts|第 15 章 Binary Search Trees]]、[[raw/CS61B/16.-b-trees|第 16 章 B-Trees]]、[[raw/CS61B/17.-red-black-trees|第 17 章 Red Black Trees]]
