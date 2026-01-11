# Memory-Bank

为 AI Agent 提供项目上下文和工作规范。

## 快速开始

1. 复制此仓库到你的项目
2. 让 AI 读取并初始化 `01-PROJECT.md`
3. 在 `02-TASK.md` 描述任务目标
4. AI 生成 `03-PLAN.md` 并逐步执行

## 文件说明

| 文件 | 用途 | 谁填写 |
|------|------|--------|
| RULES.md | AI 工作规范 | 已填写 |
| 01-PROJECT.md | 项目上下文 | AI 或用户 |
| 02-TASK.md | 任务目标 | 用户 |
| 03-PLAN.md | 执行计划 | AI |

## Agent 入口

| 文件 | 适用于 |
|------|--------|
| agents/CLAUDE.md | Claude Code |
| agents/AGENTS.md | OpenAI Codex |
| agents/GEMINI.md | Gemini Antigravity |