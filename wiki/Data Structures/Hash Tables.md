---
title: Hash Tables
tags: [data-structures, cs61b, hashing]
---

# Hash Tables（哈希表）

一句话核心：**把键映射成数组下标（哈希），冲突用链/探测解决，负载过高时扩容——摊还后插入、删除、查找都是 O(1)**。

## 思路

- 数组按下标访问是 O(1)，把数据"变成"下标就是哈希：`hashCode() % 数组长度`（取余实现 wrapping）。
- **valid** hashCode：相等的对象必须有相同的 hashCode（否则 equals 与查找矛盾）。
- **good** hashCode：分布均匀、计算快（理想 O(1)），避免一堆键挤进同一桶。

## 冲突与扩容

- **外部链（separate chaining）**：每个桶放一个链表，冲突的键挂进去。
- **线性探测（linear probing）**：冲突时往后找空位（开放寻址）。
- **负载因子（load factor）= 元素数 / 桶数**：超过上限（Java 默认 0.75）就把数组翻倍并**重新放置所有元素**（rehash）。

## 性能

- 均匀分布 + 扩容：`contains`/`add` 摊还 Θ(1)；
- 不扩容 + 哈希很差：全部进同一桶，退化为 Θ(N)；
- 教训：哈希质量直接决定"常数时间"是否成立。

## equals 与 hashCode 的配合

- 覆写 `equals` 必须同时覆写 `hashCode`，否则 HashSet/HashMap 找不到元素；
- 用**可变对象**做键有风险：键的 hashCode 变了就再也找不到它。

## 关联

- [[Tries]]：字符串键的确定性替代方案
- [[Disjoint Sets (Union-Find)]]：数组索引思想的另一应用
- [[CS61B 教材]]：来源与章节地图

## 来源

[[raw/CS61B/24.-hashing-i|第 24 章 Hashing I]]、[[raw/CS61B/25.-hashing-ii|第 25 章 Hashing II]]
