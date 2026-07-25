# Chat History - ace-run (hu--plan)

- **TIMESTAMP:** 2026-07-22 07:20:39 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** hu--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-hu__plan-260722_071529.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260722_071529.md`

**Plan:** /home/bryan/.sase/plans/202607/ungrouped_agent_houses_first.md


## Prompt

#gh:gh_sase-org__sase Any agent house that does not belong in a panel sub-group (the `hi` agent in #sshot does not belong to any sub-group, for example--unlike `hk` and `hk.f0`, which both belong to the `hk` sub-group), then it should be listed above all sub-groups in that group (e.g. `hi` and `hh` should both be listed somewhere above the `hk` group). Can you help me diagnose the root cause of this issue and fix it? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/ungrouped_agent_houses_first.md`

> # Plan: Keep standalone agent houses above panel subgroups
> ## Context and root cause
> The Agents tab already intends dotless and singleton-name-root houses to render directly below their containing project,
> ChangeSpec, or status bucket before any name-root subgroup banner. `walk_order()` encodes that distinction through the
> name-root sort key, but its `BY_STATUS` path compares each display unit's shared launch-recency value before comparing
> whether the unit is standalone or belongs to a visible subgroup. A subgroup whose root launch is newer than a standalone
> house therefore sorts ahead of that house. This reproduces the reported shape: `hh` can render first, followed by the
> `hk` subgroup (`hk` and `hk.f0`), with standalone `hi` incorrectly left below the subgroup.
> The regression came from adding newest-first status ordering across all display units without retaining subgroup
> membership as the primary within-bucket partition. The structural grouping data and banner builder are correct; the

*See full plan file for details.*

