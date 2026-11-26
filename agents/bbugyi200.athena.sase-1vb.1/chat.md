# Chat History - ace-run (sase-1vb.1)

- **TIMESTAMP:** 2026-11-26 06:51:15 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1vb.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-1vb.1, bead=sase-1vb.1)
%clan(sase-1vb, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@small
%auto
Can you complete the work for bead sase-1vb.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1vb.1` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything. Only when the host notice said the bead was already
closed and the work is genuinely unfinished, run `sase bead open sase-1vb.1` first. Otherwise never run
`sase bead open` on your own bead: it demotes an `in_progress` bead back to `open`. To view a bead, run
`sase bead read sase-1vb.1 -r "<why you need this bead>"`. Read its
description and design file with `sase bead read sase-1vb.1 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1vb.1 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1vb.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1vb.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Bead sase-1vb.1 closed.

Done: [tools/_release_watch_facts.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tools/_release_watch_facts.py) now emits assets with only `name/kind/generation` (id still validated), `_fresh_train_abandoned` reads ids from the raw release, fixtures in `tests/_release_watch_facts_contract_cases.py`, [tests/_release_watch_train_start_helpers.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11/tests/_release_watch_train_start_helpers.py), and `tests/test_release_watch_train_start_walk.py` fixed, plus new unit (`test_release_wire_emits_exact_asset_shape`) and real-binding (`test_real_binding_accepts_release_wire_assets_when_installed`) regression tests.

Verified: `tests/*release_watch*` + `test_github_actions_release_steward` pass, `sase tool run check` green. `sase bead epic-symbols` clean.
