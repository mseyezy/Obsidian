---
type: concept
title: "AGENTS.md / CLAUDE.md (Schema 配置层)"
created: 2026-07-16
updated: 2026-07-16
sources: ["[[src-karpathy-llm-wiki]]"]
tags: [schema, config, agent, 配置]
---

# AGENTS.md / CLAUDE.md (Schema 配置层)

在 [[llm-wiki|LLM Wiki]] 的三层架构中，**配置层**是一个放在仓库根的 Markdown 文件（常叫 `AGENTS.md` 或 `CLAUDE.md`），它定义目录结构、页面格式与三大操作流程——相当于给常驻 LLM 的"使用说明书"与 Schema。

## 职责
- 声明 `raw/`（只读事实来源）与 `wiki/`（AI 维护层）的权限边界。
- 规定每种页面的 YAML frontmatter 与正文结构。
- 固化 Ingest / Query / Lint 的操作步骤，使行为可复现、可迭代。

## 设计原则
- **与人共同迭代**：随对领域理解的深入逐步完善。
- **保持抽象**：描述模式而非具体实现，模块可选。
- **指纹追踪**：用 `.ingest-manifest.json` 记录每篇 raw 的 sha256，自动检测"用户手动改过的文章"以触发更新摄入。

## 相关
- [[llm-wiki|LLM Wiki]] —— 它所处的架构
- [[obsidian|Obsidian]] —— 同一仓库内的知识库
- [[src-karpathy-llm-wiki|来源文章]]
