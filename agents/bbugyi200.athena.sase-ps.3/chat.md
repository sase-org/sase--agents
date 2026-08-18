# Chat History - ace-run (sase-ps.3)

- **TIMESTAMP:** 2026-08-18 12:05:53 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-ps.3

## Prompt

#gh:gh_sase-org__sase
%id(3, clan=sase-ps, bead=sase-ps.3)
%model:@medium
%auto
%w:sase-ps.1
%w(bead=sase-ps.1)
Can you complete the work for bead sase-ps.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-ps.3 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-ps.3`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-ps.3 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead, the beads memory, and the related skills so I can implement `sase-ps.3` without changing its status by hand.

The phase is Rust-core parity for historical runner occupancy. Next I’ll read the plan and the repo skill, then open `sase-core` through `/sase_repo` before changing anything.

Phase 1 already split occupancy from admission in Python. I’ll open `sase-core` and read that implementation so the Rust stats path can match it.

The Python occupancy API is clear. Next I’ll read the Rust eligibility and stats builders, plus how this repo pins `sase_core_rs`.

Dev installs already build `sase_core_rs` from the local checkout. I’ll inspect the wire types, occupancy tests, and how previous core changes were landed so the Rust split matches that workflow.

I have the occupancy split and interval-merge design. Next I’ll implement it in `sase-core`, then add the Python parity check.

Next I’ll switch the stats builder onto family occupancy intervals and update the run-stats call sites.

The merge itself is correct; the test filter was too loose. I’ll tighten that assertion and run the rest of the occupancy tests.

Clippy is right that the snapshot helpers are only used in tests. I’ll expose the admission and occupancy predicates as public crate API so they stay part of the shared rule.

sase-core tests passed. Next I’ll rebuild the local binding and run the Python parity tests.

`just check` passed after escalating to the full suite. I’ll run the extra `check-full` gates, then close the bead.

Verification passed. I’ll record the phase notes and close `sase-ps.3`.

Closed **sase-ps.3**. Historical Statistics runner occupancy now uses the same per-family rule as live admission.

**What changed in sase-core**
- `is_runner_eligible_record` is admission-only (roots and parallel members).
- Occupancy is a separate grouping: `is_runner_occupancy_record`, `runner_slot_family_key`, `running_agent_slot_count`.
- Serial family shells (including monitors and post-handoff follow-ups) merge into one occupancy interval. Overlapping in-process handoffs do not double-count. A gap between a starter’s exit and its monitor’s start stays occupied.
- Parallel family members still each hold their own slot.
- Snapshot unit tests match the Python table from the `count` phase.

**What changed here**
- `just install` rebuilt `sase_core_rs` from the local sase-core checkout (0.28.0). The published pin in `pyproject.toml` is unchanged; release-plz / the release-branch reconciler owns that ratchet.
- Added `tests/stats/test_runner_occupancy_parity.py`: a synthetic artifact index produces the same peak and `runner_seconds` through `query_run_stats` as `running_agent_slot_count` does for the same records.

**Verified**
- sase-core `just check` (fmt, clippy, full workspace tests)
- 6 Python parity tests
- sase `just check` (lint gates + scoped tests, which escalated to the full suite because the extension identity changed)
- `sase bead epic-symbols sase-ps.3`: no leftovers

Historical Statistics numbers for windows before this change now read **higher**. That is the correction: the analyzer recomputes from stored artifacts, and the old series under-counted serial children, monitors, and post-handoff follow-ups.

The parent epic `sase-ps` was not closed. Land agent should pick up: **PROPOSED FOLLOW-UP** to commit the occupancy split on sase-core master so release-plz can publish the wheel. Those files are still uncommitted in the linked sase-core checkout.

I'll close `sase-ps.3` as required, then commit the workspace and `sase-core` changes. Reading the commit skill and checking both repos first.

Checking bead status and both repos' diffs so I can close `sase-ps.3` and commit the right changes.

The bead is already closed with no leftover epic symbols. Next I’ll open `sase-core` and inspect both repos before closing again and committing.

That status was the main workspace. I'll inspect the linked `sase-core` checkout next.

Reviewing both diffs so the commit messages match the occupancy work, then closing the bead.

The close command is still running. I’ll wait for it to finish before committing.

Close succeeded (already closed, note recorded). Next I’ll inspect the occupancy diffs and commit both repositories.

Writing commit messages and committing `sase-core` first, then the workspace parity test.

sase-core is clean and pushed. Next I’ll commit the workspace parity test.

Closed **sase-ps.3** (already done; close was a no-op plus a verification note) and committed both dirty trees.

**sase-core** (`769b9bc` on master): `fix(agent_stats): count family shells in historical runner occupancy`  
Admission stays on `is_runner_eligible_record`. Occupancy uses `is_runner_occupancy_record`, family keys, and interval merge so serial shells (monitors and post-handoff follow-ups) share one slot and parallel members do not.

**sase** (`746c80705` on master): `test(stats): assert Rust historical occupancy matches Python slot count`  
Adds `tests/stats/test_runner_occupancy_parity.py`.

Both checkouts are clean and even with `origin/master`. No leftover `--epic-symbol` entries. The parent epic `sase-ps` was not closed.
