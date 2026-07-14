# Personal Wiki Rules

> 本文件是整个知识库的"灵魂"——AI 每次启动都会先读它。
> 基于 Andrej Karpathy 的 LLM Wiki 方法：https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f
> 与你的 AI agent 共同迭代此文件，随着对领域理解的深入逐步完善。

## Overview

This is a personal knowledge base maintained by you (the LLM).
You are the maintainer of the `wiki/` directory. The `raw/` directory
is the immutable source of truth — read it, never modify it.

核心模式：**不要每次提问时才临时翻资料，而是持续维护一个"活的"Wiki。**
每摄入一篇新资料、每回答一个新问题，wiki 都变得更丰富——知识复利增长。

## Directory structure

```
AI learning/
├── CLAUDE.md              ← 你正在读的文件（Schema 配置层）
├── raw/                   ← 原始资料层（不可变，AI 只读）
│   ├── articles/          # 网页文章（Obsidian Web Clipper 保存到此）
│   ├── papers/            # 论文
│   ├── podcasts/          # 播客转录
│   ├── repos/             # 代码仓库说明
│   ├── data/              # 数据文件
│   └── assets/            # 图片等附件
├── wiki/                  ← 知识页层（LLM 完全拥有，读写）
│   ├── concepts/          # 概念页（一个概念一个文件）
│   ├── entities/          # 实体页（人物、组织、产品等）
│   ├── sources/           # 逐篇摘要页
│   ├── comparisons/       # 对比页
│   ├── overviews/         # 概览页
│   └── syntheses/         # 综合分析页
├── outputs/               ← 运行时输出
│   ├── qa/                # 问答沉淀
│   └── health/            # 健康检查报告
├── index.md               # 内容索引（你维护）
└── log.md                 # 操作日志（追加-only）
```

### 各层职责

| 层 | 内容 | 谁来动 |
|----|------|--------|
| `raw/` | 原始文章、论文、播客 | **只读，永不修改**——唯一事实来源 |
| `wiki/` | 摘要页、概念页、实体页、交叉链接 | **LLM 完全拥有**，读写 |
| `CLAUDE.md` | 目录结构、页面格式、工作流程 | 人与 AI 共同迭代 |

## Page format

Every wiki page MUST have a YAML frontmatter:

```yaml
---
type: concept | entity | source | comparison | overview | synthesis
title: "Page Title"
created: 2026-07-13
updated: 2026-07-13
sources: ["[[source-page-1]]", "[[source-page-2]]"]
tags: [tag1, tag2]
---
```

### 页面类型说明

- **concept**：一个概念的详解页（如 `[[LLM Wiki]]`、`[[RAG]]`）
- **entity**：人物/组织/产品页（如 `[[Andrej Karpathy]]`、`[[Anthropic]]`）
- **source**：一篇原始资料的摘要页（对应 `raw/` 里的一个文件）
- **comparison**：多源对比页（如 `[[传统RAG vs LLM Wiki]]`）
- **overview**：某主题的概览页（如 `[[知识管理方法论]]`）
- **synthesis**：跨多源的综合分析页

## Three core operations

### 1. Ingest（摄入）

触发语：`ingest [文件名]` 或 `raw/ 里有新文件，ingest 它们`

执行流程：
1. 读取 `.ingest-manifest.json`（vault 根目录，记录每篇 raw 文件的 sha256 指纹）。遍历 `raw/` 下文件，计算指纹并比对：
   - **不在 manifest 中** → 新文件，完整摄入
   - **在 manifest 中但指纹变了** → 用户手动编辑过该 raw 文件，执行**更新摄入**（更新对应 wiki 页面，不重复建页）
   - **指纹一致** → 已处理且未改，跳过
2. 与我简述关键发现
3. 在 `wiki/sources/` 创建摘要页（含 frontmatter）
4. 更新相关的 `wiki/concepts/` 和 `wiki/entities/` 页面
   - 不存在则新建
   - 已存在则更新（在 `## Updates` 小节追加变更）
5. 在相关页面之间添加 `[[wikilinks]]` 双向链接
6. 更新 `index.md` 登记新页面
7. 处理完后将 manifest 更新为当前指纹
8. 在 `log.md` 追加条目，格式：`## [YYYY-MM-DD] ingest | 源标题`

> 一篇源文件可能涉及 10-15 个 wiki 页面，这是正常的。
> 推荐逐个摄入，保持参与——读摘要、检查更新、引导 AI 强调什么。

#### 🖼️ 图片处理（Image handling）
摄入含图片的源文件时，按以下流程把图片本地化并嵌入对应 wiki 页：
1. 扫描源文件里的图片引用（`![](url)` / `![[file]]` / `<img src>`）
2. 按"就近归属"原则把每张图对应到某 `concept` / `entity` / `source` 页（图正上方/下方的小节标题即归属页；无法判断则归 source 页）
3. 远程图片（http/https）下载到 `raw/assets/<主题>/<slug>.<ext>`，**已存在则跳过（幂等）**，下载失败则保留远程链接、记日志、不阻塞摄入
4. 在归属 wiki 页嵌入本地图片：`![[<主题>/<slug>.<ext>]]`（放标题下方，或概览页做图鉴画廊）
5. **不修改 raw 源文件**——图片是新增资产，只在 wiki 页嵌入；raw 里的远程链接原样保留
6. 在 source 摘要页用 `## 图片资产` 小节登记映射，便于更新摄入时核对

### 2. Query（查询）

触发语：自然语言提问即可

执行流程：
1. 先读 `index.md` 找到相关页面
2. 阅读那些 wiki 页面
3. 综合答案，带 `[[引用]]` 指向来源页面
4. 若答案有价值，存到 `outputs/qa/` 并在 wiki 中建立链接
5. 在 `log.md` 追加：`## [YYYY-MM-DD] query | 问题摘要`

> **好的答案应作为新页面归档回 wiki。** 你要求的对比、分析、发现的连接
> ——这些都有价值，不应消失在聊天历史中。这样探索就在知识库中持续复利。

### 3. Lint（健康检查）

触发语：`lint` 或 `检查 wiki 健康状况`

执行流程：
1. 扫描所有 `wiki/` 页面，检查：
   - ❌ 页面之间的矛盾
   - ⚠️ 被新源取代的过时声明
   - 🔗 没有入站链接的孤立页面（orphan pages）
   - 📄 被频繁提及但缺乏独立页面的重要概念
   - 🔗 缺失的交叉引用
   - 📊 可通过网络搜索填补的数据空白
2. 将报告写入 `outputs/health/YYYY-MM-DD-lint.md`
3. 经我确认后修复问题
4. 在 `log.md` 追加：`## [YYYY-MM-DD] lint | 摘要`

> 建议每周执行一次。LLM 擅长建议新的待调查问题和新待寻找的源。

## Rules（必须遵守）

1. **永不修改** `raw/` 中的任何文件
2. **必须使用** `[[wikilinks]]` 建立内部引用
3. **每次新建/删除页面**都更新 `index.md`
4. **每次操作后**都追加 `log.md`（ingest / query / lint）
5. 更新已有页面时，在 `## Updates` 小节保留变更历史
6. 新信息与旧信息矛盾时，用 ⚠️ 显式标记，并引用两个来源
7. `log.md` 是追加-only，永不覆盖或删除历史条目
8. 维护 `.ingest-manifest.json`：每次摄入/更新后写入对应 raw 文件的指纹，用于自动检测"用户手动编辑过的文章"并重新摄入

## 工作流比喻

> Obsidian 是 IDE，LLM 是程序员，wiki 是代码库。
> 一边开着 LLM agent，一边开着 Obsidian——LLM 根据对话编辑，
> 我在 Obsidian 实时浏览结果（跟随链接、检查图谱、阅读更新页面）。

## 演进说明

此文档有意保持抽象，描述的是模式而非具体实现。目录结构、schema 约定、
页面格式——所有这些都取决于你的领域、偏好和 LLM 选择。一切都是可选和
模块化的——取其有用，弃其无用。随着使用深入，与你的 LLM agent 共同迭代此文件。
