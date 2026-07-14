# CLAUDE.md — English Learning Wiki

> 本仓库是一个基于 Karpathy LLM Wiki 方法的英语学习知识库。
> 你（AI）是这个 Wiki 的**唯一维护者**。每次启动时先读本文件，理解目录结构、页面规范和三大操作。

---

## 1. 仓库结构

```
英语学习/
├── CLAUDE.md            ← 本文件，灵魂配置
├── index.md             ← 全库内容索引（你维护）
├── log.md               ← 操作日志（你每次操作后追加）
├── raw/                 ← 原始资料层（只读，永不修改）
│   ├── articles/        ← 英语文章、新闻、博客
│   ├── videos/          ← 视频字幕、transcript
│   ├── audios/          ← 播客、听力材料、音频脚本
│   ├── texts/           ← 课文、教材、阅读材料
│   ├── dialogues/       ← 对话脚本、口语素材
│   ├── books/           ← 书籍章节
│   └── assets/          ← 图片、音频附件
├── wiki/                ← 知识页层（你完全拥有，读写）
│   ├── vocabulary/      ← 词汇页（一词一页：词义、例句、搭配、近反义词）
│   ├── grammar/         ← 语法点页（一条规则一页）
│   ├── pronunciation/   ← 发音规则、音标、连读/弱读/重音
│   ├── idioms/          ← 习语、俚语、固定表达
│   ├── phrasal-verbs/   ← 动词短语（phrasal verbs）
│   ├── sources/         ← 来源摘要页（每篇 raw 文章对应一页）
│   ├── comparisons/     ← 易混对比（如 affect/effect、in/on/at、say/tell）
│   ├── overviews/       ← 主题概览页（如"时态系统总览"）
│   └── syntheses/       ← 综合页（跨多个来源的知识整合）
└── outputs/
    ├── qa/              ← 用户提问 + 你的高质量回答归档
    └── health/          ← 你生成的健康检查报告
```

**三层职责**：
- `raw/`：唯一事实来源。**绝对不要修改、删除、重命名 raw 里的任何文件**。
- `wiki/`：你的工作区。读 raw → 在 wiki 写页面 → 互相用 `[[双向链接]]` 连起来。
- `outputs/`：运行时产物。问答归档和健康报告存这里。

---

## 2. 页面类型与格式规范

每种页面有固定 YAML frontmatter + 正文结构。**所有页面必须以 `.md` 结尾，文件名用英文小写连字符**（如 `phrasal-verb-look-up.md`，不用中文或空格）。

### 2.1 词汇页 `wiki/vocabulary/`

```markdown
---
type: vocabulary
word: look up
pos: phrasal verb
phonetic: /lʊk ʌp/
cefr: B2
sources: [[src-bbc-learning-english-2024]]
---

# look up

## 释义
1. （在字典/资料中）查阅
2. 拜访（某人）

## 例句
- I need to **look up** this word in the dictionary. （查阅）
- I'll **look up** an old friend when I'm in London. （拜访）

## 搭配
- look up sth in sth（在某资料中查阅某物）
- look sb up（拜访某人）

## 近义/反义
- 近义：[[consult]], [[refer-to]]
- 反义：[[ignore]]

## 词族
- [[lookup]]（名词形式）
- [[look-into]]（易混短语）

## 来源
- [[src-bbc-learning-english-2024]]
```

### 2.2 语法点页 `wiki/grammar/`

```markdown
---
type: grammar
topic: present-perfect
cefr: B1
sources: [[src-grammar-in-use]]
---

# Present Perfect Tense（现在完成时）

## 构成
have/has + 过去分词

## 用法
1. 过去发生，对现在有影响
2. 经验（曾经做过）
3. 持续到现在（+ since/for）

## 易错点
- 与 [[past-simple]] 的区别：见 [[comparison-present-perfect-vs-past-simple]]
- 与 [[present-perfect-continuous]] 的区别

## 例句
- I **have lived** here for 10 years.
- She **has never been** to Japan.

## 来源
- [[src-grammar-in-use]]
```

### 2.3 来源摘要页 `wiki/sources/`

**文件名前缀必须 `src-`**，如 `src-bbc-article-2024-03-15.md`。

```markdown
---
type: source
source_type: article  # article/video/audio/text/dialogue/book
title: "原文标题"
url: https://...
author:
date_read: 2026-07-13
cefr_level: B2
language: en
ingested: true
---

# [来源标题]

## 一句话摘要
本文章讲了……

## 核心要点（3-5 条）
1. ……
2. ……

## 关键词汇（链接到 wiki/vocabulary/）
- [[look-up]] —— 查阅
- [[take-for-granted]] —— 视为理所当然

## 语法点（链接到 wiki/grammar/）
- [[present-perfect]] —— 文中多次出现

## 习语/表达（链接到 wiki/idioms/）
- [[piece-of-cake]]

## 原文链接
- 本地：[[raw/articles/xxx.md]]
- 在线：https://...
```

### 2.4 易混对比页 `wiki/comparisons/`

```markdown
---
type: comparison
items: [affect, effect]
cefr: B2
sources: [[src-grammar-in-use]]
---

# affect vs effect

## affect（动词）
影响。例：The weather affects my mood.

## effect（名词）
影响/效果。例：The effect was immediate.

## 记忆口诀
**RAVEN**: **R**emember **A**ffect = **V**erb, **E**ffect = **N**oun.

## 常见错误
❌ The weather had a bad affect on me.
✅ The weather had a bad effect on me.

## 来源
- [[src-grammar-in-use]]
```

### 2.5 发音页 `wiki/pronunciation/`

```markdown
---
type: pronunciation
topic: linked-sounds
phonetic_focus: /linking/
---

# 连读规则：辅音 + 元音

## 规则
前一个词末尾的辅音与后一个词开头的元音连读。

## 示例
- "an apple" → /ən æpl/ 听起来像 "a napple"
- "pick it up" → /pɪk ɪt ʌp/ 听起来像 "pi ki tup"

## 练习词组
- turn off
- put it on
- look at this

## 来源
- [[src-bbc-pronunciation-2024]]
```

### 2.6 主题概览页 `wiki/overviews/`

```markdown
---
type: overview
topic: tense-system
cefr: B1-C1
---

# 英语时态系统总览

## 时态一览
| 时态 | 用法 | 例子 | 详解 |
|------|------|------|------|
| 一般现在 | 习惯、事实 | I work. | [[present-simple]] |
| 现在完成 | 经验、持续 | I have worked. | [[present-perfect]] |
| …… | …… | …… | …… |

## 时态对比
- [[comparison-present-perfect-vs-past-simple]]
- [[comparison-present-simple-vs-present-continuous]]

## 综合练习来源
- [[src-grammar-in-use]]
```

### 2.7 综合页 `wiki/syntheses/`

跨多个来源整合的主题文章，如"商务英语邮件常用句式"、"雅思写作高分连接词"等。结构自由，但必须有 frontmatter 和 `## 来源` 段。

---

## 3. 三大操作

### 3.1 INGEST — 摄入新资料

**触发**：用户说"ingest"、`raw/` 里有新文件、"消化一下新文章"等。

**流程**：
1. 读取 `.ingest-manifest.json`（vault 根目录，记录每篇 raw 文件的 sha256 指纹）。遍历 `raw/` 各子目录，计算指纹并比对：
   - **不在 manifest 中** → 新文件，完整摄入
   - **在 manifest 中但指纹变了** → 用户手动编辑过该 raw 文件，执行**更新摄入**（更新对应 wiki 页面，不重复建页）
   - **指纹一致** → 已处理且未改，跳过
2. 对每篇新资料/更新资料：
   - 通读全文
   - 在 `wiki/sources/` 创建/更新来源摘要页（文件名 `src-xxx.md`）
   - 提取核心词汇 → `wiki/vocabulary/` 每词一页（如果页面已存在，**追加新例句和来源**，不覆盖）
   - 提取语法点 → `wiki/grammar/` 每点一页
   - 提取习语/动词短语 → `wiki/idioms/` 或 `wiki/phrasal-verbs/`
   - 提取发音要点 → `wiki/pronunciation/`
   - 提取图片 → 按 §3.4 处理文中图片（下载到 raw/assets/ 并嵌入对应 wiki 页）
   - 发现易混对比 → `wiki/comparisons/`
   - 每个新页面都用 `[[双向链接]]` 连到相关已有页面
   - 来源摘要页必须 link 回原始 `raw/` 文件路径
3. 更新 `index.md`：在"已摄入来源"加入新来源，在"概念索引"加入新页面
4. 处理完后将 manifest 更新为当前指纹
5. 追加 `log.md`：日期 + 操作（ingest N 篇）+ 新增页面数

**关键原则**：
- **增量更新**：词汇页已存在则合并新例句，不要重复创建
- **必须 link**：每个新页面至少有 1 个 `[[链接]]` 到其他页面，避免孤儿页
- **CEFR 标注**：尽量标 B1/B2/C1 等级别，方便后续按难度查询

### 3.2 QUERY — 查询与回答

**触发**：用户问任何与英语学习相关的问题。

**流程**：
1. 先读 `wiki/` 相关页面（不是 raw）综合理解
2. 如 wiki 信息不足，再去 `raw/` 查原文
3. 用中文解释 + 英文例句回答
4. 高质量问答归档到 `outputs/qa/YYYY-MM-DD-短标题.md`，并在 `log.md` 记录

**回答规范**：
- 涉及单词/短语时用 `[[wiki 链接]]` 标注，方便用户跳转
- 中文讲解 + 英文例句，例句加粗目标词
- 不确定时明确说"我需要查 raw/"，不要编造

### 3.3 LINT — 健康检查

**触发**：用户说"lint"、"检查一下"、"健康检查"等，或每 ingest 10 篇后建议一次。

**检查项**：
1. **孤儿页**：没有任何入链的页面 → 列出，建议补充链接
2. **断链**：`[[链接]]` 指向不存在的页面 → 列出，建议创建或修正
3. **矛盾**：同一词汇/语法点在不同页面有冲突描述 → 列出对比，请用户裁决
4. **重复页**：同一概念被创建了多个页面 → 建议合并
5. **缺失 frontmatter**：页面没按规定写 YAML → 列出

**输出**：`outputs/health/YYYY-MM-DD-lint-report.md`，列出问题清单 + 修复建议。
**修复必须经用户确认后再执行**（除非是断链这种纯技术问题）。

### 3.4 图片处理 — IMAGE（把远程/本地图片本地化并嵌入）

**目的**：Web Clipper 或手动剪藏的带图文章，图片常是远程 URL（百度图床、WordPress 媒体等），随时可能失效且 Obsidian 加载不稳。本步骤把图片下载到本地 `raw/assets/`，再嵌入对应 wiki 页，做成图文记忆卡。

**触发**：ingest 任意 `raw/` 文章时（尤其含 `![](http...)`、`![[file]]` 或 `<img>` 的文章）。

**流程**：
1. 扫描该文章正文里的所有图片引用：
   - Markdown 远程图：`![](https://...)`
   - Obsidian 附件图：`![[filename.png]]`
   - HTML：`<img src="...">`
2. 按"就近归属"原则把每张图对应到某个 wiki 页面（图正上方/正下方的小节标题即归属页；无法判断则归来源摘要页 `wiki/sources/`）。
3. 对每张**远程**图片（http/https 链接）：
   - 目标路径：`raw/assets/<主题>/<slug>.<ext>`（主题用归属页词名/文章主题，如 `raw/assets/herbs/basil.jpeg`；`<slug>` 用归属页文件名去扩展名；扩展名按实际 MIME 取 jpeg/png/webp）
   - **已存在则跳过**（不重复下载，保证幂等）
   - 不存在则下载（`curl -sL` 等）；失败则保留远程链接并记日志，**不阻塞 ingest**
   - 校验文件非空、是合法图片（尺寸 > 1KB）
4. 对每张**本地**图片（`![[filename]]` 且已在 `raw/assets/`）：直接用 `![[<主题>/<slug>.<ext>]]` 或 `![](raw/assets/...)` 引用。
5. 在归属 wiki 页嵌入本地图片：
   - 词汇/实体页：放在 `# 标题` 下方
   - 概览页：可在文末做"图鉴画廊"（多图列表，每张配 `[[链接]]`）
6. **不修改 raw 文章本身**——只在 wiki 页嵌入；raw 里的原始远程链接原样保留。
7. 在来源摘要页用小节登记图片映射（便于更新摄入时核对）：
   ```markdown
   ## 图片资产
   - basil → ![[herbs/basil.jpeg]]（来源：原文章图1）
   ```

**关键原则**：
- **幂等**：图片已下载则绝不重复下载；远程 URL 失效也不报错中断
- **本地优先**：嵌入用本地路径，不再依赖远程图床
- **归属清晰**：每张图至少链到一个 wiki 页，避免"孤儿图"
- **不污染 raw**：raw 文章正文一字不改，图片是新增资产，不违反"raw 永不修改"

---

## 4. 必须遵守的规则

1. **raw/ 永不修改**：原始资料是唯一事实来源，绝对不动。
2. **文件名规范**：英文小写 + 连字符，如 `present-perfect.md`，不用空格/中文/大写。
3. **链接是灵魂**：每个页面至少 1 个 `[[双向链接]]`，wiki 的价值在网络结构。
4. **frontmatter 必填**：每页必须有 YAML 头，至少含 `type` 和 `sources`。
5. **增量合并**：已存在的页面要追加新例句/新来源，不要覆盖。
6. **每次操作后更新 index.md 和 log.md**：让用户能追踪变化。
7. **维护 `.ingest-manifest.json`**：每次摄入/更新后写入对应 raw 文件的指纹，用于自动检测"用户手动编辑过的文章"并重新摄入。

---

## 5. 给用户的日常使用提示

- **添加新资料**：用 Obsidian Web Clipper 把网页剪藏到 `raw/articles/`；视频字幕/课文手动放对应 `raw/` 子目录
- **触发 ingest**：跟我说 "ingest 一下新加的资料"
- **提问**：直接问，比如 "affect 和 effect 怎么区分"、"过去完成时什么时候用"
- **看图谱**：Obsidian Graph view 可视化词汇/语法/习语之间的关联
- **复习**：可以让我"出 5 道 present perfect 的练习题"等

---

## 6. 版本

- v1.0 — 2026-07-13 初始化，基于 Karpathy LLM Wiki 方法
- v1.1 — 2026-07-14 增加 §3.4 图片处理流程（自动下载 raw 文章图片到 raw/assets 并嵌入 wiki 页）
