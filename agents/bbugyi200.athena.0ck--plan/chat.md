# Chat History - ace-run (0ck--plan)

- **TIMESTAMP:** 2026-08-24 12:29:27 EDT
- **MODEL:** claude/opus
- **AGENT:** 0ck--plan

**Plan:** /home/bryan/.sase/plans/202608/symvision_stale_epic_symbols.md


## Prompt

#gh:gh_sase-org__sase Can you help me fix the `just symvision` command (see the command output below for context)? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 
```
┌───────────────────────────────────────────────────────┐
│                RUNNING: just symvision                │
└───────────────────────────────────────────────────────┘
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github from /home/bryan/projects/github/sase-org/sase-github.
[setup] Installing required plugin sase-research-artifacts from /home/bryan/projects/github/sase-org/sase-research-artifacts.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop --epic-symbol "sase-n4.5(ProviderDisableWriteOutcome)" --epic-symbol "sase-n4(get_usage_limit_config)" --epic-symbol "sase-sp.3(FinalizerDeferralWire)" --epic-symbol "sase-sp.3(finalizer_deferral_from_dict)" --epic-symbol "sase-su.2(plan_provider_drain)" --epic-symbol "sase-su.2(execute_provider_drain)"
Error: --epic-symbol 'sase-su.2(plan_provider_drain)': symbol 'plan_provider_drain' is already properly used. Remove this unnecessary --epic-symbol entry.
Error: --epic-symbol 'sase-su.2(execute_provider_drain)': symbol 'execute_provider_drain' is already properly used. Remove this unnecessary --epic-symbol entry.
error: recipe `_lint-symvision` failed on line 340 with exit code 1
error: recipe `symvision` failed on line 786 with exit code 1
```

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/symvision_stale_epic_symbols.md`

> # Clear the stale symvision `--epic-symbol` entries that break `just symvision`
> ## Problem
> `just symvision` fails on a clean `master` tree, which also reddens the `symvision`
> stage of `just lint` and `just check` for every agent in the repo, regardless of what
> they changed.
> The `_lint-symvision` recipe in `Justfile` passes a whitelist of
> `--epic-symbol "<bead_id>(<symbol>)"` exemptions. Those exemptions are _self-cleaning_:
> symvision fails the run when an entry's bead is missing or closed, when the symbol is
> now properly used by a non-test consumer, or when the symbol no longer exists as a
> public definition. Four of the six entries have gone stale as their epic phases landed

*See full plan file for details.*

