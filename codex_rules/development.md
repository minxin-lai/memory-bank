# Research-grade agent working agreements (PhD, reproduction + inference optimization)

## 0) Operating contract (non-negotiable)
- Plan-first: before editing code, produce/refresh a step-by-step plan and name the single step you will execute next.
- One-step rule: execute ONLY one step per iteration. Do not start the next step until validation for the current step passes.
- Evidence-driven: every change must come with a measurable validation artifact (test output, benchmark JSON/CSV, log excerpt, or metric table).
- Minimal surface: prefer small changes. Avoid refactors unless required by the current step.


## 1) Glue principle (anti-spaghetti)
- Glue layer does wiring only (CLI, config loading, dependency injection, pipeline orchestration).
- Core research logic MUST live in testable modules (pure functions / small classes), not hidden in glue.
- No "magic constants" in glue. Thresholds/ratios belong in configs with documented defaults.

## 2) How to generate a plan (required format)
When asked to "make a plan" or before coding:
1) Ask clarifying questions if any of these are missing:
   - Inputs/outputs and correctness criteria (tolerance, acceptance threshold)
   - Baseline command + exact commit/version
   - Evaluation protocol (warmup, repeats, latency/throughput definition, sync boundaries)
   - Target environment (GPU/CPU, batch, sequence length, resolution/fps, codec)
2) Produce `plan.md`-style steps. Each step MUST include:
   - Goal (what we prove)
   - Change surface (files/modules likely touched)
   - Commands to run (build/test/bench)
   - Validation gate (pass/fail rule; metric thresholds)
   - Artifacts to save (where logs/results go)


## 3) Coding rules (quality + reproducibility)
- Keep modules small and named by responsibility (e.g., pruner/, codec_features/, bench/, metrics/, configs/).
- Prefer explicit interfaces: define input/output dataclasses or typed dicts.
- Determinism where feasible: seed control, fixed model eval mode, fixed preprocessing.
- Logging: structured logs (JSONL preferred) for benchmarks; include git SHA, config hash, timestamp, environment summary.
- Avoid adding heavy dependencies without strong justification.

## 4) Testing rules (minimum set)
Every coding step must add or update at least one of:
- Unit test (pure logic, deterministic)
- Golden / regression test (baseline comparison with tolerance)
- Integration test (end-to-end minimal run)
- Benchmark test (micro/throughput/latency) with fixed parameters

If tests are slow, create a "smoke" subset.

## 5) Benchmark & profiling rules (for inference optimization)
- Always separate: (a) correctness validation and (b) performance measurement.
- Warmup before timing; measure multiple runs; report at least P50/P90 and throughput.
- Define timing boundary explicitly (end-to-end vs model-only). Never mix them in the same chart/table.
- GPU timing must include synchronization boundaries (document exactly where you synchronize).
- Record peak memory (VRAM) consistently.

## 6) Research workflow hygiene
- Before claiming an improvement, re-run baseline under the same protocol and hardware.
- Save an experiment record per run: date, git SHA, command, config, metrics, notes, anomalies.
- Maintain an ablation matrix: one variable at a time; keep fixed factors explicit.

## 7) Safety / secrets
- Never print or exfiltrate secrets. Do not paste private keys, tokens, or proprietary data into code or logs.
