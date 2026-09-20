# Chat History - ace-run (sase-13t.5)

- **TIMESTAMP:** 2026-09-20 14:20:30 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-13t.5

## Prompt

#gh:gh_sase-org__sase
%id(5, clan=sase-13t, bead=sase-13t.5)
%model:@medium
%auto
%w:sase-13t.4
%w(bead=sase-13t.4)
Can you complete the work for bead sase-13t.5? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close only this bead with
`sase bead close sase-13t.5 --note "<what you verified>"`. Before closing, run
`sase bead epic-symbols sase-13t.5`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-13t.5 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

Opened the sase-core checkout; now reading the release workflow and its git state.

Tests pass (51). Next I'll confirm the tests fail against the old push-triggered gate, then validate the YAML and update the runbook.

Bead sase-13t.5 is closed and the work is submitted for the host commit. The change is in the sase-core repo, and none of the new workflow behaviour has run on GitHub yet.

**What changed** (`.github/workflows/release-plz.yml`)
- **Daily cut:** a second cron, `41 7 * * *`, sits beside the existing `23 */6 * * *` heal cron. It is the only schedule that merges the release PR.
- **Merge gate:** `release-plz-merge` now runs only for that daily schedule or a `workflow_dispatch` with `dry_run=false`. Pushes and the six-hourly heal skip it.
- **Heal path:** `release-plz-release`, `release-plz-pr`, `publish-plan` and the build and publish jobs are unchanged, so a push still updates the release PR and a missed publish still heals.
- **Safety guards:** the checks on base branch, author, head-branch timestamp, title shape and body footer are untouched.
- **Concurrency group:** a push or heal run that skips the merge job now gets its own group, so it can't cancel an in-flight cut. I added this defensively, because I couldn't confirm from memory whether a skipped job can still cancel a running one.
- **Decision record:** the header comment now explains the cadence and the reason not to restore merge-on-push.

I also added a "Release cadence" section to `docs/pypi-retention.md` and corrected its note on the manual heal dispatch. That dispatch now also cuts a release as a side effect.

**Verification**
- `just check` passed in sase-core: fmt, clippy, cargo tests and the 51 script tests.
- The workflow YAML parses.
- The new `.github/scripts/test_release_cadence.py` has 14 tests. Six of them fail against the old workflow.

**Not verified:** GitHub Actions can't run locally. I haven't seen a push update the release PR without merging it, or the first daily cut. sase-13t.6 should confirm both after this lands.

There were no epic-symbol entries to resolve, and I recorded no follow-ups.
