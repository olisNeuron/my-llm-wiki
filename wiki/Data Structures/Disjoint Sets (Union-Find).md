---
title: Disjoint Sets (Union-Find)
tags: [data-structures, cs61b, union-find]
---

# Disjoint Sets（Union-Find / 并查集）

一句话核心：**维护"哪些元素连通"的集合关系，用树 + 按大小合并 + 路径压缩，把 connect/isConnected 做到摊还几乎常数 O(α(N))**。

## ADT

- `connect(x, y)`：把 x、y 所在的集合合并；
- `isConnected(x, y)`：判断 x、y 是否在同一集合。

## 四代实现（设计演进的教科书案例）

| 实现 | connect | isConnected | 思路 |
| --- | --- | --- | --- |
| List of Sets | Θ(N) | O(N) | 线性扫描找集合 |
| QuickFind | Θ(N) | Θ(1) | 数组直接存集合编号 |
| QuickUnion | O(N) | O(N) | 树形结构，向上找根 |
| **Weighted Quick Union** | **O(log N)** | **O(log N)** | 总是把小树接在大树下，树高 ≤ log N |
| **WQU + 路径压缩** | **摊还 O(α(N))** | **摊还 O(α(N))** | find 时把路径上的节点直接指向根 |

- 路径压缩后，M 次操作在 N 个元素上的总代价是 O(N + M·lg\*N)，lg\*（迭代对数）对现实规模小于 5，通常写作 O(α(N))。

## 关键教训

- 初始设计决策（用什么数据结构）直接决定代码复杂度和运行时间；
- 小优化（按大小合并、路径压缩）能把"线性"变成"几乎常数"。

## 应用

- [[Minimum Spanning Trees]]：Kruskal 算法用它合并边；
- 动态连通性（网络、图像连通域、渗透模型）。

## 关联

- [[Minimum Spanning Trees]]：Kruskal 的核心组件
- [[CS61B 教材]]：来源与章节地图

## 来源

[[raw/CS61B/14.-disjoint-sets|第 14 章 Disjoint Sets]]
