---
title: Asymptotic Analysis
tags: [algorithms, cs61b, complexity]
---

# Asymptotic Analysis（渐近分析）

一句话核心：**用输入规模 N 的函数刻画算法运行时间与空间，通过"只看最坏情况、去掉低阶项和常数"得到可比较的复杂度**。

## 分析方法

- 把运行时间写成关于 N 的函数 R(N)，再做四条简化：
  1. 通常只关心**最坏情况**；
  2. 选一个代表性操作计数；
  3. 去掉低阶项；
  4. 去掉乘法常数。
- 也可以"画图/几何"论证（嵌套循环 = 三角形面积 → Θ(N²)）。

## 记号

- **Θ**（Big Theta）：精确的增长率（上下界都确定），如 `f ∈ Θ(N)` 就是线性；
- **O**（Big O）：上界（≤），如 `f ∈ O(N)` 可以是常数/对数/线性；
- **Ω**（Big Omega）：下界。
- 注意：**Big O 不等于最坏情况**——最坏情况本身也可以用 Θ 精确描述；O 只是"上界"。
- 对数的底数无关紧要（换底公式），Θ(log₂N) = Θ(log N)。

## 常见结果

- 嵌套循环：Θ(N²)（如 dup1）；
- 二分查找：Θ(log N)（每步减半）；
- 归并排序：Θ(N log N)（每层 O(N)，共 log N 层）；
- 朴素递归（fib）：Θ(2^N)；每个节点做线性工作的二分递归：Θ(N log N)。
- **空间复杂度**只统计算法"额外"使用的内存（输入本身不算，如 Dijkstra 的队列/数组是 Θ(V)）。

## 关联

- [[Sorting]]：复杂度分析的经典应用
- [[CS61B 教材]]、[[Algorithms 4ed 教材]]：来源

## 来源

[[raw/CS61B/11.-asymptotics-i|CS61B 第 11 章 Asymptotics I]]、[[raw/CS61B/12.-asymptotics-ii|第 12 章 Asymptotics II]]、[[raw/CS61B/13.-asymptotics-iii|第 13 章 Asymptotics III]]；Algorithms 4ed 讲义 14AnalysisOfAlgorithms
