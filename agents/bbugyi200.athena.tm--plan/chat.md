# Chat History - ace-run (tm--plan)

- **TIMESTAMP:** 2026-08-05 19:11:22 EDT
- **MODEL:** claude/opus
- **AGENT:** tm--plan

**Plan:** /home/bryan/.sase/plans/202608/test_suite_tier0.md


## Prompt

#gh:gh_sase-org__sase Can you help me implement the `Tier 0` recommendations in the `Recommended solution` section of the test_suite_verification_architecture.md file in the research sidecar repo? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/test_suite_tier0.md`

> # Plan: Test suite Tier 0
> ## Background
> The research report `202608/test_suite_verification_architecture/test_suite_verification_architecture.md` in the
> `sase--research` sidecar concludes that the suite is slow because of **admitted demand**, not slow tests: roughly
> 200–400 full-suite runs per day at ~61 worker-minutes each, against a host that supplies ~46,000 worker-minutes per day.
> This plan implements only that report's **Tier 0** section — four low-risk changes it describes as "this week, hours of
> work, no architectural risk". Tier 1 (diff-scoped selection, `just check-full`, the no-lease scoped path) and Tier 2 are
> explicitly **not** in scope.
> The canceled epic `sase-fd` ("Make the default parallel test suite reliable under host contention") was closed with the
> reason "See research.y agents (I plan on going with their plan instead)". This plan is that replacement for the Tier 0

*See full plan file for details.*

