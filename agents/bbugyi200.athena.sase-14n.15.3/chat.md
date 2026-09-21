# Chat History - ace-run (sase-14n.15.3)

- **TIMESTAMP:** 2026-09-21 18:31:57 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-14n.15.3

## Prompt

#gh:gh_sase-org__sase
%id(3, clan=sase-14n.15, bead=sase-14n.15.3)
%model:@medium
%auto
%w:sase-14n.15.1
%w(bead=sase-14n.15.1)
Can you complete the work for bead sase-14n.15.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-14n.15.3 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-14n.15.3 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-14n.15.3`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-14n.15.3 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-14n.15.3 is done and closed.

What changed: direct `create_gate` with a shell-bearing custom spec now raises `missing_gate_shell_row` instead of silently recording a rowless gate. The gate-shell transaction passes an internal `shell_row_managed` marker that raw JSON cannot claim. The fabricated row test in `tests/gate_shell/test_model_shell.py` is now a real `create_gate_shell` run in a temp home/project asserting the `gate_shell` mode, the member row, and visibility via both `list_gate_shells` and `sase gate list --all --json`, plus a test that the bypass fails loudly.

Finding recorded in the close note: CLI shell-routing predates `c04171670`, so the historic rowless gate came from direct creation or list-side filtering (terminal rows hidden without `--all`, or wrong project), not the old `none` default via CLI. Guard scoped to `kind=custom`; extending it to built-in kinds is filed as a `PROPOSED FOLLOW-UP` note for the land agent.

Verification: focused suites (settlement, detach, conformance, fakey, sudo, question, transaction) green; `sase tool run check` reached 4538 passed with only 3 failures I proved pre-existing on the clean tree (bead free-text classification, question-pane footer, core-rs bindings). No `--epic-symbol` leftovers.
