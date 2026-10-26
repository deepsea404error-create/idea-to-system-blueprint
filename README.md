# idea-to-system-blueprint

> 将业务构想 / 系统想法系统化拆解为工业级架构蓝图与分阶段任务卡实施计划。技术栈中立，通用适配各类研发系统。

---

## 它解决什么问题

当开发者或产品设计者产生一个项目 Idea 时，最容易出现的阻碍是：
- **想法粗放，不知从何下手**，直接写代码导致业务逻辑混乱，架构反复推倒重来；
- **缺乏明确的分期与剪裁红线**，一期范围膨胀蔓延，导致项目半途烂尾；
- **实施计划缺乏可验证的验收标准（DoD）**，分工协作或 AI 辅助编码时无法精准闭环；
- **技术亮点挖掘不足**，难以在面试、答辩或述职中条理清晰地防守架构决策。

`idea-to-system-blueprint` 通过 5 步漏斗模型建立工业级设计事实源：
1. **《系统蓝图.md》**：包含竞品矩阵、模块无环依赖拓扑、核心数据模型 DDL/结构体、状态机跃迁图、核心时序与 3~5 个技术亮点地图；
2. **《实施计划.md》**：包含明确剪裁红线、M0~M4 里程碑、标准化任务卡清单（带人日与精确 DoD）与架构决策记录（ADR）。

---

## 产物与落点规则

所有设计文档与实施计划均严格落在目标项目工作区内部：
- `<PROJECT_ROOT>/docs/<项目名>-系统蓝图.md`
- `<PROJECT_ROOT>/docs/<项目名>-实施计划.md`
- `<PROJECT_ROOT>/docs/adr/` (架构决策记录)

---

## 安装与跨 Agent 适配

本技能严格遵循开放标准（Open Agent Skills Standard），可无缝安装于国内外主流 AI Coding Agent 中。

### 方式 1：业界通用技能包管理器（推荐）
使用 `skills.sh` 开放标准 CLI 直接安装：
```bash
# 通用自适应安装至当前工程检测到的 Agent 目录
npx skills add ./idea-to-system-blueprint

# 或显式指定目标 Agent (支持 claude-code, cursor, opencode, codex 等)
npx skills add ./idea-to-system-blueprint -a claude-code
```

### 方式 2：对当前使用的 AI Agent 直接下发指令（AI 一键自装）
在目标项目中打开您的 AI 对话框，直接发送以下指令：
> “请帮我把 `e:\WorkSpace\SkillWorkSpace\idea-to-system-blueprint` 技能安装到当前工程的对应 Agent 技能目录中（如果是 ZCode 写入 `.zcode/skills/`，WorkBuddy 写入 `.workbuddy/skills/`，Claude Code 写入 `.claude/skills/`，未识别则统一写入通用开放标准 `.agents/skills/`）。”

### 方式 3：Git Submodule / 软链接 / 复制
直接将本目录软链接或复制至目标工程对应目录即可立即生效：
```bash
# 通用开放标准（兼容 Cursor, OpenCode, Codex, Antigravity 等）
mkdir -p .agents/skills
cp -r /path/to/idea-to-system-blueprint .agents/skills/

# Claude Code
mkdir -p .claude/skills
cp -r /path/to/idea-to-system-blueprint .claude/skills/

# ZCode (ADE)
mkdir -p .zcode/skills
cp -r /path/to/idea-to-system-blueprint .zcode/skills/
```

### 主流 Agent 扫描路径对照表

| 平台 / Agent | 项目级路径（当前仓库生效） | 用户/全局级路径（全局可用） |
|---|---|---|
| **ZCode** (腾讯/国内主流) | `<项目>/.zcode/skills/idea-to-system-blueprint/` | `~/.zcode/skills/idea-to-system-blueprint/` |
| **Tencent WorkBuddy** | `<项目>/.workbuddy/skills/idea-to-system-blueprint/` | `~/.workbuddy/skills/idea-to-system-blueprint/` |
| **DeepSeek Harness** (`dsh`) | `<项目>/.dsh/skills/idea-to-system-blueprint/` | `~/.dsh/skills/idea-to-system-blueprint/` |
| **Claude Code** (Anthropic) | `<项目>/.claude/skills/idea-to-system-blueprint/` | `~/.claude/skills/idea-to-system-blueprint/` |
| **OpenCode** (开源) | `<项目>/.opencode/skills/idea-to-system-blueprint/` | `~/.config/opencode/skills/idea-to-system-blueprint/` |
| **OpenAI Codex / CLI** | `<项目>/.agents/skills/idea-to-system-blueprint/` | `~/.agents/skills/idea-to-system-blueprint/` |
| **Cursor** | `<项目>/.cursor/skills/idea-to-system-blueprint/` | `~/.cursor/skills/idea-to-system-blueprint/` |
| **Windsurf** (Codeium) | `<项目>/.windsurf/skills/idea-to-system-blueprint/` | `~/.codeium/windsurf/skills/idea-to-system-blueprint/` |
| **Google Antigravity (AGY)** | `<项目>/.gemini/skills/idea-to-system-blueprint/` | `~/.gemini/antigravity/skills/idea-to-system-blueprint/` |
| **开放标准规范 (Universal)** | `<项目>/.agents/skills/idea-to-system-blueprint/` | `~/.agents/skills/idea-to-system-blueprint/` |

