# Chat History - ace-run (vf--plan)

- **TIMESTAMP:** 2026-08-07 21:35:16 EDT
- **MODEL:** claude/opus
- **AGENT:** vf--plan

**Plan:** /home/bryan/.sase/plans/202608/saved_query_zero_prefix.md


## Prompt

#gh:gh_sase-org__sase Can you help me fix the saved PR / ChangeSpec query keymaps (which are mapped
to "Artifacts" sub-tabs now)?

- Let's have each numeric saved query keymap use the `0` prefix now.
- For example, after this change we would use `02` to load the 2nd saved PR query slot
  instead of `2`.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/saved_query_zero_prefix.md`

> # Plan: Restore direct saved-PR-query slot keys behind a `0` prefix
> ## Background
> Saved PR/ChangeSpec queries used to be loadable with bare digits: `2` loaded slot 2.
> Commit `835929471` ("feat(ace): add numbered artifacts and saved query picker") took
> those digits away and gave them to the Artifacts sub-tabs:
> - `src/sase/ace/tui/keymaps/bindings.py` and `src/sase/ace/tui/bindings.py` now build
>   `Binding(str(index), f"show_artifacts_{subtab}", ...)` for
>   `enumerate(ARTIFACTS_SUBTAB_ORDER, start=1)` — today that is `1`=Commits, `2`=Beads,
>   `3`=Bugs, `4`=PRs, `5`=Files. These are deliberately non-configurable.
> - The 10 `action_load_saved_query_<d>` methods still exist in

*See full plan file for details.*

