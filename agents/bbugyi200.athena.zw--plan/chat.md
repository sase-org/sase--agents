# Chat History - ace-run (zw--plan)

- **TIMESTAMP:** 2026-08-13 15:23:04 EDT
- **MODEL:** claude/opus
- **AGENT:** zw--plan

**Plan:** /home/bryan/.sase/plans/202608/sase_context_incremental.md


## Prompt

#gh:gh_sase-org__sase Can you help me make the `SASE CONTEXT` section shown in the agent metadata panel start appearing (with all of its contents) much faster without blocking the TUI? It can take a while currently for the bead/plan/commit context to show currently (because this whole section takes a while to load).

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/sase_context_incremental.md`

> # Plan: SASE CONTEXT — stop re-parsing three whole stores per agent and stream the section lane by lane
> ## Why this plan exists
> Selecting an agent on the Agents tab shows the metadata header immediately, but the
> `SASE CONTEXT` section — `PLAN`, `BEAD`, `ARTIFACTS` (commits, deltas, artifact files),
> `MEMORY`, `SKILLS`, `WORKSPACES` — stays absent for a noticeable beat and then appears
> all at once.
> That is not incidental. `build_header_text` renders the section only when
> `not cheap and summary is not None`
> (`src/sase/ace/tui/widgets/prompt_panel/_agent_display_header.py:276`), and `summary` is
> produced by one monolithic worker task, `build_detail_header_summary`

*See full plan file for details.*

