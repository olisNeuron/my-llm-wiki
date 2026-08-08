---
title: Complexity and P vs NP
tags: [algorithms, cs61b, complexity, np]
---

# Complexity and P vs NP（压缩、复杂度类与 P vs NP）

一句话核心：**压缩的极限是柯氏复杂度（多数比特流根本不可压缩）；计算问题的难度最终归结为 P、NP、NP-complete 这些复杂度类**。

## 压缩

- **前缀码（prefix-free codes）**：任何码字都不是另一个的前缀，保证可解码；如摩尔斯码有歧义，前缀码没有。
- **Shannon-Fano / Huffman**：按频率分配码长，高频短码、低频长码；Huffman 用频率树贪心构造。
- **LZW**：动态维护字典，用已有子串替换重复片段（gif 等格式的基础）。
- 压缩理论：**Kolmogorov 复杂度** = 能生成该比特流的最短程序长度；它与语言无关（解释器只是常数开销），并且**不可计算**；绝大多数比特流本质上不可压缩。

## 复杂度类

- **P**：能在多项式时间（O(N^k)）内**解决**的问题。
- **NP**：解可以在多项式时间内**验证**的问题（NP 不直接等于"指数时间"）。
- **NP-complete**：NP 中最难的一类——任何 NP 问题都可以多项式归约到它；若其中一个有多项式算法，则 P = NP。经典成员：最长路径、哈密顿回路、TSP、可满足性问题等。
- **归约（reduction）**：把问题 A 化归为问题 B，说明"B 至少和 A 一样难"，是证明 NP 困难度的核心工具。
- **P = NP?**：未解问题；若成立，所有可验证的问题都可快速求解（对密码学、优化、AI 影响巨大）。

## 关联

- [[Shortest Paths]]：DAG 最长路径可解，一般图最长路径是 NP 难题
- [[Sorting]]：比较排序下界是"难度"思想的雏形
- [[CS61B 教材]]、[[Algorithms 4ed 教材]]：来源

## 来源

[[raw/CS61B/37.-compression-and-complexity|CS61B 第 37 章 Compression and Complexity]]、[[raw/CS61B/38.-compression-complexity-p-np|第 38 章 Compression, Complexity, P = NP]]
