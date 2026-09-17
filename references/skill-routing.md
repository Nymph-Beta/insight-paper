# 可选辅助 skill 的调用

## 定位与授权

从当前会话的 skill 清单定位。常见根目录是 `$CODEX_HOME/skills`，未设置时为 `~/.codex/skills`；插件 skill 按清单展开路径，不把某台机器的绝对路径写成依赖。使用前读取对应 `SKILL.md`，依阶段加载它要求的参考。

这些是 skills，不是同名 MCP 工具。`paper-search` 执行 CLI；绘图和写作由加载后的操作能力完成。名称找不到时报告具体缺失；关键能力缺失时先完成其他环节，并用下表中的可行替代或保留待处理项，不声称已调用。

本仓库只包含 insight-paper，不附带下列辅助 skills、CLI 或其脚本，也不假定它们都可从公共源安装。优先复用用户已安装的能力；缺少同名 skill 不妨碍按本仓库的参考规范组织研究，实际检索、PDF 阅读、实验和渲染仍需要对应工具。

用户请求整个本工作流时，检索下载、brainstorm、insight、实验设计、叙事和风格制图已在同一授权范围，不因内部技能转换重复询问。用户只请求一环节时，不自动执行其余环节。尊重用户禁用名单；完整同行评审、rebuttal、投稿、外发、全局技能库修改等按实际请求处理。

## 阶段映射

| 能力 | 主用 skill | 具体用途与传入材料 |
|---|---|---|
| 检索、核验、PDF获取 | `paper-search` | 领域词、目标会议、时间窗、已核验清单；以当前CLI参数为准 |
| PDF阅读和图表查看 | 当前可用PDF能力 | 本地PDF、所需页/图；查看真实图像，保留定位 |
| 单篇关键论文深入解读 | `nature-paper-card`，按需 | 仅需深读关键论文时加载其完整规则；无需给每篇强制制作16节卡片 |
| 候选idea具象化 | `ccf-idea-optimizer` | 已读文献矩阵、候选、原idea不变项；选择exploratory/quick模式以适配阶段 |
| 实验细化 | `ccf-experiment-designer` | insight卡和M/P/A/G矩阵；保留动机实验的Method位置 |
| 论文叙事和正文 | `ccf-paper-writer` | 已确认机制、storyline、证据状态、文献定位与目标语言/格式 |
| 可编辑框架及模块图 | `academic-figures-drawer` | 方法语义、已查看参考图、提取后的visual-spec、图型与输出格式 |
| 数据图表和版式 | `ccf-visual-composer` | 真实数据、指标方向、视觉规格、图意和图注事实 |
| 真实数字与主张核对 | `ccf-integrity-auditor`，按需 | 有结果/稿件并需要专门核对时使用；不把早期idea讨论变成整稿审查 |

CCFA技能的已有任务授权条款适用于这条主线。调用时明确本阶段交付，不让其默认全流程、评分报告或默认会议替换用户所选内容。入口只列的可选能力必须在真正使用前读取其完整指导。

## 写作与视觉范例的区别

写作借鉴可在项目内记录论文的段落角色和论证顺序。视觉借鉴必须查看实际页面并提取可用参数，不能从写作卡或摘要猜出配色。

`ccf-paper-to-exemplar` 会涉及全局 exemplar 注册。只有用户要求把参考论文加入持久模板库时才调用这一流程。当前论文仅需参考时，将局部写作观察保存在项目内，不改变已有 skill 的索引或用户默认模板。

不要自动安装/更新所有辅助skills或覆盖它们的文件；本 skill 的可用性不依赖改写其他 skill。

## 辅助 skill 未安装时

| 缺失能力 | 可行的继续方式 |
|---|---|
| `paper-search` | 使用当前浏览/检索工具查官方论文集、OpenReview 和开放全文；按 literature-and-ideas.md 核验、下载和阅读，登记实际使用的工具 |
| `nature-paper-card` | 使用当前 PDF 阅读工具按文献证据矩阵提取正文和图表定位 |
| `ccf-idea-optimizer` | 按 literature-and-ideas.md 的候选字段和 insight-and-motivation.md 的 insight 卡继续 |
| `ccf-experiment-designer` | 按 experiments-and-story.md 完成 M/P/A/G 方案、控制条件和结果状态 |
| `ccf-paper-writer` | 根据 storyline、主张证据表和用户目标直接起草所需章节，保留引用定位和未完成实验状态 |
| `ccf-visual-composer` | 用可用绘图工具从真实数据制作图表，保持 visual-spec、指标方向和图注一致 |
| `academic-figures-drawer` | 先交付实际参考图记录和 visual-spec；如有同等可编辑制图能力，可制作 SVG 或 draw.io 源文件并完成实际渲染检查。它专有的脚本与三轮流程仅在安装并使用该 skill 时适用，不声明执行了不存在的脚本 |
| `ccf-integrity-auditor` | 对照实际结果检查主张、数字和图表；需要更深审查时记录缺口 |

工具本身不可用时只将对应环节记为待完成，继续其他可执行工作；不能把文字方案标成已经下载、运行或渲染。

## 一个可复制的调用

`使用 $insight-paper，研究方向是〔领域/任务〕，目标会议是〔会议或会议族〕。先检索并下载近三年相关主会论文，基于全文形成候选idea，再给出insight卡、以方法动机为重点的实验方案和storyline。视觉风格从这些论文及同领域技术报告提取，框架图使用academic-figures-drawer。已有资料在〔路径〕，本次先做到〔终点〕。`

只有当前确实缺失、且影响后续工作的输入才询问。名称、配色等可从上下文和实际参考中解决的例行选择，不制造新的审批步骤。
