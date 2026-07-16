---
type: concept
title: "零代码自动化流水线"
created: 2026-07-16
updated: 2026-07-16
sources: ["[[src-workbuddy-automation-pipeline]]"]
tags: [自动化, 零代码, workbuddy, 效率]
---

# 零代码自动化流水线

**零代码自动化流水线**指用自然语言描述需求、由 AI 工作台（如 [[WorkBuddy]]）把重复性任务编排成可定时/批量执行的流程，无需编写代码。

## 典型场景（来自实战教程）
1. **每日自动签到领积分**：把签到动作交给 WorkBuddy 定时执行，累积 [[credits-points|积分]]。
2. **批量整理文件**：5 分钟整理 100+ 文件，告别手工归类。
3. **一键生成周报**：从零散信息自动汇总成专业周报。

## 关键能力
- [[natural-language-task-driving|自然语言任务驱动]]：描述即执行。
- 本地文件操作：AI 直接读写电脑文件，把"对话"变成"动作"。
- 定时/批量：从一次性任务升级为可复用的流水线。
- 可扩展：通过 [[mcp|MCP（模型上下文协议）]] 接入外部工具与数据源。

## 相关
- [[workbuddy|WorkBuddy]] —— 执行主体
- [[skills-system|Skills 技能系统]] —— 流水线中的能力单元
- [[credits-points|积分]] —— 自动化签到的激励产出
