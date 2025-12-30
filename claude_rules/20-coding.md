# 20-coding.md — Coding rules

## Structure
- Split by responsibility: pruner/, codec_features/, bench/, metrics/, configs/, utils/.
- Prefer explicit interfaces (dataclass/typed dict) between stages.
- Keep glue thin; no research logic in CLI entrypoints.

## Change discipline
- Implement ONLY the current planned step.
- Prefer small PR-sized commits.
- Add feature flags for any optimization; safe default.

## Logging
- Benchmarks must emit structured outputs (JSONL/CSV).
- Always include git SHA + config summary in outputs.
