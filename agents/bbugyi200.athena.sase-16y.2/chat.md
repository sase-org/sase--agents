# Chat History - ace-run (sase-16y.2)

- **TIMESTAMP:** 2026-09-23 11:41:14 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-16y.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-16y, bead=sase-16y.2)
%model:@small
%auto
Can you complete the work for bead sase-16y.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-16y.2 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-16y.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-16y.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-16y.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-16y.2 is closed.

What landed (keymap phase of the jump-panel epic):

- New Agents-only `toggle_agent_jump_panel` on `.`, inert until the panel phase: availability and palette gating use `getattr` for `jump_panel_toggle_available`, and the action calls `toggle_jump_panel_expanded()` only when present. On Agents, `.` is now a clean no-op.
- Non-run toggle moved to new `toggle_hide_non_run_agents` on `I`; `toggle_hide_reverted` narrowed to Services axe commands; new tab-disjoint registry pairs for the three `.` owners.
- Updated command palette (jump entry AGENTS_ONLY + gated; `toggle_hide_reverted` narrowed to Services; new non-run entry), help modal (row moved from General into Agent Actions, no jump row advertised early), `docs/ace.md`, and `docs/configuration.md` allowlist.
- Tests: extended keymap defaults/bindings/validation, palette wiring, availability, and key-resolution suites; new [test_agents_non_run_toggle_keys.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_40/tests/ace/tui/test_agents_non_run_toggle_keys.py) proving `I` toggles and `.` no longer does on Agents while still toggling axe commands on Services.

Verification: 197 targeted tests pass; fmt, ruff, mypy, feature-flags, test-waits, and toobig are green; `epic-symbols` clean. Full `just check` can't go fully green on this tree: pyscripts and symvision fail only on pre-existing files I didn't touch, and the scoped suite (45k+ passing) has 13–14 failures in bead/prompt-history/query-profile areas — none reference the new symbols and the set varies between runs. No PNG goldens affected (no widget in this phase).

Declaration accepted for the commit payload (bead already closed, so declared with keep). No other work done on this recovery turn.
