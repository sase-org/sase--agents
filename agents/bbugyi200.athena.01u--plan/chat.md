# Chat History - ace-run (01u--plan)

- **TIMESTAMP:** 2026-08-14 17:05:02 EDT
- **MODEL:** claude/opus
- **AGENT:** 01u--plan

**Plan:** /home/bryan/.sase/plans/202608/artifacts_pane_contract.md


## Prompt

#gh:gh_sase-org__sase Can you help me unify every ACE Artifacts sub-tab behind one API/contract so a
sidecar / artifact repo declares how its tab behaves, and so any new sub-tab feature is
implemented once and inherited by every configured provider — including providers
belonging to users we will never see?

- Lean on the artifacts_query_and_pane_contract.md file in the research sidecar repo
  heavily for context and inspiration.
- With that said, you are responsible for this feature's final success (make sure to
  clearly call out any area of your plan that contradicts the research file).
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful! 

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/artifacts_pane_contract.md`

> # Plan: One Artifacts contract
> ## Why this shape
> The Artifacts tab is five browser implementations wearing one tab bar. The widget
> package is 13,506 lines; four panes each carry their own filter model, row identity,
> detail scheduling and footer wiring, and Patch carries a fifth stack that the view
> refuses to treat like the others — `ArtifactsView.entry_navigator` raises
> `ValueError("Patches use the existing Patch navigation model")`
> (`src/sase/ace/tui/widgets/artifacts/view.py:194`). Provider specs already reach the
> panes and are then ignored: nothing reads them for presentation.
> The consequence is the thing this epic exists to remove. Today a new sub-tab feature is

*See full plan file for details.*

