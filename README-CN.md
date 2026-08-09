# LLM Wiki Lab

[English](./README.md) | 中文

> 一个可持续进化的个人知识系统。用 Obsidian 管理：`raw/` 存放原始资料，`wiki/` 存放提炼后的知识页，`AGENTS.md` 定义知识库的维护规则。

## 目录结构

```
llm-wiki-lab/
├── raw/       # 原始资料（书籍全文、讲义、笔记原文）
├── wiki/      # 整理后的知识页（Obsidian 双链）
├── AGENTS.md  # 工作规则：ingest 原则与查询原则
└── README.md
```

## raw/ — 原始资料

| 目录 | 内容 | 格式 |
| --- | --- | --- |
| `raw/CSAPP/` | 《深入理解计算机系统》（CSAPP）12 章中文读书笔记 | Markdown，按章节 01–12 命名 |
| `raw/CS61B/` | UC Berkeley CS61B 官方教材 Spring 2026 英文全文 | 209 页 Markdown |
| `raw/Algorithms4ed/` | 《算法（第 4 版）》（Sedgewick & Wayne）官方英文讲义 | 24 个 PDF |
| `raw/zhihu-favorites/` | 知乎收藏快照（2 个收藏夹、140 条去重文章，含摘要与链接） | Markdown |

各目录内的 `README.md` 记录来源、下载日期与文件结构。

## wiki/ — 知识页

按主题分类，页与页之间用 Obsidian 双链连接：

- **Data Structures**：链表/动态数组、树与平衡树、Trie、堆、哈希表、并查集、图与遍历
- **Algorithms**：渐近分析、排序、最短路、最小生成树、复杂度与 P vs NP
- **Computer Architecture**：CSAPP 核心思想、数据表示、栈帧、缓存局部性
- **Operating Systems**：虚拟存储器、链接与加载
- **CS Learning**：自学路线与公开课、学习方法与编程实践
- **AI Industry**：AI 时代的编程学习与就业、大模型竞争格局
- **People**：梁文锋与 DeepSeek、周信静、科学家与行业人物
- **Education**：教育体系与内卷、成长心态
- **Culture**：摇滚与电影、随笔与社会观察
- **Programming Languages**：预留分类

## 使用方式

1. 用 Obsidian 打开本仓库，即是一个 Vault。
2. 查询时**优先阅读 `wiki/` 中的知识页**，需要细节时再回溯 `raw/` 中的原始资料。
3. 新资料进入 `raw/` 后，按 `AGENTS.md` 的 ingest 流程整理：生成来源页 → 提炼关键观点 → 更新相关 wiki 页面 → 增加交叉链接 → 没有对应页面时新建页面。

## 内容说明

- 原始资料均来自公开渠道（教材官方站点、开源笔记仓库），具体来源与版权说明见各 `raw/` 子目录的 README。
- 知识页为学习笔记式提炼，非原书全文转载。

## 维护

- 详细规则见 [AGENTS.md](AGENTS.md)。
- 修改后用 git 提交并推送到 GitHub 即可。
