# Chat History - ace-run (sase-17x.2)

- **TIMESTAMP:** 2026-09-24 11:55:08 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-17x.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-17x, bead=sase-17x.2)
%model:@medium
%auto
Can you complete the work for bead sase-17x.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-17x.2 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-17x.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-17x.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-17x.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-17x.2 (Command Line spec contract) is complete and closed.

What was built:
- [model.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/completion/model.py) — `OptionSpec` gains `required`/`metavar`/`default`/`value_hint`, `PositionalSpec` gains `required`/`value_hint`, `CommandSpec` gains `run_policy`/`writes`/`stdin` (new `RunPolicyRule` type). `from_json` stays tolerant of older caches; `structural_view` covers the new grammar fields.
- [run_policy.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/completion/run_policy.py) (new) — foreground/deny table, writes verb heuristic with true/false overrides, stdin set. Every path verified against the live parser. Two plan items needed adjustment: `sudo approve` is `sudo answer` in the live parser (rule keys on absent `approve`/`deny`), and `gate act` editor actions can't be expressed statically (edit_file is a runtime bundle property), so no static rule was added there.
- [build.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/completion/build.py) — populates all new fields, including `required` derivation for every `nargs` shape and display-safe defaults (scalar ≤40 chars, SUPPRESS→null).
- `sase completion spec -d/--descriptions` — full-summary view for the Command Line cache; default output is unchanged (structural digests).
- [command_line_spec.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/src/sase/completion/command_line_spec.py) (new) — subprocess-built (`spec -d -j -o`), identity+fingerprint-keyed cache with atomic rename, stale pruning, worker-thread-safe locking, and timing log.
- [test_spec_contract.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/tests/completion/test_spec_contract.py) (new, 12 tests) plus regenerated `cli_spec.json` snapshot.

Verification observed: 12/12 new tests pass; 45/45 across spec-contract/snapshot/model/build; ruff and mypy clean. Full `tests/completion/` run: 287 passed with 1 failure in `test_bead_candidates_without_a_store_returns_empty_list`, which is environmental (the test doesn't isolate the bead store, so it sees this workspace's real beads) and untouched by this change. `sase tool run check` is red only on a pre-existing symvision `_failure_count` private-import flag in two untouched files. `sase bead epic-symbols` showed no leftovers.
