# Chat History - ace-run (1f5--plan)

- **TIMESTAMP:** 2026-11-22 08:34:48 EST
- **MODEL:** claude/opus
- **AGENT:** 1f5--plan

**Plan:** /home/bryan/.sase/plans/202611/fix_running_field_import_cycle.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/fix_running_field_import_cycle.md`

> # Fix the `sase.running_field` ↔ `sase.core.agent_launch_claims` import cycle
> ## Problem
> Every hourly run of the `housekeeping/disk_pressure` chop has failed since
> `ff0baf13e9 perf(axe): cheap hooks-lane jobs and fewer spawns` (2026-11-21). So
> disk-pressure housekeeping is not running at all. The job crashes at import time:
> ```
> ImportError: cannot import name 'allocate_and_claim_workspace_from_content' from partially
> initialized module 'sase.core.agent_launch_claims' (most likely due to a circular import)
> ```
> The import chain is:

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase Is this something we can/should fix? If so, use your /sase_plan skill to plan the appropriate changes. See the
~/.sase/axe/error_digests/digest_20261122_081602_d29f793f.txt file for context.
%m:@xlarge

## Response

Every hourly `disk_pressure` run has failed since that commit landed, so disk-pressure housekeeping is currently not running at all. This is worth fixing. Writing the plan now.

I'll quickly prototype the lazy-package fix in a throwaway worktree to confirm it breaks the cycle before I commit to it in the plan.

The plan validates. Proposing it now.

Yes, it's fixable and worth fixing now. Every hourly `housekeeping/disk_pressure` run since yesterday evening has crashed at import, so disk-pressure housekeeping isn't running at all. I've proposed a small plan, now staged for your approval.

**Root cause:** two modules import each other.
- `sase.core.agent_launch_claims` imports `WorkspaceClaim` from `sase.running_field._model`.
- Importing that file first runs the `sase/running_field/__init__.py` package file, which loads `_claim`.
- `_claim` imports back from `agent_launch_claims` while it is still half-loaded, which is the `ImportError` in the digest.

This loop has existed since May but stayed hidden: other packages loaded `sase.running_field` first on every real entry point. Bisect shows the first broken commit is `ff0baf13e9 perf(axe): cheap hooks-lane jobs and fewer spawns`. It made `sase.monitor`, `sase.procs` and `sase.agent.hijack` load their names on first use instead of at import, which removed that ordering. On current master, three modules fail when imported in a fresh interpreter: `sase.core.agent_launch_claims`, `sase.workspace_provider.inventory` and `sase.workspace_provider.occupancy_conflicts`. Among the 56 entry-point modules, only the `disk_pressure` chop script fails.

**The plan** (`sase_plan_fix_running_field_import_cycle.md`, a single-agent plan sized small):
1. **The fix:** make `sase/running_field/__init__.py` load its names on first use, the same way `ff0baf13e9` already did for `sase.monitor`. Importing `running_field._model` then no longer loads `_claim`, which breaks the loop. I tried exactly this in a throwaway worktree: all four failing imports work, and every name in `__all__` still resolves.
2. **Regression tests** in `tests/test_chop_import_budget.py`: tests that import each module in the loop first, each in a fresh interpreter, plus a check that importing `_model` doesn't pull in `_claim`. One decision is embedded, defaulting to "yes": whether to also fresh-import every `sase_chop_*` script. That's about 37 probes (~12s serial), so any future import crash in a scheduled job fails CI instead of showing up in a digest.
3. **An unrelated break on master:** `tests/test_held_settle_evidence.py` doesn't load at all. Commit `2ede612ca7` moved the two helpers it imports into `tests/_stale_running_cleanup_monitor_claims_retention.py`, and its import wasn't updated. `just check` would hit this, so the plan includes the one-line fix.

No reinstall is needed: once the fix reaches master and the primary checkout syncs, the next hourly `disk_pressure` run will pick it up.
