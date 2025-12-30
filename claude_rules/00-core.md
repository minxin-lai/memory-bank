# 00-core.md — Research-grade working contract

## Non-negotiables
- Plan-first; one-step rule; evidence-driven validation.
- Keep changes minimal; avoid unrelated refactors.
- All optimizations must be reversible (feature flag/config switch).

## Glue principle
- Glue does wiring only (CLI/config/orchestration).
- Core logic lives in testable modules.
- No hidden constants; thresholds/ratios are config + documented.

## Reproducibility defaults
- Prefer deterministic runs where feasible (seed, eval mode, fixed preprocessing).
- Every benchmark/log must include: timestamp, git SHA, config summary, environment summary.


