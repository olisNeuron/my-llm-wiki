---
title: Linked Lists and Dynamic Arrays
tags: [data-structures, cs61b, linked-list, array]
---

# Linked Lists and Dynamic Arrays

一句话核心：**链表用指针串联分散的内存，数组用连续内存换取随机访问；两者通过封装（ADT）和哨兵节点等技巧变成好用且高效的表**。

## 引用与对象（前置知识）

- Java 变量里存的是 bits：基本类型存值，引用类型存对象地址；`=` 复制的是 bits。
- 黄金法则（GRoE, Golden Rule of Equals）：`b = a` 后 b 和 a 指向同一对象，改 b 会改 a。
- 参数传递按值传递（复制引用），对象本身共享。

## 链表演进（CS61B 的主线）

- **IntList**：递归定义（`first` + `rest`），裸链表，操作繁琐。
- **SLList**：封装 IntNode，对外只暴露 `addFirst/addLast/getFirst/size` 等方法。
  - 用 `size` 缓存让 `size()` 变 O(1)；
  - 用**哨兵节点（sentinel）**消除空表特殊情况，形成不变量：`sentinel` 永远指向哨兵节点，首元素在 `sentinel.next`。
- **DLList**：加 prev 指针，让前端和后端都能 O(1) 增删查；用双哨兵或环形哨兵避免特殊情况。

## 数组与动态数组

- 数组：连续内存、随机访问 O(1)，但定长；`get(i)` 直接寻址，不需要像链表那样遍历。
- **AList / Resizing ArrayList**：满时扩容。
  - 朴素"每次 +1"扩容：每次复制 O(N)，整体 O(N²)；
  - **几何扩容（翻倍）**：摊还后 `addLast` 为 O(1)。

## 运行时间对比

| 操作 | SLList | DLList（带尾指针） | AList/ArrayList |
| --- | --- | --- | --- |
| addFirst | O(1) | O(1) | O(N)（要挪元素） |
| addLast | O(1)（缓存尾） | O(1) | 摊还 O(1) |
| get(i) | O(N) | O(N) | O(1) |
| removeLast | O(N)（要找到倒数第二个） | O(1) | O(1) |

## 关联

- [[Heaps and Priority Queues]]：堆正是用数组表示完全二叉树
- [[Trees and Balanced Search Trees]]：链表思想延伸为树
- [[CS61B 教材]]：来源与章节地图

## 来源

[[raw/CS61B/3.-references-recursion-and-lists|第 3 章 引用/递归/链表]]、[[raw/CS61B/5.-sllists|第 5 章 SLLists]]、[[raw/CS61B/6.-dllists-and-arrays|第 6 章 DLLists and Arrays]]、[[raw/CS61B/7.-resizing-arraylist|第 7 章 Resizing ArrayList]]
