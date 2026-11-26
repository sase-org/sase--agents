# Chat History - ace-run (sase-1vc.1)

- **TIMESTAMP:** 2026-11-26 08:12:31 EST
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-1vc.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-1vc.1, bead=sase-1vc.1)
%clan(sase-1vc, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium
%auto
Can you complete the work for bead sase-1vc.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1vc.1` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything. Only when the host notice said the bead was already
closed and the work is genuinely unfinished, run `sase bead open sase-1vc.1` first. Otherwise never run
`sase bead open` on your own bead: it demotes an `in_progress` bead back to `open`. To view a bead, run
`sase bead read sase-1vc.1 -r "<why you need this bead>"`. Read its
description and design file with `sase bead read sase-1vc.1 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1vc.1 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1vc.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1vc.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Done. Bead `sase-1vc.1` (release_evidence_project) is complete and closed, with the final declaration accepted.

What changed: commit publication now resolves one host project key per commit via `_resolve_commit_publication_project_key` (repo inventory, then workspace marker, then the checkpoint's project file) and uses it for release evidence, the publication enqueue (`project=`), and the publisher hint, with an assertion that evidence and queue keys match. Unmappable repos skip with a warning instead of failing the landed commit, and the inline outbox drain uses the same resolver against the machine store. Added `publication_project_key_for_path` (public, in `sase.agents_sync.commit_publication`) and made `project_from_project_file` public (renamed from private per symvision).

Verification: 20/20 in `tests/test_commit_workflow_publication_step.py` (7 new regression tests), 11/11 in the sibling publication modules, 95 passed in the wider publication/artifact-link lane, and `sase tool run check` succeeded (STATE succeeded, EXIT 0), including symvision and mypy.
