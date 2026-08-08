---
title: Minimum Spanning Trees
tags: [algorithms, cs61b, graph, mst]
---

# Minimum Spanning Trees（最小生成树）

一句话核心：**用"割性质"保证贪心正确：每次选跨越割的最小边，Prim 和 Kruskal 都以不同方式实现这个原则**。

## 定义与割性质

- **MST**：连通带权图中，连接所有顶点且总权重最小的无环子图（恰好 V-1 条边）。
- **割性质（cut property）**：把顶点分成两部分的任意"割"，跨越割的所有边中权重最小的那条，一定属于某个 MST。

## Prim 算法

- 从任意顶点开始生长：用优先队列维护"到已选集合"的最小边，每次取最小的边加入。
- 机制与 Dijkstra 相同（"离树最近"而非"离源点最近"），正确性由割性质保证。
- 运行时间：O((V+E) log V)。

## Kruskal 算法

- 把所有边按权重排序，从小到大尝试；若边的两端**不在同一集合**（用并查集判断），就加入。
- 正确性同样是割性质（对当前森林的割取最小边）。
- 运行时间：O(E log E)（排序是瓶颈）；若边已排序，合并/查询由 WQU 路径压缩主导，接近 O(E log\*V)。

## 对比

| | Prim | Kruskal |
| --- | --- | --- |
| 增长方式 | 从一点向外生长一棵树 | 多棵树合并（森林） |
| 数据结构 | 优先队列 | 排序 + 并查集 |
| 适合场景 | 稠密图 | 稀疏图/边可排序 |

## 关联

- [[Disjoint Sets (Union-Find)]]：Kruskal 的合并工具
- [[Shortest Paths]]：Prim 与 Dijkstra 同构
- [[CS61B 教材]]、[[Algorithms 4ed 教材]]：来源

## 来源

[[raw/CS61B/22.-minimum-spanning-trees|CS61B 第 22 章 Minimum Spanning Trees]]；Algorithms 4ed 讲义 43MinimumSpanningTrees
