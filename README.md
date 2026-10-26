# idea-to-system-blueprint · 构想转系统蓝图与分阶段实施计划

> 遵循 **Open Agent Skills 规范** 的架构设计智能体技能。将模糊的业务想法、产品构想或重构诉求，系统化转化为**工业级系统架构蓝图**与**带明确验收标准（DoD）的分阶段实施计划**。

[![Open Agent Skills](https://img.shields.io/badge/Spec-Open%20Agent%20Skills-blue.svg)](https://skills.sh)
[![Multi-Agent Compatible](https://img.shields.io/badge/Agent-Claude%20%7C%20Cursor%20%7C%20ZCode%20%7C%20WorkBuddy%20%7C%20Antigravity-success.svg)](https://github.com/deepsea404error-create/idea-to-system-blueprint)
[![Gated Protocol](https://img.shields.io/badge/Gating-Mandatory%20Confirmation-purple.svg)](./SKILL.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-lightgrey.svg)](./LICENSE)

---

## 🎯 它解决什么问题

当开发者或产品团队产生一个项目 Idea 时，最容易出现以下工程失控现象：

1. **想法粗放，过早写代码**：在核心实体、数据流向和状态跃迁未厘清前盲目手搓，导致业务逻辑反复打架、代码频繁重构推倒；
2. **缺乏边界剪裁，一期范围膨胀**：未定义明确的 MVP 剪裁红线，把所有远期诉求全部塞入首期，最终导致项目烂尾；
3. **任务颗粒度模糊，协作与 AI 无法闭环**：任务卡写得像日记，缺乏精确的完成定义（DoD）与自检清单，后续无论是人类开发还是交给下游 AI 生成代码，均无法精准验收；
4. **技术亮点发掘不足**：系统做完了，在面试、评审或述职中却讲不出架构深度，无法有力防守技术选型与性能权衡。

`idea-to-system-blueprint` 通过**五步漏斗推演法**与**刚性方案把关门禁**，在落笔写代码前建立唯一且坚实的技术事实源。

---

## 🏗️ 核心交付资产

所有产出物均严格保存在目标项目根目录中，随代码仓库版本受控：

| 交付文件 | 核心内容 | 核心价值 |
|---|---|---|
| `<PROJECT_ROOT>/docs/<项目名>-系统蓝图.md` | • 竞品与差异化定位矩阵<br>• 领域核心实体与 DDL/结构体定义<br>• 核心业务状态机跃迁图<br>• 端到端核心业务时序图<br>• **3~5 个技术亮点与面试防守地图**（选型权衡/极限压测/避坑） | 提供全局架构心智模型，指导后续详细设计与技术答辩 |
| `<PROJECT_ROOT>/docs/<项目名>-实施计划.md` | • 自适应分期与 M0~M4 里程碑定义（支持 1期结项 / 2期演进 / 3期长程）<br>• 各阶段坚决不做的**剪裁红线**<br>• 结构化任务卡（含工作量、前置依赖与**可执行 DoD 验收清单**） | 指导项目排期协作，可直接无缝喂给下游 AI 编程 Agent 施工 |
| `<PROJECT_ROOT>/docs/adr/` | • 关键架构决策记录（Architecture Decision Records） | 记录每个选型的上下文、备选方案与后果评估 |

---

## 🔄 核心执行工作流（五步漏斗与方案门禁）

```
                         用户提出系统构想或业务需求
                                     │
                                     ▼
                Step 1: 业务澄清（通过结构化选项补齐模糊边界）
                                     │
                                     ▼
                Step 2: 架构推演（领域模型、状态机、时序与技术亮点）
                                     │
                                     ▼
                Step 3: 产出「一页纸蓝图与实施方案草案」
                                     │
                       ┌─────────────┴─────────────┐
                       ▼                           ▼
               [用户确认通过]                [用户驳回或指导调整]
                       │                           │
                       │                           └────► 补充细节并重新生成草案
                       ▼
                Step 4: 落地完整资产（蓝图.md + 实施计划.md + ADR）
                                     │
                                     ▼
                Step 5: 交付检查与下游施工提示
```

> ⚠️ **刚性门禁机制（Iron Rule 1）**：在输出完整的几十页技术文档前，AI 必须先生成紧凑的“一页纸方案草案”并向用户请示确认。未经用户明确批准，绝不擅自输出全量长文，确保把关权牢牢掌握在架构师手中。

---

## 📦 目录结构与规范

```text
idea-to-system-blueprint/
├── SKILL.md                          # 核心执行 SOP、门禁机制与 Agent 指令
├── README.md                         # 技能规范与集成指引
└── references/                       # 渐进式披露参考库（按需载入）
    ├── clarification-guide.md        # 结构化澄清提问指南（按业务领域归类）
    └── output-templates.md           # 蓝图、实施计划与任务卡的标准化 Markdown 模板
```

---

## 💻 快速安装与集成

本技能完全兼容国际 **Open Agent Skills 规范**，适配国内外全系主流 Agent。

### 方式 1 · 行业通用包管理器（skills.sh 标准）
```bash
# 在当前项目工作区根目录下执行
npx skills add ./idea-to-system-blueprint

# 或显式指定目标 Agent
npx skills add ./idea-to-system-blueprint -a claude-code
```

### 方式 2 · AI 原生一键自省安装（推荐 ⭐⭐⭐）
在目标项目中，直接向您的 AI Agent（Claude、ZCode、WorkBuddy、Antigravity 等）发送以下提示词：
> “请将 `E:\WorkSpace\SkillWorkSpace\idea-to-system-blueprint` 安装到我当前工程的 Agent 技能目录中（自动识别环境：若是 ZCode 写入 `.zcode/skills/`，WorkBuddy 写入 `.workbuddy/skills/`，Claude 写入 `.claude/skills/`，通用标准写入 `.agents/skills/`）。”

### 方式 3 · 多平台扫描路径速查

| 平台 / Agent | 项目级路径（随 Git 提交） | 用户全局路径（跨项目可用） |
|---|---|---|
| **通用开放标准 (`skills.sh`)** | `<项目>/.agents/skills/idea-to-system-blueprint/` | `~/.agents/skills/idea-to-system-blueprint/` |
| **Claude Code** (Anthropic) | `<项目>/.claude/skills/idea-to-system-blueprint/` | `~/.claude/skills/idea-to-system-blueprint/` |
| **ZCode** (Baidu ADE) | `<项目>/.zcode/skills/idea-to-system-blueprint/` | `~/.zcode/skills/idea-to-system-blueprint/` |
| **腾讯 WorkBuddy / CodeBuddy** | `<项目>/.workbuddy/skills/idea-to-system-blueprint/` | 桌面技能市场 / 全局规则 |
| **Cursor / Windsurf** | `<项目>/.cursor/skills/idea-to-system-blueprint/` | `~/.cursor/skills/idea-to-system-blueprint/` |
| **Google Antigravity** | `<项目>/.agents/skills/idea-to-system-blueprint/` | `~/.gemini/antigravity/skills/idea-to-system-blueprint/` |
| **DeepSeek Harness** (`dsh`) | `<项目>/.dsh/skills/idea-to-system-blueprint/` | `~/.dsh/skills/idea-to-system-blueprint/` |

---

## 💬 触发语句示例

在已经挂载本技能的环境中，您可以对 AI 提出任意类似指令以激活本技能：

- *“我有一个关于开发‘多租户协同看板系统’的想法，请帮我梳理成一份系统蓝图和实施计划。”*
- *“参考业界最佳实践，把当前需求拆解为包含数据模型、状态机和任务卡的实施计划。”*
- *“我们需要重构现有的交易订单链路，请使用 idea-to-system-blueprint 输出架构方案并梳理 3 个技术亮点。”*
