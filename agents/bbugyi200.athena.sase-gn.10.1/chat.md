# Chat History - ace-run (sase-gn.10.1)

- **TIMESTAMP:** 2026-08-07 00:42:54 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-gn.10.1

## Prompt

#gh:gh_sase-org__sase
%id(sase-gn.10.1, bead=sase-gn.10.1)
%clan(sase-gn.10, tribe=epic, summary_script=sase_clan_summary_epic)
%model:@medium_phase_worker
%auto
Can you complete the work for bead sase-gn.10.1? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close the bead with
`sase bead close sase-gn.10.1 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself: record discovered
follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-gn.10.1 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead.

My phase is entirely in the sibling Rust core repo. Let me open it properly.

Now the reducer in events.rs.

Now let me make the edits. First, the durability ordering guard and `close_one`:

Now the shared helper in `events.rs`, next to `archive_close_metadata`:

Now the three reducer arms:

Now route the existing `snooze = None` sites in the reducer through the chokepoint:

Now the mutation side. `close_one`, `open_issue`, `claim_for_agent_launch`, and the preclaim paths:

Now route the remaining mutation-side `snooze = None` sites through the helper and fix imports:

Now delete the dead `wake_due_task_snoozes` selector:

Now the Python binding:

Builds clean. Now let me add the tests the plan requires. Let me look at the existing test helpers:

Now let me write the tests:

All new tests pass. Now the full gate suite:

All Rust gates green. Now let me verify the plan's actual reproduction against the built binding:

The plan's exact reproduction now closes cleanly and the store stays readable. Let me clean up and check the repo state:

The phase's implementation is complete and all crate gates are green. Now committing to the core repo:

The commit hook closed the bead with no note. Let me check on the release, then record both:

Release-plz is running on my commit. Let me wait for it to cut the release so I can record the exact version for the next phase.

release-plz opened PR #91 cutting **v0.19.0**. Let me record the verification note:

Phase **snooze-close-core** (sase-gn.10.1) is done and closed. The bead was closed by the `sase commit` hook when the fix landed; I added the verification and handoff notes.

## What changed, in `sase-core` (commit `0c3e287`, pushed to master)

**The corruption.** Added `clear_snooze_record` in `events.rs` as the mirror of `archive_close_metadata` — one chokepoint for leaving `snoozed`, matching the existing precedent and its comment. It's called from every transition out of that status on *both* projections: `close_one`, `open_issue`, `reopen_closed_ancestors`, `claim_for_agent_launch`, both `preclaim_epic_work_plan` sites, and the matching `IssueClosed` / `IssueOpened` / `EpicWorkPreclaimed` reducer arms. The existing `snooze = None` sites were routed through it too, so the mutation and the reducer can't drift again — that drift is the invariant that broke.

**The durability ordering.** `MutableStore::save` now validates every derived issue before `write_event_store`. This is what made the defect unrecoverable rather than merely wrong; the next mismatch of this class is a clean rejection with nothing on disk.

**The dead selector.** Removed `wake_due_task_snoozes`, its two wire types, both re-export sites, its crate test, and the `bead_wake_due_snoozes` binding with its module-doc line, registration, and both inventory-test entries. No references remain.

## Verification

The plan's exact reproduction now closes cleanly against a release build of the binding, and `bead_list` reloads the closed bead with `snooze=None` both in-process and cold from disk. Five new crate tests cover the close, the reducer parity, recovery of a store poisoned with raw `task_snoozed` + `issue_closed` events (built without calling the fixed close, so it stays a real recovery test), the ordering guard leaving streams byte-identical, and reopen/launch-claim from `snoozed`.

Gates green in `sase-core`: `cargo fmt --all --check`, `cargo clippy --workspace --all-targets -- -D warnings`, `cargo test --workspace` (1270 lib tests + all integration suites, 0 failed). No files changed in the sase repo, so `just check` doesn't apply.

## One thing for the next phase

The `BREAKING CHANGE` footer (the removed selector) bumped the minor, so release-plz opened PR **#91 — `chore: release v0.19.0`**. **That release is not published yet** — the PR must merge before sase-gn.10.2 can pin it, and the pin should then be `>=0.19.0,<0.20.0`, not the `>=0.18.5` the current version suggests. I left this as a `PROPOSED FOLLOW-UP:` note rather than merging the release PR myself, since publishing a release is the owner's call and outside this phase's scope.
