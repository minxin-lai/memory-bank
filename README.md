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

## 核心约束

- **Plan-first**: 先计划后编码，每次只执行一步
- **Glue principle**: 入口只做连接，核心逻辑模块化、可独立测试
- **Evidence-driven**: 每个改动须有验证产物
- **Minimal surface**: 改动最小化，避免无关重构
- **Reversible**: 优化必须可回滚（feature flag）