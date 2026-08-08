---
title: Sorting
tags: [algorithms, cs61b, sorting]
---

# Sorting（排序）

一句话核心：**比较排序最优只能到 Θ(N log N)；实际选哪种取决于数据特征（有序度、稳定性、内存），非比较的基数排序可以做到线性**。

## 基本概念

- **稳定排序**：相等元素的相对顺序保持不变（对多关键字排序重要）；
- **自适应排序**：利用数组已有的有序性（逆序对 K 少时更快）。

## 主要算法

| 算法 | 最坏 | 最好 | 额外空间 | 稳定 |
| --- | --- | --- | --- | --- |
| 选择排序 | Θ(N²) | Θ(N²) | Θ(1) | 否 |
| 插入排序 | Θ(N²) | Θ(N) | Θ(1) | 是 |
| 归并排序 | Θ(N log N) | Θ(N log N) | Θ(N) | 是 |
| 堆排序 | Θ(N log N) | Θ(N log N) | Θ(1) | 否 |
| 快速排序 | Θ(N²) | Θ(N log N) | Θ(log N) | 通常不稳定 |

- **插入排序**：几乎有序时 Θ(N + K)，K = 逆序对数量，可以接近线性；
- **归并排序**：最坏也 Θ(N log N)，代价是 Θ(N) 辅助空间；
- **快速排序**：平均/最好 Θ(N log N)，最坏（每次分区都选到极端 pivot）Θ(N²)；Hoare 分区不稳定；**QuickSelect**（只排一边）期望 Θ(N) 求第 k 小。

## 理论下界

- 任何基于比较的排序，最坏至少需要 Ω(N log N) 次比较（"20 问"论证：N 个元素有 N! 种排列，需 lg(N!) ≈ N log N 个是非问题）。
- 因此归并排序在渐近意义下已经最优；要突破下界必须**不比较**。

## 非比较排序（基数排序）

- **计数排序（counting sort）**：按取值范围计数，稳定，Θ(N+R)（R 为字母表大小）；
- **LSD 基数排序**：从最低位到最高位逐位稳定排序，Θ(WN + WR) ≈ Θ(WN)；
- **MSD 基数排序**：从最高位开始分治，最坏同 LSD，最好 Θ(N+R)；
- 整数排序：按 base 16/256/65536 处理，减少位数 W。
- 对比：比较排序处理等长字符串最坏 Θ(WN log N)，LSD 是 Θ(WN)，N 大时更快；但常数因子和缓存等现实因素会让比较排序反超（JIT/工程原因）。

## 关联

- [[Heaps and Priority Queues]]：堆排序的基础
- [[Asymptotic Analysis]]：复杂度分析工具
- [[CS61B 教材]]、[[Algorithms 4ed 教材]]：来源

## 来源

[[raw/CS61B/29.-basic-sorts|CS61B 第 29 章 Basic Sorts]]、[[raw/CS61B/30.-quicksort|第 30 章 Quicksort]]、[[raw/CS61B/31.-more-quick-sort-sorting-summary|第 31 章 Quick Sort 总结]]、[[raw/CS61B/32.-sorting-and-algorithmic-bounds|第 32 章 排序下界]]、[[raw/CS61B/33.-radix-sorts|第 33 章 Radix Sorts]]；Algorithms 4ed 讲义 21-24
