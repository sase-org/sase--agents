# Chat History - ace-run (sase-16e.1)

- **TIMESTAMP:** 2026-09-22 14:48:04 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** sase-16e.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-16e.1, bead=sase-16e.1)
%clan(sase-16e, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium
%auto
Can you complete the work for bead sase-16e.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file with `sase bead read sase-16e.1 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-16e.1 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-16e.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-16e.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Bead sase-16e.1 is done and closed.

**What landed (rescue-store phase):**
- New `src/sase/workspace_provider/rescue.py`: durable rescue store outside the workspace (`~/.sase/projects/<key>/rescue/<YYYYMM>/`, `~/.sase/rescue/` fallback) writing git bundles (all branches, tags, recovery refs, detached HEAD, every stash entry; `--not --remotes`), binary worktree patches via a temp index (64 MiB cap), and `manifest.json` with restore commands. Retention 30d (7d for quarantines), one `workspace-rescue` notification per rescue, best-effort throughout.
- Launch eviction no longer refuses: `prepare_launch_workspace_repos` publishes once per sidecar (30s lock wait, memoized by repo+HEAD so the tolerant and eviction passes never double-publish), rescues, and always proceeds. `_WorkspaceBeadEvictionRefused` deleted, `refuse_on_unpublished` replaced with `evicting`, generic sidecar pass skips every bead-handled root, unknown counts rescue instead of passing silently, damaged clones quarantine to the durable store.
- Docs updated (`workspace.md`, `beads.md`, `sdd_storage.md`) with restore procedure.

**Verification:** 31 focused tests pass (9 new rescue + 18 eviction incl. publish-once incident regression + 4 auto-connect), 4 prepare-regression tests pass, all lint gates pass (ruff, mypy, symvision, fmt). Final `just check`: 7281 passed, 4 failed — all 4 reproduced failing on pristine master (3 `test_commit_bead_hooks` `env=None` mock mismatches, 1 free-text classification gap), recorded as `PROPOSED FOLLOW-UP` notes on the bead for the land agent. No `--epic-symbol` entries remain; only this bead was closed.
