---
type: comparison
title: "LLM Wiki vs 传统 RAG"
created: 2026-07-16
updated: 2026-07-16
sources: ["[[src-karpathy-llm-wiki]]"]
tags: [对比, llm-wiki, rag]
---

# LLM Wiki vs 传统 RAG

| 维度 | 传统 RAG | LLM Wiki |
|------|----------|----------|
| 知识形态 | 片段检索（问完即忘） | 结构化 Wiki（持续沉淀） |
| 沉淀 | 不沉淀，反复从零 | [[knowledge-compounding|知识复利]] |
| 链接 | 片段级，无网络 | 全库 wikilinks 双向链接 |
| 矛盾处理 | 无 | ⚠️ 显式标记 |
| 维护者 | 无（每次临时检索） | 常驻 LLM 维护 wiki/ |
| 事实来源 | 向量库 | raw/ 只读，单一来源 |

## 结论
RAG 擅长"即时检索回答"，LLM Wiki 擅长"长期积累与连接"。二者并非互斥：可用 RAG 做检索入口，用 Wiki 做沉淀层。详见 [[rag|RAG]] 与 [[llm-wiki|LLM Wiki]]。
