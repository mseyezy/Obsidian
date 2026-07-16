---
type: concept
title: "知识复利 (Knowledge Compounding)"
created: 2026-07-16
updated: 2026-07-16
sources: ["[[src-karpathy-llm-wiki]]"]
tags: [knowledge-management, 复利, 方法论]
---

# 知识复利 (Knowledge Compounding)

**知识复利**是 [[llm-wiki|LLM Wiki]] 方法的核心价值主张：每摄入一篇新资料、每回答一个新问题，Wiki 都变得更丰富；后续的摄入与查询建立在前面积累之上，形成"越用越懂你"的复利效应。

## 为什么重要
- 传统笔记/[[RAG]] 是线性、割裂的，知识不互相连接。
- 结构化 + 双向链接的 Wiki 让概念、实体、来源彼此成网，新信息能立刻挂接到已有网络。
- AI 自动完成"记账"（摘要、实体标注、矛盾发现），降低维护成本。

## 实现要点
- raw/ 作为单一事实来源，永不修改（保证可复核）。
- wiki/ 完全由 AI 维护，页面间用 wikilinks 双向连接。
- 矛盾信息用 ⚠️ 显式标记，而不是覆盖。

## 相关
- [[llm-wiki|LLM Wiki]] —— 承载复利的机制
- [[rag|RAG]] —— 缺乏复利的对立面
- [[ai-knowledge-management-overview|知识管理方法总览]]
