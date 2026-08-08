---
title: Shortest Paths
tags: [algorithms, cs61b, graph, dijkstra]
---

# Shortest Paths（最短路）

一句话核心：**从 BFS（无权）到 Dijkstra（带权非负）、再到 DAG 上的拓扑松弛，最短路的正确性建立在"先确定者最优"的不变量上**。

## BFS（无权图）

- 无权图最短路 = 最少边数；BFS 按层扩展，首次到达即最短；O(V+E)。
- DFS 只保证"找到路径"，不保证最短。

## Dijkstra

- 思路：优先队列按当前已知距离取最近节点，**松弛（relax）**它的邻居。
- 不变量：**节点出队那一刻，它的最短路径已确定**（前提：边权非负）。
- 负权边会让不变量失效（B→C 可能被错误更新），所以 Dijkstra 不能处理负权。
- 运行时间：O((V+E) log V)（堆操作主导；E > V 时可写作 O(E log V)）。

## A*

- 在 Dijkstra 基础上加**启发式**（估计到终点的距离）优先扩展"看起来更有希望"的节点；
- 启发式必须**乐观（admissible）**才能保证最优；坏启发式会退化成 Dijkstra 或更差。

## DAG 上的最短路

- 先**拓扑排序**（DFS，O(V+E)），再按拓扑序依次松弛 → 总 O(V+E)，且**可以处理负权**。
- DAG 上最长路径同样 O(V+E)；一般图的最长路径是 NP 难题（见 [[Complexity and P vs NP]]）。

## 关联

- [[Graphs and Traversals]]：BFS/DFS 基础
- [[Heaps and Priority Queues]]：Dijkstra 的优先队列
- [[CS61B 教材]]、[[Algorithms 4ed 教材]]：来源

## 来源

[[raw/CS61B/21.-shortest-paths|CS61B 第 21 章 Shortest Paths]]、[[raw/CS61B/23.-reductions-and-decomposition|第 23 章 Reductions and Decomposition]]；Algorithms 4ed 讲义 44ShortestPaths
