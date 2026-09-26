---
title: MIT 6.006 算法课
tags: [source, algorithms, mit, 6006]
---

# MIT 6.006 算法课（来源页）

一句话核心：**6.006 是 MIT 的算法入门课，用「数据结构 + 算法范式 + 复杂度分析」三件套把问题—模型—算法串成一条线；它不指定必读书，讲义即教材，CLRS 只是参考。**

## 课程定位

- 官方名 *Introduction to Algorithms*，本科课；Spring 2020 版讲师 Erik Demaine、Jason Ku、Justin Solomon。
- 先修：6.0001（Python 编程）+ 6.042J（离散数学：集合、逻辑、组合、证明、递归、图论、概率）。开学用 Problem Set 0 摸底。
- 评分：Quiz 1（20%）+ Quiz 2（15%）+ Quiz 3（10%）+ Final（35%）+ Problem Sets（18%）+ Recitation（2%）——考试占 80%，说明重心在**手推复杂度、设计并证明算法**，而非写代码。
- 与相邻课的关系：6.006（数据结构 + 基础算法）→ 6.046J（算法设计，Kleinberg & Tardos，进阶）。与 CS61B 内容大量重叠，但 6.006 更强调**形式化分析与证明**（均摊分析、DP 的 SRTBOT 框架、归约）。

## 课程地图（Spring 2020，20 讲）

| # | 主题 | 本库页面 |
| --- | --- | --- |
| 1 | Introduction | — |
| 2 | Data Structures：动态数组、均摊分析 | [[Linked Lists and Dynamic Arrays]] |
| 3 | Sorting：插入/归并/堆排与比较下界 | [[Sorting]] |
| 4 | Hashing：链地址、哈希函数族、动态表 | [[Hash Tables]] |
| 5 | Linear Sorting：计数排序、基数排序 | [[Sorting]] |
| 6–7 | Binary Trees；AVL 平衡树 | [[Trees and Balanced Search Trees]] |
| 8 | Binary Heaps：堆与优先队列 | [[Heaps and Priority Queues]] |
| 9–10 | Breadth-First Search；Depth-First Search | [[Graphs and Traversals]] |
| 11 | Weighted Shortest Paths：松弛、一般结构 | [[Shortest Paths]] |
| 12 | Bellman-Ford：负权与负环 | [[Shortest Paths]] |
| 13 | Dijkstra's Algorithm | [[Shortest Paths]] |
| 14 | All-Pairs Shortest Paths & Johnson's Algorithm | [[Shortest Paths]] |
| 15–18 | Dynamic Programming：SRTBOT 框架、LCS/LIS、硬币找零、背包与伪多项式 | （本库待整理） |
| 19 | Complexity：P / NP / 归约 | [[Complexity and P vs NP]] |
| 20 | Course Review | — |

> 主线可概括为 **数据结构 → 排序/哈希 → 图 → 动态规划 → 复杂度**。动态规划（4 讲）和形式化复杂度是与 CS61B 差异最大的两块；6.006 不讲最小生成树（在 6.046J / CS61B 中）。

## 教科书怎么选

- **CLRS《Introduction to Algorithms》**：6.006 官方参考书（Syllabus 列 3rd ed.；2022 年出 4th ed.）。Fall 2011 版 OCW 的 Readings 页直接按 CLRS 章节指定阅读范围。**课程不要求购买**，讲义已自洽；CLRS 更适合当字典，遇到需要深入或补证明时查阅。
- **免费替代（本库已存）**：
  - [[raw/MIT6006/textbooks/Algorithms-JeffErickson.pdf|Jeff Erickson《Algorithms》]]：覆盖面与 6.006 高度重合（DP、图、NP），讲解偏"人话"，适合与讲义并读；
  - [[raw/MIT6006/textbooks/Mathematics-for-Computer-Science-MIT6042.pdf|MIT 6.042J《Mathematics for Computer Science》]]：补先修（归纳、渐进记号、图论、概率）。
- **其他常见搭配**：
  - Sedgewick & Wayne《Algorithms, 4th ed.》：代码与可视化强，本库已有官方讲义 [[Algorithms 4ed 教材]]；
  - Kleinberg & Tardos《Algorithm Design》：6.046J 主教材，学完 6.006 想进阶再读；
  - Roughgarden《Algorithms Illuminated》：四小册，配 Stanford/Coursera 课程；
  - Skiena《The Algorithm Design Manual》：偏工程实战。

## 怎么用这套材料

- **主线**：按讲读 `raw/MIT6006/lectures/`（20 讲），配合 OCW 视频（课程页 Lecture Videos，视频托管在 archive.org）；每讲后做对应的 `problem-sessions/` 题目对答案。
- **验证掌握**：`problem-sets/` 共 9 套（含模仿先修的 PS0），全部有官方答案；复习用 `exams/` 的 Quiz 1–3 Review + 答案，最后用 Final 计时模拟。
- **配合本库**：先读 [[Asymptotic Analysis]] 建立复杂度语言，再按上面的课程地图跳到对应知识页；讲义 PDF 用于细节回溯。

## 关联

- [[CS61B 教材]]、[[Algorithms 4ed 教材]]：另外两套数据结构/算法来源
- [[自学路线与公开课]]：算法课在整条自学路线中的位置
- [[Asymptotic Analysis]]、[[Sorting]]、[[Shortest Paths]]、[[Complexity and P vs NP]]：课程核心主题

## 来源

- MIT OCW 6.006 Spring 2020：<https://ocw.mit.edu/courses/6-006-introduction-to-algorithms-spring-2020/>（CC BY-NC-SA 4.0）
- 原始资料：[[raw/MIT6006/README|raw/MIT6006 目录与说明]]
- 下载日期：2026-09-26
