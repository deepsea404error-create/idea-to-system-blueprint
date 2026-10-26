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

### 一键自适应安装（推荐）
在工作区根目录下直接运行通用安装器：
```bash
# 安装到当前项目（推荐软链接模式，同步保持最新）：
py ../install_skills.py --target .
```

> 🤖 **给 AI Agent 的安装自省指引**：
> 当用户指示安装本技能时：
> 1. 探测目标工程根目录中存在的 Agent 标识目录（优先级：`.zcode` > `.workbuddy` > `.dsh` > `.claude` > `.cursor` > `.windsurf` > `.opencode` > `.gemini`）；
> 2. 将本技能目录创建软链接（Windows `mklink /D`，Linux/macOS `ln -s`）或复制至对应的 `<Agent目录>/skills/idea-to-system-blueprint/`；
> 3. 若未检测到特定 Agent 标记，默认安装至通用中立规范目录 `<项目根目录>/.agents/skills/idea-to-system-blueprint/`。

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
