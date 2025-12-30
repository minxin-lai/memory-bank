# 10-planning.md — How to plan (required format)

## Before coding, ask if missing
- Baseline repo + exact commit/version + "how to run"
- Correctness criteria (metric + tolerance/threshold)
- Evaluation protocol (warmup, repeats, P50/P90, boundary definition)
- Environment (GPU/CPU, batch, seq len, resolution/fps, codec)

## Step template (must use)
For each step:
- Goal:
- Change surface (files/modules):
- Commands (build/test/bench):
- Validation gate (pass/fail):
- Artifacts to save (paths, filenames):
- Rollback (flag/config or revert instructions):

## Planning ordering
1) Make baseline reproducible + scripted.
2) Add instrumentation (metrics + logging) so all future claims are comparable.
3) Implement minimal optimization behind a flag.
4) Add correctness regression.
5) Do performance sweep + ablations.
