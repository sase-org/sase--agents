# Chat History - ace-run (sase-1fs.1)

- **TIMESTAMP:** 2026-10-03 15:10:13 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1fs.1

## Prompt

#gh:gh_sase-org__sase
%id(1, clan=sase-1fs, bead=sase-1fs.1)
%model:@medium
%auto
Can you complete the work for bead sase-1fs.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-1fs.1 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1fs.1 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-1fs.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1fs.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open.

## Response

Bead sase-1fs.1 is done and closed.

What landed: legacy family-only session manifests are now accepted through a new Rust core policy (`agent_session_manifest`: derives the canonical file set and classifies an explicit list as current / supported-legacy / slim / invalid), exposed via a `classify_session_manifest_files` binding and a thin Python facade. `hood_file_set()` and manifest validation delegate to it behind the sunset flag `agents_session_manifest_compat` (bead sase-1ft, default on); flag-off keeps the old strict comparison. Normal publication still writes the current format with session pages plus family redirect stubs.

Verified: 9 Rust core tests, 1 binding test, 11/11 in `tests/agents_sync/test_publication_manifest.py` (including a real legacy fixture publishing a second hood of the same owner plus a `bob.zeus` owner hood with foreign bytes byte-identical, both flag states, slim/no-session/repeat sync, and corruption negatives for digest, identity, payload, and file list), 25 adjacent publication/rendering/repair tests, 140 flag tests, ruff clean, and no `--epic-symbol` leftovers. Two check failures (mypy `checks_config_retired.py:322`, 6 symvision hits in untouched files) reproduce identically on the clean base, so I recorded both as `PROPOSED FOLLOW-UP` notes and closed anyway.

Changed repos declared to the host finalizer: `sase` (validation, facade, flag registry + schema, tests) and linked `sase-core` (new module, binding, tests) — core must land first with `sase-core-revision.txt` ratcheted past the new binding.
