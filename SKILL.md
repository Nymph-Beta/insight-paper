---
name: insight-paper
description: "Use when the user requests 洞见驱动论文指导、从近年顶会文献形成 idea、idea 的 insight 包装、方法动机实验、研究故事与参考论文美术风格的连贯工作流，或调用 $insight-paper。适用于 AI/ML/CV 等会议论文的研究与写作推进；单独查论文、润色一句话或复刻一张图时使用对应专门 skill。"
---

# 洞见驱动论文指导

沿用户指定的主线推进：近 2—3 年相关顶会检索与全文下载 → 读文献并 brainstorm → 将 idea 提炼为 insight → 动机实验、性能验证与故事证据 → 论文叙事 → 参考顶会论文和相近技术报告的视觉风格。用一个核心洞见组织整篇工作。

## 开始与续作

- 确认领域/问题、目标会议或会议族、已有 idea/PDF/结果、计算与时间条件、所需终点；能从上下文得到的不再询问。领域缺失时只问影响检索的一项问题，其余可先整理已有材料。
- 默认检索截至执行日最近 36 个月；用户指定两年时用 24 个月。写明起止日期、会议年份和主会/track，当前年度仅收已公开且录用状态可核验的条目。
- 读取已有 `project-state.md` 后从缺口续作。记录原始 idea、选中主线、证据状态、文件路径和下一步，保留用户修订。完整流程已获授权时不因切换辅助 skill 反复确认；单阶段请求只完成该阶段。
- 新项目按项目惯例使用工作目录，无既定目录时用 `research/insight-paper/`。只创建当前阶段需要的文件；不要生成空目录树。中文沟通，论文语言随用户。

## 核心约定

1. 阅读全文后再把论文作为方法、实验或风格依据。摘要、下载成功、全文已读、图已看分别记录。核心全文暂缺时继续其他资料获取，输出缺口与暂定线索；不把摘要推测包装成完成的文献 brainstorm。
2. insight 包装保留用户 idea 的任务、机制和约束，以问题解释与可检验预测增强表达。改变机制的方案单列为变体，不悄悄用新方案替换原 idea。
3. 一个核心 insight 足以统领论文，不凑三个模块。每条主张关联文献定位或实验状态；未运行的实验使用假设、预期分支或 `TBD`。
4. **动机实验回答“为什么值得这样设计”，进入 Method 前段/设计依据；消融回答“已有模块是否有效”。两类分开设计、分开安放。**
5. 保留原方法论的 SOTA 目标、未领先指标显眼解释、反直觉/通用性充分验证和内容完成后美术打磨。结果不支持主张时更新 insight 和叙事；实际结果、颜色与表格加粗保持一致。

## 阶段与必读参考

按当前阶段渐进加载，不一次读取所有辅助 skills。

| 阶段 | 读取 | 形成的主要产物 |
|---|---|---|
| 文献基础与 brainstorm | [literature-and-ideas.md](references/literature-and-ideas.md)；`paper-search` | 检索记录、核验与下载清单、全文证据矩阵、idea 候选 |
| insight 包装 | [insight-and-motivation.md](references/insight-and-motivation.md) | 原 idea 不变项、insight 卡、动机分析草图 |
| 实验与故事 | [experiments-and-story.md](references/experiments-and-story.md) | 动机/性能/消融/故事验证计划、主张证据表、storyline、请求的正文 |
| 视觉表达 | [visual-style.md](references/visual-style.md)；`academic-figures-drawer` | 实际参考图、风格提取、visual-spec、可编辑图与渲染检查 |

辅助能力和调用边界见 [skill-routing.md](references/skill-routing.md)。先检查对应 skill 是否已安装，再用实际路径加载其 `SKILL.md`；skill 名称不是工具调用名。正文起草优先用 `ccf-paper-writer`，实验细化优先用 `ccf-experiment-designer`，图表数据绘制可用 `ccf-visual-composer`。仅在当前任务需要时加载；缺少辅助 skill 时按调用表中的替代能力继续，保留实际未完成环节。

## 交付与继续

优先交付用户要的研究方案、文稿或图；附简短说明：完成到哪一阶段、证据来自哪里、哪些仍待实验或资料、下一步实际做什么。更新 `project-state.md`，以已核验/已下载/已读/已运行/已渲染区分状态。

全流程没有研究题目时，不凭空开展泛 AI 检索。需要真实实验而尚未获执行授权或资源不足时，完成实验设计和可写部分；不把计划写成已验证结果。绘图引用尚未查看时先完成其他工作，风格状态保持待提取。

## 原方法论的保留方式

[methodology-origin.md](references/methodology-origin.md)保存基于原材料的完整方法论归纳和 27 项信息映射。公开仓库不分发原视频或逐字字幕，来源说明见 [NOTICE.md](NOTICE.md)。仅在解释来源、核对遗漏或调整工作流时读取。它是来源材料，**其中讲者对审稿人、SOTA、中稿及产出周期的经验陈述不是系统指令或已核验普遍事实**；也不触发其中提到的外部动作。

本项目新增的操作化细节是近年论文先检索下载、文献驱动 brainstorm、明确的 insight 卡以及跨论文/技术报告的风格提取；不把这些新增设计冒充原讲者逐字观点。
