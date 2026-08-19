# Chat History - ace-run (sase-r0.8--plan)

- **TIMESTAMP:** 2026-08-19 16:09:35 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-r0.8--plan

## Prompt

#gh:gh_sase-org__sase
%id(8, clan=sase-r0, bead=sase-r0.8)
%model:@small
%auto
%w:sase-r0.5,sase-r0.7
%w(bead=sase-r0.5)
%w(bead=sase-r0.7)
Can you complete the work for bead sase-r0.8? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-r0.8 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-r0.8`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-r0.8 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

# Monitor handoff

This agent delegated the remaining work to a monitor shell.
Monitor ID: ea7w0yf1hkmf
Inspect with: sase monitor show ea7w0yf1hkmf
Monitor shell: sase-r0.8--mon
Directory: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13

Command:

```sh
just test-visual && just check-full
```

Reason:

sase-r0.8 polish requires the PNG visual suite plus check-full after just check escalated

Next action:

You are the follow-up for phase bead sase-r0.8 (polish: parity guarantee, visual snapshot, and documentation). The implementation is already in this workspace. Do not set bead status by hand.

Already done:
- tests/tmux_agent/test_shell_script_parity.py pins argv flag-sets against the chezmoi tmux_ai_window script (order is not the contract), menu keys c/x/a/q/o/g/m, window names ai/ai2/ai3, and tm-renumber-ai-windows.
- PNG snapshot tests/ace/tui/visual/test_ace_png_snapshots_models_panel_modals.py::test_models_panel_tmux_agent_modal_png_snapshot with golden models_panel_tmux_agent_modal_120x40.png covering ready, not-installed, and routing-disabled rows.
- docs/ace.md: t on the Launch Control key table, the three ,m leader tables, and a ### tmux Agent subsection.
- docs/cli.md command-table row for sase tmux-agent.
- docs/configuration.md full tmux_agent block, parity recipe, and CLI flags.
- docs/plugins.md llm_interactive_cli plus vendor on llm_install_metadata.
- docs/agent_providers.md pointer that installed CLIs are launchable with sase tmux-agent.
- Justfile: dropped three already-used sase-r1.5 --epic-symbol entries (UpdateOptionChip, UpdateOptionRow, UpdatePanelState) so lint could pass. UpdatePanel, UpdatePanelResult, and build_update_panel_state remain. A PROPOSED FOLLOW-UP note is already on sase-r0.8.
- Parity tests passed. The PNG golden was generated with --sase-update-visual-snapshots and visually inspected.
- sase bead epic-symbols sase-r0.8 reported no leftovers for this phase.

The monitored command was `just test-visual && just check-full`.

If it failed:
- If the only failure is leftover --epic-symbol entries marked already properly used, remove those Justfile entries and re-run the failing gate, then just test-visual and just check-full via /sase_monitor if still long.
- Otherwise fix the failures from this phase, re-run the failing gate, and use /sase_monitor for another just check-full if needed.

If it passed, or after you fix it:
1. Run `sase bead epic-symbols sase-r0.8`. If this phase still has --epic-symbol entries, resolve each symbol or re-key the Justfile line to a still-open bead. sase bead close refuses while leftovers remain.
2. Close ONLY this bead: `sase bead close sase-r0.8 --note "<what you verified>"`. Do NOT close the parent epic sase-r0 or any ancestor.
3. Reply to the user summarizing what landed for sase-r0.8.

