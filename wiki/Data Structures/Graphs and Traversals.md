---
title: Graphs and Traversals
tags: [data-structures, cs61b, graph, bfs, dfs]
---

# Graphs and Traversals（图与遍历）

一句话核心：**图用顶点 + 边描述关系；表示方式决定内存与算法运行时间，BFS/DFS 是所有图算法的基础**。

## 图的基础

- 图 = 顶点集合 V + 边集合 E；分类：无向/有向、无权/带权、简单图（无自环/重边）。
- 图的两种主流表示：

| 表示 | 空间 | 判断边 (u,v) | DFS/BFS |
| --- | --- | --- | --- |
| 邻接表 | Θ(V+E) | O(degree) | **O(V+E)** |
| 邻接矩阵 | Θ(V²) | Θ(1) | O(V²) |

## 遍历

- **树遍历**：前序、中序、后序、层序（level order）。
- **DFS**（栈/递归）：一路深入；**BFS**（队列）：按层扩展。
- 关键区别：**BFS 能找到无权图的最短路，DFS 不能保证**；两者运行时间同为 O(V+E)（邻接表）。

## 图问题速览

- 连通性、路径存在性：BFS/DFS 可解；
- 最短路径（带权）：见 [[Shortest Paths]]；
- 最小生成树：见 [[Minimum Spanning Trees]]；
- 难度差异：欧拉回路 O(E) 可解，哈密顿回路至今无多项式算法（NP 问题，见 [[Complexity and P vs NP]]）。

## 关联

- [[Shortest Paths]]：BFS 是 Dijkstra 的特例
- [[Minimum Spanning Trees]]：图上的另一类优化问题
- [[CS61B 教材]]：来源与章节地图

## 来源

[[raw/CS61B/19.-tree-traversals-and-graphs|第 19 章 Tree Traversals and Graphs]]、[[raw/CS61B/20.-graph-traversals-and-implementations|第 20 章 Graph Traversals and Implementations]]
