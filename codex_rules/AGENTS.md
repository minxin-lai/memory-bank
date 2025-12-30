# Codex project instructions (repo-root)

## Must-read repo context before coding
Read these files first:
- memory-bank/01-repo-overview.md
- memory-bank/02-context.md
- memory-bank/06-commands.md
- memory-bank/04-architecture.md
- memory-bank/03-plan.md
- memory-bank/05-progress.md

## Workflow contract
- Plan-first. If 03-plan.md is missing or outdated, update it before coding.
- Execute ONLY one step from 03-plan.md per iteration.
- Every step must produce a validation artifact (test output or benchmark log).
- All optimizations must be reversible (feature flag/config switch, safe default).
- After a passing step: update memory-bank/05-progress.md (and 04-architecture.md if boundaries changed).

## Development rules (source of truth)
Follow the rules described in:
- memory-bank/codex_rules/development.md
You MUST open and follow it before making code changes.
