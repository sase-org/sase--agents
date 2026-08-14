# Chat History - ace-run (014--plan)

- **TIMESTAMP:** 2026-08-14 10:49:03 EDT
- **MODEL:** claude/opus
- **AGENT:** 014--plan

**Plan:** /home/bryan/.sase/plans/202608/models_panel_pool_authoring.md


## Prompt

#gh:gh_sase-org__sase Do we currently support specifying model pools when overriding model alias definitions in the "Models" panel? We should fully suppor this use-case. If not, use your /sase_plan skill to plan the appropriate changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/models_panel_pool_authoring.md`

> # Full model-pool support when overriding model alias definitions in the Models panel
> ## Problem
> The ACE Models panel (`,m`) is the authoritative place to edit model alias definitions
> (`docs/llms.md:1170`). Alias values may be selector expressions — `A | B`
> (availability-filtered round-robin pool) or `A || B` (ordered fallback chain) — and
> selectors are explicitly **config-only**: `%model` values, launch-scoped alias
> overrides, and temporary overrides all remain single targets (`docs/llms.md:1140`).
> Pools are therefore _only_ reachable through the panel's persistent **Edit** (`e`) path,
> and today that path supports them barely and unevenly:
> 1. **Authoring is hand-typing only.** `e` opens `ModelPickerModal`, which is

*See full plan file for details.*

