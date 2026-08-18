# Chat History - ace-run (06l--plan)

- **TIMESTAMP:** 2026-08-18 14:04:16 EDT
- **MODEL:** claude/opus
- **AGENT:** 06l--plan

**Plan:** /home/bryan/.sase/plans/202608/beads_detail_drop_readiness_row.md


## Prompt

#gh:gh_sase-org__sase Can you help me stop showing the "Readiness" field on the "Beads" sub-tab of the "Artifacts" tab? This is redundant since any ready bead has a task of ready. Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/beads_detail_drop_readiness_row.md`

> # Plan: Drop the Beads "Readiness" row
> ## Goal
> `Readiness` restates the `Status` row on every bead the user can actually select, so
> remove it from both Beads sub-tab surfaces:
> - the detail property grid built by `bead_properties_header()`
>   (`src/sase/ace/tui/widgets/artifacts/beads_detail.py:85`), and
> - the preview markdown built by `bead_preview_markdown()` (same file, line 198), which
>   is what `ArtifactsBeadsPane.preview_for_row()` feeds the preview panel.
> Both are the same sub-tab, so they change together; leaving `**Readiness:**` in the
> preview would just move the redundancy one keypress away.

*See full plan file for details.*

