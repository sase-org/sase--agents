# Chat History - ace-run (tn--plan)

- **TIMESTAMP:** 2026-08-05 20:55:54 EDT
- **MODEL:** claude/opus
- **AGENT:** tn--plan

**Plan:** /home/bryan/.sase/plans/202608/test_suite_tier1.md


## Prompt

#gh:gh_sase-org__sase Can you help me implement the `Tier 1` recommendations in the `Recommended solution` section of the test_suite_verification_architecture.md file in the research sidecar repo? Tier 0 was completed already (see recent, related git commits). Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/test_suite_tier1.md`

> # Plan: Test suite Tier 1 — two-speed verification
> ## Background
> The research report
> [`202608/test_suite_verification_architecture/test_suite_verification_architecture.md`](https://github.com/sase-org/sase--research/blob/main/202608/test_suite_verification_architecture/test_suite_verification_architecture.md)
> in the `sase--research` sidecar concludes that the suite is slow because of **admitted demand**, not slow tests: 200–400
> full-suite runs per day at ~61 worker-minutes each, against a host supplying ~46,000 worker-minutes per day — 26% to 53%
> of the machine, continuously.
> **Tier 0 is done** (commit `9672c5602`): proportional gate CPU reserve, 950 MiB per-worker memory reserve, visual lane
> out of the default `just test`, three scale tests behind `slow` with a CI home. That fixed per-run cost and CI
> throughput. It did not touch demand.

*See full plan file for details.*

