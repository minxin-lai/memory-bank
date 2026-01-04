# Memory Bank — Vibe Coding 提示仓库

为 AI Coding Agents 提供项目上下文和工作规范的"薄层记忆库"。

## 目录结构

**项目事实层**
- `01-repo-overview.md` — 仓库简介、边界、依赖
- `02-context.md` — 论文/commit/数据集规格
- `03-plan.md` — 当前执行计划
- `04-architecture.md` — 模块边界
- `05-progress.md` — 进度和结果
- `06-commands.md` — setup/test/bench 一键命令

**Agent 规则**
- `claude_rules/` — Claude Code 入口 + 分模块规范
- `antigravity/` — Gemini Antigravity 规则
- `codex_rules/` — OpenAI Codex 规则

## 用法

1. 复制 `memory-bank/` 到项目根目录
2. 填写项目事实层的 6 个文件
3. 将对应 Agent 入口文件（如 `CLAUDE.md`）放到项目根目录

## Core Constraints
- Plan-first: Plan before coding; execute only one step at a time.
- Glue principle: Entry points should only handle wiring; core logic must be modular and independently testable.
- Evidence-driven: Every change requires a verification artifact (proof of testing).
- Minimal surface: Keep changes minimal; strictly avoid unrelated refactoring.
- Reversible: Optimizations must be reversible (e.g., via feature flags).