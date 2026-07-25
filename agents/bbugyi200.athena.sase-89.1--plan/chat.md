# Chat History - ace-run (sase-89.1--plan)

- **TIMESTAMP:** 2026-07-20 12:50:54 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** sase-89.1--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-sase_89_1__plan-260720_124636.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260720_124636.md`

**Plan:** /home/bryan/.sase/plans/202607/project_display_contract.md


## Prompt

#gh:gh_sase-org__sase
%id:sase-89.1
%clan(sase-89, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@phase_worker
%auto
Can you complete the work for bead sase-89.1? The bead has already been claimed for you (status=in_progress,
assignee set). Read its description and design file, do the work, and close the bead. Do NOT close the parent
epic. Do NOT create new beads.
Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/project_display_contract.md`

> # Plan: Establish the project identity and display projection contract
> ## Context and boundaries
> Project lifecycle records already distinguish the canonical directory key from the configured name through
> `ProjectRecordWire.project_name`, `ProjectRecordWire.display_name`, and `effective_project_name`. The current
> `project_display_names` convenience layer collapses that distinction into mutable dictionaries, refreshes against only
> the projects-root directory mtime, and lets presentation callers resolve names directly. A nested ProjectSpec rename
> therefore can remain stale, while TUI consumers have no explicit immutable value to load off-thread and pass to pure
> renderers.
> This phase will establish the reusable Python presentation boundary only. Canonical project keys remain authoritative
> for persistence, paths, joins, filters, colors, selections, and structured payloads; Rust lifecycle and statistics

*See full plan file for details.*

