---
type: log
title: "操作日志"
created: 2026-07-13
---

# 操作日志

> 追加-only 时间线记录。记录 ingest / query / lint 操作。
> 可用命令查看近期操作：`grep "^## \[" log.md | tail -5`

## [2026-07-13] init | 知识库初始化

按 Karpathy LLM Wiki 方法建立目录结构：
- 创建 `raw/`（articles, papers, podcasts, repos, data, assets）
- 创建 `wiki/`（concepts, entities, sources, comparisons, overviews, syntheses）
- 创建 `outputs/`（qa, health）
- 写入 `CLAUDE.md` 配置规则
- 写入 `index.md` 索引（空）
- 迁移 4 篇剪藏文章从 `Clippings/` 到 `raw/articles/`

待办：ingest `raw/articles/` 中的 4 篇初始资料。

## [2026-07-16] ingest | 4 篇初始资料（WorkBuddy / Karpathy LLM Wiki / 扣子 / 自动化流水线）

按 Karpathy LLM Wiki 方法处理 `raw/articles/` 中全部 4 篇初始资料（均为 manifest 中不存在的新文件，哈希已写入 `.ingest-manifest.json`）：

- **源摘要页（4）**：[[src-workbuddy-guide-2026]]、[[src-workbuddy-automation-pipeline]]、[[src-coze-intro]]、[[src-karpathy-llm-wiki]]
- **图片：0 张**——仅 1 张 `chrome-extension://` 插件图标（无下载价值），按图片处理流程跳过。
- 处理数量 **processed_count = 4**。

> 说明：本次运行前，vault 已存在一次**未提交**的 ingest（自动化 `1783958831946`）产出的 22 个 wiki 页面，覆盖了相同的 4 篇文章。本次运行最终化了摄入元数据，并与既有页面做了去重对齐：
> - 补齐 5 个被既有页面正向链接、但此前缺失的核心概念页：[[agent]]、[[rag]]、[[vibe-coding]]、[[multi-agent-collaboration]]、[[mcp]]；
> - 删除 6 个与既有页面同名/同义的冗余页（`src-workbuddy-zerotohero-2026`、`ai-office-automation`、`concepts/coze`、`concepts/workbuddy`、`rag-vs-llm-wiki`、`ai-agent-tools-overview`）；
> - 重写 `index.md` 登记全部 **27** 个页面并移除"待摄入资料"。
> 最终提交后 wiki 共 27 页，链接图闭合、无孤儿/断链。

> 注：4 篇 raw 中 2 篇为 Web Clipper 仅含 frontmatter 的剪藏残页（内容以 description 为主），1 篇（了解扣子）为正文完整的 Coze 官方文档，1 篇为自动化流水线教程（仅含导航链接 + 1 张插件图标）。
