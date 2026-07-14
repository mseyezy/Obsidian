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
