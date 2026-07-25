# Chat History - ace-run (sase-89.4--plan)

- **TIMESTAMP:** 2026-07-20 14:11:17 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** sase-89.4--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-sase_89_4__plan-260720_124639.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260720_124639.md`

**Plan:** /home/bryan/.sase/plans/202607/project_display_regression_audit.md


## Prompt

#gh:gh_sase-org__sase
%id(4, clan=sase-89)
%model:@phase_worker
%auto
%w:sase-89.2,sase-89.3
Can you complete the work for bead sase-89.4? The bead has already been claimed for you (status=in_progress,
assignee set). Read its description and design file, do the work, and close the bead. Do NOT close the parent
epic. Do NOT create new beads.
Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/project_display_regression_audit.md`

> # Plan: Lock project display names across human-facing surfaces
> ## Context and success contract
> Phases 1–3 established an immutable `ProjectDisplaySnapshot`, projected every Statistics project-bearing view model, and
> repaired the confirmed CLI and TUI leaks. This final phase must make those repairs durable. The regression case is
> deliberately asymmetric: a canonical key such as `gh_acme__widgets`, configured label `widgets`, and canonical
> ChangeSpec identity such as `gh_acme__widgets_feature` must render as `widgets` / `widgets_feature` on human-facing
> surfaces while retaining the canonical strings in filters, joins, persistence, paths, task metadata, replay state, and
> machine-readable output.
> The work stays in the Python presentation and test layers unless the audit exposes a concrete missed presentation
> boundary. It must not change Rust aggregation, wire schemas, project lifecycle storage, ChangeSpec storage, or other

*See full plan file for details.*

