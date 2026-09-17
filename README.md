# insight-paper · 洞见驱动论文指导

把近年顶会文献、研究 idea、核心 insight、动机实验、论文叙事和视觉风格连接起来的 Codex skill。

**An insight-driven research and writing skill for Codex: literature → ideas → insight → motivation experiments → narrative → figures.**

[MIT License](LICENSE) · [技能入口](SKILL.md) · [来源说明](NOTICE.md)

## 工作流

```mermaid
flowchart LR
    A[近 2–3 年顶会检索与全文阅读] --> B[文献驱动 brainstorm]
    B --> C[保留原 idea · 提炼 insight]
    C --> D[动机 / 性能 / 消融 / 故事验证]
    D --> E[证据支撑的论文叙事]
    E --> F[参考论文与技术报告的视觉风格]
    D -->|实验结果更新解释| C
```

核心做法：

- **一个核心洞见统领工作。** 不为凑贡献数量而添加模块。
- **动机实验进入 Method。** 先用分析回答“为什么这样设计”，再引出方法；消融另行回答“已有模块是否有效”。
- **Insight 具有可检验内容。** 将 idea 展开为已有假设、现象、解释、设计原则和预测，保留原机制及相反结果分支。
- **一套文献多次复用。** 同时积累研究依据、写作结构和实际参考图。
- **从实际图示提取风格。** 记录构图、色彩、字体、线条与箭头语义，形成可交付给绘图工具的视觉规格。
- **从已有进度继续。** `project-state.md` 区分已核验、已下载、已读、已运行和已渲染的状态。

## 安装

需要支持本地 skills 的 Codex，以及任务所需的文件读取、网页检索、PDF 阅读或图形处理能力。这个仓库是工作流指令包，不包含模型、论文数据集或训练程序。

将仓库克隆到 Codex 的 skills 目录：

```bash
git clone https://github.com/Nymph-Beta/insight-paper.git \
  "${CODEX_HOME:-$HOME/.codex}/skills/insight-paper"
```

如果目标目录已存在，先检查已有版本；不要覆盖其中的个人修改。也可以下载仓库 ZIP，将包含 `SKILL.md` 的目录命名为 `insight-paper` 后放入 skills 目录。

## 使用

完整流程：

```text
使用 $insight-paper。
我的研究方向是〔领域与任务〕，目标会议是〔会议或会议族〕。
先检索并下载近三年相关主会论文，基于全文形成候选 idea，
再给出 insight 卡、以方法动机为重点的实验方案和论文故事。
图示参考这些论文与同领域技术报告，优先使用 academic-figures-drawer。
已有资料位于〔路径〕，本次先做到〔所需阶段〕。
```

已有 idea：

```text
使用 $insight-paper。保留我的原始方法机制，先把它提炼成 insight，
给出可检验预测、Method 前段的动机实验及过渡段，
再单独设计验证模块有效性的消融。已有材料：……
```

已有实验结果：

```text
使用 $insight-paper，从项目的 project-state.md 继续。
根据这些真实结果更新 insight、主张证据表与论文叙事，
复用已有文献，不重新开始检索。本次只修改 Method 和 Results。
```

默认窗口为执行日之前 36 个月；明确要求两年时使用 24 个月。主会、workshop 和预印本分别登记。

## 可选技能集成

安装 insight-paper **不会同时安装**下列技能或 CLI。它们是可复用的辅助能力，按当前阶段加载；具体实现和许可证由各自项目管理。

| 阶段 | 优先集成 | 没有该技能时 |
|---|---|---|
| 文献检索、核验与获取 | `paper-search` skill 与 CLI | 使用实际可用的检索工具、官方来源和 PDF 阅读能力 |
| idea 细化 | `ccf-idea-optimizer` | 按仓库中的候选表和 insight 卡推进 |
| 实验设计 | `ccf-experiment-designer` | 按 M/P/A/G 分类完成实验方案 |
| 叙事与正文 | `ccf-paper-writer` | 基于已读文献和主张证据表起草 |
| 可编辑方法图 | `academic-figures-drawer` | 交付视觉规格，或使用同等可编辑制图能力 |
| 数据图表 | `ccf-visual-composer` | 使用实际绘图工具和真实数据 |
| 关键论文深读 | `nature-paper-card` | 使用文献证据矩阵 |
| 主张与数字核对 | `ccf-integrity-auditor` | 对照结果与来源逐项核对 |

详细的材料交接、缺失能力处理及范例库边界见 [skill-routing.md](references/skill-routing.md)。本仓库不分发上述辅助技能，也不提供未经核验的安装地址。

## 主要产物

按任务需要逐步创建：

| 产物 | 用途 |
|---|---|
| 文献清单与证据矩阵 | 记录论文身份、全文状态、正文定位和参考图 |
| `ideas.md`、`insight.md` | 保存候选、原机制、核心解释与预测 |
| `experiment-plan.md` | 动机、性能、消融、故事验证的具体方案 |
| `claim-evidence.md`、`storyline.md` | 将主张、实验和正文连接起来 |
| `figures/style-sources.md`、`visual-spec.md` | 实际风格参考与可执行视觉规格 |
| `project-state.md` | 记录完成状态和下一步 |

真实训练、长时计算和数据获取按具体任务的资源与授权执行。没有实验结果时交付方案或带待补标记的稿件；缺少实际参考图时不把自主草图称作风格复刻。

## 仓库结构

```text
insight-paper/
├── SKILL.md
├── agents/openai.yaml
├── references/
│   ├── literature-and-ideas.md
│   ├── insight-and-motivation.md
│   ├── experiments-and-story.md
│   ├── visual-style.md
│   ├── skill-routing.md
│   └── methodology-origin.md
├── README.md
├── CONTRIBUTING.md
├── NOTICE.md
└── LICENSE
```

## 验证范围

原始技能通过了 Codex skill-creator 的结构校验，并经过三个模拟场景的应用检查：资料不足、已有 idea 但未实验，以及已有项目返回不支持原假设的结果。开源版另检查了引用文件、依赖说明和发布文件范围。

这些检查不代表已经完成真实论文检索、训练或绘图的端到端验证。欢迎通过 [Issues](https://github.com/Nymph-Beta/insight-paper/issues) 提供可复现的使用反馈；贡献方式见 [CONTRIBUTING.md](CONTRIBUTING.md)。

## 来源与许可

研究方法论根据《2026年，AI方向硕博何去何从？》相关字幕整理，保留来源时间段和信息对应表；本仓库不分发视频或逐字字幕。来源经验和本项目新增的执行规范在 [NOTICE.md](NOTICE.md) 中区分。

本项目采用 [MIT](LICENSE) 许可证。第三方论文、图像、视频和外部技能不随本仓库重新授权。
