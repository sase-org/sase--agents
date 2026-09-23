# Chat History - ace-run (sase-16n.2)

- **TIMESTAMP:** 2026-09-22 20:00:44 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-16n.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-16n, bead=sase-16n.2)
%model:@small
%auto
Can you complete the work for bead sase-16n.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-16n.2 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-16n.2 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-16n.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-16n.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-16n.2 is done and closed.

What changed, per the phase design:

- [project_alias_records.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/src/sase/project_alias_records.py): alias map, conflict detection, and name allocation all compare case-insensitively now, and `home` is reserved. This automatically covers the `bare_git_init`, `bare_git_ref`, and `create_project_file` guards.
- [project_aliases.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/src/sase/project_aliases.py): `find_project_ref_owner` is case-insensitive; case-variants of `home` report `home` as owner while exact `home` keeps first-use auto-init behavior.
- [checks_project.py](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_34/src/sase/doctor/checks_project.py): `project.name_collisions` reports every key/name/alias conflict (disabled included, siblings excluded, `home` reserved) with concrete `sase project alias remove …` / rename next steps.
- sase-core `project_spec.rs`: collision warnings casefolded, claims on `home` flagged.
- sase-github `workspace_plugin.py`: canonical-name allocation never mints a case-variant duplicate.

Verification observed: new case-variant/home tests fail pre-fix and pass post-fix; 37 alias+doctor tests, 58 bare-git/name/display tests, 103 sase-github plugin tests, and 31 sase-core project_spec tests pass; full sase-core `check` gate green; widened `sase doctor` reports 0 collisions on this machine; diff-scoped lane 45222 passed. One real regression caught mid-work (`#git:home` auto-init) was fixed by narrowing the home reservation to case-variants. Two pre-existing failures unrelated to this phase (symvision on `_linked_repo_workspaces.py`, artifact-dir audit) reproduce on the clean tree and were recorded on the bead as `PROPOSED FOLLOW-UP` for the land agent. No `--epic-symbol` entries remain; parent epic untouched.
