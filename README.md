# LLM Wiki Lab

English | [中文](./README-CN.md)

> An ever-evolving personal knowledge system. Managed with Obsidian: `raw/` holds source material, `wiki/` holds distilled knowledge notes, and `AGENTS.md` defines how the knowledge base is maintained.

## Layout

```
llm-wiki-lab/
├── raw/       # Source material (books, lecture slides, notes)
├── wiki/      # Distilled knowledge notes (Obsidian wikilinks)
├── AGENTS.md  # Workflow rules: ingest principles & query principles
└── README.md
```

## raw/ — Source material

| Directory | Contents | Format |
| --- | --- | --- |
| `raw/CSAPP/` | Chinese reading notes for Computer Systems: A Programmer's Perspective (12 chapters) | Markdown, named 01–12 per chapter |
| `raw/CS61B/` | Full text of the official UC Berkeley CS61B textbook, Spring 2026 | 209 Markdown pages |
| `raw/Algorithms4ed/` | Official English lecture slides for Algorithms, 4th ed. (Sedgewick & Wayne) | 24 PDFs |

Each subdirectory has its own `README.md` with source, download date, and file layout.

## wiki/ — Knowledge notes

Organized by topic, with pages cross-linked using Obsidian wikilinks:

- **Data Structures**: linked lists/dynamic arrays, trees & balanced trees, tries, heaps, hash tables, disjoint sets, graphs & traversals
- **Algorithms**: asymptotic analysis, sorting, shortest paths, minimum spanning trees, complexity & P vs NP
- **Computer Architecture**: CSAPP core ideas, data representation, stack frames, cache locality
- **Operating Systems**: virtual memory, linking & loading
- **Programming Languages**, **AI Systems**: reserved categories

## Usage

1. Open this repository as a vault in Obsidian.
2. When looking something up, **read `wiki/` first**; fall back to `raw/` when you need details.
3. When new material enters `raw/`, follow the ingest workflow in `AGENTS.md`: create a source page → distill key points → update related wiki pages → add cross-links → create new pages if none exist.

## Notes

- All source material comes from public channels (official book sites, open-source note repos); see each `raw/` subdirectory README for attribution and licensing.
- Wiki pages are distilled study notes, not verbatim book text.

## Maintenance

- Detailed rules live in [AGENTS.md](AGENTS.md).
- Commit changes and push to GitHub after editing.
