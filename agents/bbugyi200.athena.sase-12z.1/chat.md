# Chat History - ace-run (sase-12z.1)

- **TIMESTAMP:** 2026-09-18 11:47:50 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-12z.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-12z.1, bead=sase-12z.1)
%clan(sase-12z, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium
%auto
Can you complete the work for bead sase-12z.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-12z.1 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-12z.1`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-12z.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the workspace context and bead sase-12z.1 so I can complete only that phase.

The bead is a capture-protocol phase. Next I’ll read the epic plan and the current screenshot fixtures.

I’ll inspect the current visual snapshot fixtures, helpers, and research so the capture protocol can slot in without changing goldens.

I’ll inspect plugin registration, snapshot-path tests, and xdist patterns so the capture protocol can stay isolated from golden writes.

I have a clear picture of the capture protocol. Next I’ll add the isolated candidate-capture modules and wire them into the ACE and pager fixtures.

Next I’ll add focused regression tests for the capture protocol, including a small xdist project.

The workspace venv needs installing before the capture tests can import ACE fixtures. I’ll install, then run the focused tests.

Phase **sase-12z.1** (capture-protocol) is done and closed. The parent epic **sase-12z** is still open.

ACE and pager PNG fixtures can now collect a full set of screenshot **candidates** without comparing or writing goldens. Direct helper calls and temp-root unit tests still use the old compare/update path, so they cannot pollute the real corpus.

When pytest is given `--sase-visual-capture-dir` (and optional run id / `full` vs `targeted` scope):

- Each snapshot still does rendering and ACE frame-convergence checks, then writes candidate PNG/SVG plus versioned metadata into that run’s scratch directory.
- The next snapshot in the same test still runs. Ordinary assertions, teardown failures, timeouts, and convergence failures are not swallowed.
- Canonical identity is the repo-relative golden path under the ACE or pager PNG root. Artifact ids are SHA-256 based, not the old lossy slug.
- Absolute names, `..` traversal, symlink escapes, and duplicate golden ownership are rejected even when the bytes match.
- xdist workers write only into their own directories; the controller merges them. Completeness evidence (collected/executed nodes, skips/xfails, worker loss, collection-only) is stored separately from captures.
- A requested **full** run that lacks both-root execution evidence cannot prove orphans. **Targeted** runs report limited scope and disable pruning.

Verified:

- 25 focused capture tests, including a real `pytest -n 2` fixture project and golden-tree hashes unchanged after collection
- 28 existing `png_diff` helper tests
- ruff, mypy, and symvision
- No `--epic-symbol` leftovers for this phase

`just check`’s feature-flag gate still fails on closed flag bead `sase-11u` (`agent_holds`), which this phase did not touch. The scoped suite escalated because root/visual `conftest.py` changed: 42,975 passed; `tests/completion/test_snapshot.py` has two unrelated completion-spec snapshot failures, noted as a proposed follow-up on the phase bead.
