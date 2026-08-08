---
title: Heaps and Priority Queues
tags: [data-structures, cs61b, heap, priority-queue]
---

# Heaps and Priority Queues

一句话核心：**优先队列是"总是取最小"的 ADT；二叉堆用完全二叉树 + 数组表示，让 add 和 removeSmallest 都是 Θ(log N)**。

## 优先队列 ADT

核心操作：`add(x)`、`getSmallest()`、`removeSmallest()`。

各实现的对比（最坏情况）：

| 实现 | add | getSmallest | removeSmallest |
| --- | --- | --- | --- |
| 有序数组 | Θ(N) | Θ(1) | Θ(1) |
| BST | Θ(log N) | Θ(log N) | Θ(log N) |
| 无序数组 | Θ(1) | Θ(N) | Θ(N) |
| **二叉最小堆** | **Θ(log N)** | **Θ(1)** | **Θ(log N)** |

## 二叉堆

- 两个性质：**完全二叉树**（无空洞）+ **min-heap 性质**（每个节点 ≤ 它的两个孩子）。
- 用数组表示：根在 index 1，节点 i 的孩子是 2i 和 2i+1，父是 i/2。
- 操作：
  - `add`：先放到末尾，再 **swim（上浮）** 与父交换直到恢复堆序；
  - `removeSmallest`：把最后一个元素移到根，再 **sink（下沉）**，与更小的孩子交换。
- 数组扩容是摊还的，不影响 O(log N) 结论。

## 应用

- **Heapsort**：建最大堆逐个取最大值，Θ(N log N)（见 [[Sorting]]）；
- **Dijkstra / Prim** 的最优实现（见 [[Shortest Paths]]、[[Minimum Spanning Trees]]）。

## 关联

- [[Sorting]]：堆排序
- [[Shortest Paths]]：Dijkstra 的优先队列
- [[Linked Lists and Dynamic Arrays]]：堆的数组表示基础
- [[CS61B 教材]]：来源与章节地图

## 来源

[[raw/CS61B/18.-heaps-and-priority-queues|第 18 章 Heaps and Priority Queues]]
