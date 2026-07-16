---
type: source
title: "Karpathy 的 LLM Wiki 搭建实战：三层架构 + 三大操作"
url: https://cloud.tencent.com/developer/article/2703127
author: 腾讯云开发者社区
date_read: 2026-07-16
sources: []
tags: [llm-wiki, karpathy, obsidian, 知识管理, rag]
---

# Karpathy 的 LLM Wiki 搭建实战：三层架构 + 三大操作

> 原始文件：[[raw/articles/Karpathy 的 LLM Wiki 搭建实战：三层架构 + 三大操作，Obsidian + AGENTS.md 让知识库自我维护-腾讯云开发者社区-腾讯云]]
> 在线链接：https://cloud.tencent.com/developer/article/2703127

## 一句话摘要
详解 [[andrej-karpathy|Andrej Karpathy]] 提出的 [[llm-wiki|LLM Wiki]] 知识管理新范式：用 [[Obsidian]] + AI 构建"可累积"的知识库，通过 Schema 配置层、原始资料层、AI 维护层的权限分离实现 [[knowledge-compounding|知识复利]]，解决传统 [[RAG]] "问完即忘"的痛点。

## 核心要点
1. **三层架构**：Schema 配置层（CLAUDE.md / AGENTS.md）、原始资料层（raw/，只读）、AI 维护层（wiki/，由 LLM 拥有）。
2. **三大操作**：Ingest（摄入）、Query（查询）、Lint（健康检查）。
3. **AI 记账**：自动完成摘要提取、实体标注、矛盾发现等"记账"工作，让知识持续复利。
4. **权限分离**：raw/ 永不修改，wiki/ 完全由 AI 维护，保证事实来源单一。

## 关键概念
- [[llm-wiki|LLM Wiki]] —— Karpathy 提出的知识库自我维护方法
- [[agents-md|AGENTS.md / CLAUDE.md]] —— 配置层（Schema）
- [[obsidian|Obsidian]] —— 作为"IDE"承载知识库
- [[knowledge-compounding|知识复利]] —— 每摄入一篇、每回答一问，wiki 都更丰富
- [[rag|RAG]] —— 对比对象：传统 RAG 问完即忘

## 原文链接
- 本地：[[raw/articles/Karpathy 的 LLM Wiki 搭建实战：三层架构 + 三大操作，Obsidian + AGENTS.md 让知识库自我维护-腾讯云开发者社区-腾讯云]]
- 在线：https://cloud.tencent.com/developer/article/2703127
