# 📝 操作日志

> AI 每次操作后在此追加一行。格式：`- YYYY-MM-DD HH:MM | 操作类型 | 详情`

---

- 2026-07-13 23:19 | **初始化** | 基于 Karpathy LLM Wiki 方法搭建英语学习知识库结构。建立三层目录（raw/wiki/outputs），写入 CLAUDE.md（v1.0，英语学习定制版）、index.md、log.md。raw/ 含 7 个子类（articles/videos/audios/texts/dialogues/books/assets），wiki/ 含 9 个子类（vocabulary/grammar/pronunciation/idioms/phrasal-verbs/sources/comparisons/overviews/syntheses）。保留原有 `欢迎.md`。

- 2026-07-13 23:31 | **INGEST** | 摄入 raw/articles/ 下 2 篇文章：①中英文菜单词汇一（饮食英语词汇，日料菜单对照）②如何用英语点餐？100+种表达（贝立兹）。新建 32 个 wiki 页面：2 来源页 + 20 词汇页（通用场景 12 + 日料专有 8）+ 2 语法页 + 3 习语页 + 4 对比页 + 1 发音页。所有页面双向链接到位，无孤儿页/断链。更新 index.md 与 log.md。

- 2026-07-14 00:26 | **INGEST（手动触发）** | 摄入 raw/articles/ 下 3 篇新文章：①美剧常见口语（用户手动新建，验证手工建文也能被 ingest）②12组英语饮食类单词归类 ③学西餐必备的香草知识。新建 24 个 wiki 页面：3 来源页 + 9 词汇页（al-dente/medium-rare/pinch/basil/oregano/thyme/mint/rosemary/parsley）+ 8 习语页（give-a-shot/tons-of/hit-a-rough-patch/get-the-best-of-me/punch-out/duck/couch-potato/carrot-and-stick）+ 3 对比页（impression-of-vs-on/trim-vs-cut/herb-vs-spice）+ 2 概览页（food-vocabulary-groups/western-herbs）。更新 .ingest-manifest.json（现 5 篇全部登记）、index.md 与 log.md。

- 2026-07-14 00:54 | **INGEST（手动触发·单篇）** | 仅摄入用户更新的 1 篇：各国菜系中英文对照菜单词汇大全（1600+ 行，日/中/西三大菜系约 600 条对照）。**策略**：因体量巨大，不逐词建页（否则 500+ 低价值页稀释图谱），改为结构化消化——1 来源页 + 3 菜系总览页（japanese/chinese/western-cuisine-vocab，按原文分类完整收表）+ 1 跨菜系烹饪手法页（cooking-methods：蒸/煮/炸/炒/烤/煎/焗/炖/熏）+ 1 顶层索引（cuisine-vocabulary）。新建 6 个 wiki 页面，文中 [[sashimi]]/[[sushi]]/[[tempura]]/[[udon]]/[[soba]]/[[miso-soup]]/[[teriyaki]]/[[teppanyaki]] 等已存在页均做了双向链接。无图片。更新 .ingest-manifest.json（现 6 篇全登记）、index.md 与 log.md。

- 2026-07-14 00:30 | **LINT/FIX** | 链接自检发现 4 处断链并修复：①补建 pasta/beef/salt 三个词汇页（与 12组饮食文章呼应）；②修正 src-how-to-order-food-berlitz.md 中 raw 链接多余的"｜贝立兹"后缀（首次 ingest 遗留）。复验全库无断链。更新 index.md（词汇页 29→32）并二次提交。

- 2026-07-14 00:45 | **MEDIA MAP** | 为「学西餐香草」文章整理图文对应关系。从 raw 文章提取 13 个百度图床 URL 全部下载到 raw/assets/herbs/（本地永久保存，0 失败）。将 13 张图嵌入对应 wiki 页：12 张香草页（basil/oregano/bayleaf/curly-parsley/thyme/mint/parsley/dill/rosemary/lemongrass/fennel/chives）+ 1 张 herb-vs-spice 总图。新建 6 个缺失香草页（bayleaf/curly-parsley/dill/lemongrass/fennel/chives），在 western-herbs 总览页新增「外观图鉴」12 图画廊，补全 6 个旧页互通链接，index.md 词汇页 32→38。raw 原文保持只读未改。
