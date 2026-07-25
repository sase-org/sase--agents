# Chat History - ace-run (5p--plan)

- **TIMESTAMP:** 2026-07-11 12:42:10 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 5p--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-5p__plan-260711_123347.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260711_123347.md`

**Plan:** /home/bryan/.sase/plans/202607/agents_view_hint_race.md


## Prompt

#gh:gh_sase-org__sase Sometimes when I use the `v` (view) keymap on the "Agents" tab of the `sase ace` TUI, the hints that are initially shown disappear (see the ~/tmp/20260711_101812.png screenshot). Can you help me diagnose the root cause of this issue and fix it? Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/agents_view_hint_race.md`

> # Stabilize Agents-tab view hints against deferred detail repaints
> ## Context and root cause
> Pressing `v` on the Agents tab synchronously replaces the selected agent's prompt with a hint-annotated render and
> mounts the `View:` input bar. App-level detail refreshes already notice `_hint_mode_active` and preserve that annotated
> render, but entering hint mode does not advance `AgentDetail`'s render generation.
> The normal detail render may already have launched deferred prompt work: detail-header enrichment, linked-delta
> resolution, bead metadata resolution, workflow rendering, or the periodic slow-tool metadata tick. Those callbacks use
> the selected agent identity and `AgentDetail` generation to reject stale results. Because the hint render currently
> leaves the generation unchanged, a callback started before `v` still looks current and can run the plain prompt renderer
> after the hint-annotated renderer. The numbered markers then disappear while the `View:` input bar and its original

*See full plan file for details.*

