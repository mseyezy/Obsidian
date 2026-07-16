---
type: entity
title: "Obsidian"
created: 2026-07-16
updated: 2026-07-16
sources: ["[[src-karpathy-llm-wiki]]"]
tags: [obsidian, 工具, 笔记, 知识库]
---

# Obsidian

**Obsidian** 是一款本地优先的 Markdown 笔记软件，以双向链接（wikilinks）和图谱视图著称。在 [[llm-wiki|LLM Wiki]] 方法中被类比为"IDE"——承载知识库、让 LLM 实时编辑页面、用户边浏览边跟随链接。

## 在本库中的角色
- 作为 Wiki 的存放与浏览界面（graph view 可视化概念/语法/实体关联）。
- 与根目录的 [[agents-md|AGENTS.md / CLAUDE.md]] 配合：AI 按配置维护 `raw/`（只读）与 `wiki/`（AI 拥有）。
- 支持 Web Clipper 把网页剪藏进 `raw/articles/`，成为摄入原料。

## 相关
- [[llm-wiki|LLM Wiki]] —— 推荐的承载方法
- [[agents-md|AGENTS.md / CLAUDE.md]] —— 同仓库的配置
- [[knowledge-compounding|知识复利]] —— Obsidian 链接网络支撑复利
