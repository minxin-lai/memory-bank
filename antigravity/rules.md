---
trigger: always_on
---

# Project entrypoint for Claude Code

## Always read these repo facts before coding
@memory-bank/01-repo-overview.md
@memory-bank/02-context.md
@memory-bank/06-commands.md
@memory-bank/04-architecture.md
@memory-bank/03-plan.md
@memory-bank/05-progress.md

## Workflow rules (shared)
@memory-bank/claude_rules/00-core.md
@memory-bank/claude_rules/10-planning.md
@memory-bank/claude_rules/20-coding.md
@memory-bank/claude_rules/30-testing.md
@memory-bank/claude_rules/40-benchmarking.md

## Execution contract
- Execute ONLY one step from memory-bank/03-plan.md at a time.
- Stop after completing the step and producing its validation artifact(s).
- After a passing step: update memory-bank/05-progress.md (and 04-architecture.md if module boundaries changed).

## Core Constraints
- Plan-first: Plan before coding; execute only one step at a time.
- Glue principle: Entry points should only handle wiring; core logic must be modular and independently testable.
- Evidence-driven: Every change requires a verification artifact (proof of testing).
- Minimal surface: Keep changes minimal; strictly avoid unrelated refactoring.