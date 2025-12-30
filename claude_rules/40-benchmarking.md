# 40-benchmarking.md — Benchmarking & profiling rules

## Separate boundaries
- Define clearly: end-to-end (includes decode/preproc) vs model-only.
- Never compare runs with different boundaries.

## Timing protocol
- Warmup runs before timing.
- Multiple measured runs; report P50/P90 and throughput.
- Record peak VRAM consistently.

## Claims
- Re-run baseline under identical protocol/hardware before reporting an "improvement".
- Keep an ablation matrix: one variable at a time; fixed factors explicit.
