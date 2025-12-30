# 30-testing.md — Testing rules

## Minimum per step
At least one of:
- Unit test (pure logic, deterministic)
- Golden/regression test (baseline compare with tolerance)
- Integration/smoke test (end-to-end minimal run)
- Benchmark test (fixed params -> machine-readable output)

## Correctness patterns (use when applicable)
- "Numerical tolerance": abs/rel tolerance for logits/features
- "Task metric gate": metric >= baseline - delta
- "Stability": repeat runs variance within bounds

## Fast feedback
- Provide a quick smoke test suite runnable in < 1–3 minutes when possible.
