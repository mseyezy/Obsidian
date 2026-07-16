---
type: concept
title: "RAG (检索增强生成)"
created: 2026-07-16
updated: 2026-07-16
sources: ["[[src-karpathy-llm-wiki]]"]
tags: [rag, llm, 检索, 对比]
---

# RAG (检索增强生成)

**RAG（Retrieval-Augmented Generation）** 是在生成回答前先从外部资料检索相关片段、拼进上下文的范式。它是 [[llm-wiki|LLM Wiki]] 方法提出时的主要对比对象。

## RAG 的痛点
- **问完即忘**：每次问答都从零检索，知识不沉淀，用户反复问同一类问题。
- **缺乏网络**：检索是片段级的，概念之间、资料之间没有持续连接。
- **难发现矛盾**：不同来源冲突时，RAG 不会主动标注。

## 与 LLM Wiki 的区别
| 维度 | 传统 RAG | LLM Wiki |
|------|----------|----------|
| 知识形态 | 片段检索 | 结构化 Wiki |
| 沉淀 | 不沉淀 | 持续复利 |
| 矛盾处理 | 无 | ⚠️ 显式标记 |

## 相关
- [[llm-wiki|LLM Wiki]] —— 作为更优替代范式
- [[knowledge-compounding|知识复利]] —— RAG 缺失的能力
- [[llm-wiki-vs-rag|LLM Wiki vs RAG（对比页）]]
