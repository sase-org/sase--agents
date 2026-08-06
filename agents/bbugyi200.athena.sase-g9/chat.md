# Chat History - ace-run (sase-g9)

- **TIMESTAMP:** 2026-08-06 16:31:59 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-g9

## Prompt

#gh:gh_sase-org__sase #commit
%id(sase-g9, bead=sase-g9)
%m:@medium_phase_worker
Can you complete the work for task bead sase-g9? The bead is already reserved for you and assigned to your
agent name: it was set to status=in_progress by the launch that started you; do not set the status by hand. Run
`sase bead show sase-g9`, read the description and notes, do the work, and close the bead with
`sase bead close sase-g9 --note "<what you verified>"`. If you discover genuinely distinct follow-up work,
do not expand this bead's scope: use `/sase_new_task` to check duplicates and active epics, then record it in the
location that skill selects.

## Response

I'll start by reading the bead.

Now I'll implement the breadth-aware ranking in the contexts module.

Now the breadth dataclass and measurement:

Now the cache-side functions:

Now the installer's thinness guard:

Now the install flow itself:

Now wire the guard into `_run` and add the flag:

Now tests. Let me check the fixture helper and add coverage for the new behavior:

Now let me install and run these tests:

Now the installer tests:

Now add the installer tests and fix the affected existing one:

Docs need updating to match:

Both flakes are already fixed on master (`5a1980363`, `bde727ecc`) — commits landed after my workspace's HEAD, so no bead is warranted. Let me check the running verification:

I'll wait for the check to finish rather than poll.

The check is still running. Let me wait for the notification.

I'll pause and let the background check complete — the notification will arrive.

Green. Closing the bead:

Done. `sase-g9` is closed.

**What changed**

`tests/_test_selection_contexts.py`
- New `BaselineBreadth` (contexts, attribution pairs, measured files, plus a `density` = pairs/file property) and `measure_breadth()`, which counts `context` / `line_bits` / `file` straight from SQLite over a read-only URI — ~17ms on the 49 MB CI database, versus seconds through `CoverageData`.
- Breadth is memoized in a `<sha>.sqlite.breadth.json` sidecar keyed on the database's size and `mtime_ns`, so a SHA re-recorded by `just test-contexts` is measured again rather than read through stale numbers. `prune_baselines` now removes the sidecar with its database.
- `resolve_baseline` ranks ancestors of `HEAD` by commit distance, then takes the nearest one holding at least 75% of the best candidate's attribution pairs. Unreadable databases count as zero and never displace a readable one; when nothing is measurable the ordering degrades to plain distance. Its docstring now matches what it does.

`tools/install_coverage_contexts` — third guard refusing a database whose density is under half that of the densest already cached (`--allow-thin` overrides; never fires with no measurable reference). `tools/fetch_coverage_contexts` writes the sidecar at fetch time.

**Verified on athena's real cache** at HEAD `5da193482`: `6b0976bcb` measures 46,364 pairs over 2,643 files (density 17.5, distance 28) and `96183d71b` 597,959 over 2,638 (density 226.7, distance 43). `resolve_baseline` now returns `96183d71b` — the CI artifact with 13× the attribution — where it previously returned the newer, nearer, thin local one. I left the thin database in place: it is correctly deprioritized now, and the installer would refuse to re-cache one like it (8% of the floor).

12 new tests; `docs/development.md` updated. `just check` passed clean (exit 0 — the `selection-tooling` rule escalated it to the full 26,054-test suite), plus bare mypy over 2,762 files.

Two tests flaked in earlier runs of this verification (`test_concurrent_bead_mutations_wait_past_the_old_lock_timeout`, `test_bulk_waiting_agents_mount_forced_artifact_prompts`), both passing in isolation. I did not file beads: both were fixed on master in `5a1980363` and `bde727ecc`, which land after this workspace's HEAD. The final green run confirms it. No commit was created.

Close is published. Now committing.

Committed and pushed; working tree clean, branch level with `origin/master`.

**Bead sase-g9** — closed (`done`) and published; the close note records the verification.

**What shipped**

- `tests/_test_selection_contexts.py` — new `BaselineBreadth` (contexts, attribution pairs, files, `density`) and `measure_breadth()`, counting `context`/`line_bits`/`file` directly over SQLite through a read-only URI (~17ms on the 49 MB CI database vs. seconds through `CoverageData`). Results memoize into a `<sha>.sqlite.breadth.json` sidecar keyed on size + `mtime_ns`, so a re-recorded SHA is re-measured rather than read stale; `prune_baselines` removes the sidecar with its database. `resolve_baseline` now ranks ancestors of HEAD by commit distance and takes the nearest holding ≥75% of the best candidate's attribution pairs — unreadable databases count as zero and never displace a readable one, and ordering degrades to plain distance when nothing is measurable.
- `tools/install_coverage_contexts` — third guard refusing a database under half the densest cached one's density (`--allow-thin` overrides; inert with no measurable reference). `tools/fetch_coverage_contexts` writes the sidecar at fetch time.
- 12 new tests; `docs/development.md` updated.

**Verified** on athena's real cache: `resolve_baseline` now returns `96183d71b` (597,959 pairs) instead of the newer but thin local `6b0976bcb` (46,364). `just check` passed clean — the `selection-tooling` rule escalated it to the full 26,054-test suite.

One caveat from the commit output: the primary commit and push succeeded, but prompt-archive/agent-hood publication was deferred because the agents sync lock was busy. It is queued and retries automatically — nothing in the code change is affected.
