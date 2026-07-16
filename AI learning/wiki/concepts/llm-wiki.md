---
type: concept
title: "LLM Wiki"
created: 2026-07-16
updated: 2026-07-16
sources: ["[[src-karpathy-llm-wiki]]"]
tags: [knowledge-management, karpathy, obsidian, 方法论]
---

# LLM Wiki

[[llm-wiki|LLM Wiki]] 是 [[andrej-karpathy|Andrej Karpathy]] 提出的一种"让知识库自我维护"的方法：不再每次提问时临时翻资料，而是由一个常驻的 LLM 持续把原始资料消化成结构化的 Wiki 页面，使知识随每次摄入、每次回答而**复利增长**。

## 核心思想
- **活的 Wiki**：知识库是"代码库"，LLM 是"程序员"，[[Obsidian]] 是"IDE"。
- **三层架构**：Schema 配置层（[[agents-md|AGENTS.md / CLAUDE.md]]）、原始资料层（raw/，只读）、AI 维护层（wiki/，由 LLM 拥有）。
- **三大操作**：Ingest（摄入）、Query（查询）、Lint（健康检查）——详见 [[src-karpathy-llm-wiki|Karpathy 搭建实战]]。

## 解决什么问题
传统 [[RAG]] 是"问完即忘"——每次问答都从零检索，知识不沉淀。LLM Wiki 把回答与资料**归档回 Wiki**，让探索持续复利。

## 相关
- [[knowledge-compounding|知识复利]] —— 为什么"活的"知识库有价值
- [[rag|RAG]] —— 作为对比对象
- [[obsidian|Obsidian]] —— 承载知识库的"IDE"
- [[src-karpathy-llm-wiki|来源文章]]
