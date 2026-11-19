# Chat History - ace-run (sase-1tz.2.1.11)

- **TIMESTAMP:** 2026-11-19 14:56:22 EST
- **MODEL:** claude/opus
- **AGENT:** sase-1tz.2.1.11

## Prompt

%id(11, clan=sase-1tz.2.1, bead=sase-1tz.2.1.11)
#gh:gh_sase-org__sase
%m:@xlarge 
%auto
Can you complete the work for bead sase-1tz.2.1.11? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1tz.2.1.11` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything. Only when the host notice said the bead was already
closed and the work is genuinely unfinished, run `sase bead open sase-1tz.2.1.11` first. Otherwise never run
`sase bead open` on your own bead: it demotes an `in_progress` bead back to `open`. To view a bead, run
`sase bead read sase-1tz.2.1.11 -r "<why you need this bead>"`. Read its
description and design file with `sase bead read sase-1tz.2.1.11 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1tz.2.1.11 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1tz.2.1.11`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1tz.2.1.11 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Reading the bead history to see if an earlier run left notes, then I'll look at the three target code paths.

Still surveying: now reading the change-token peek and the launchable-MRU build to design the off-thread move.

Now reading the hijack roster/decision-cache code (item 2).

Reading the existing hijack-parity tests and then item 3 (project alias map / display cache).

Now item 3: the project alias map and display cache.

Apollo is reachable. Analyzing its stall rows (read-only) to confirm the hot callers before changing code.

Design settled. Now checking the TUI entry so the alias-map cache opts in only for the real TUI process (not CLI or tests).

Starting edits. Item 2 first: defer the hijack roster's per-row path resolution to the single-flight worker.

Now item 1: move the launchable-MRU tick's token peek into a pump-free task.

Updating the module's state init, type hints, and docs to match.

Item 3 next: the tick-managed alias-map cache in `_project_display_cache.py`.

Wiring the alias-map cache into `project_aliases.py` and the display-names facade.

Now the opt-in at the real TUI entry point.

Code changes are in. Now tests; first finding how existing tests build ProjectSpec fixtures for alias maps.

Writing the shared main-thread filesystem guard helper and the alias-map cache tests.

All 9 pass. Adding a negative control so the guard is proven to catch the uncached path.

Now the launchable-MRU tests: update the drift test for the async peek and add off-main-thread and single-flight tests.

Pre-existing warning (same on base). Negative control: run the new MRU tests against the old tick code.

Fails on old code as expected. Now the hijack roster test.

Passes with the fix, fails on the old code. Fixing the Pyright complaint in the test.

Base tree fails identically: the workspace's `sase_core_rs` wheel is stale. Refreshing the venv before verification.

148 pass. Adding a test that `_run_ace_app` scopes the opt-in to the app's lifetime.

I'll document the new structural gates in the perf runbook; reading the docs-writing note first.

Now formatting/lint fixes, then the j/k bench and `just check`.

My new test tripped the test-waits lint. Checking the sanctioned wait helper.

Tests pass; checking whether the remaining direct-mypy errors are mine or pre-existing (the repo gate's mypy already passed).

Those are all in pre-existing lines, not mine. Re-running `just check`.

Lint is clean now; the full test lane ran (62,160 passed). Investigating the 2 failures triage marked NEW.

The bare-git test passes in isolation (load flake). The audit failure names `agents_sync/publication_scratch.py`, which I didn't touch; confirming it reproduces on the clean base.

The stash hit an index-write error. Checking the working tree state carefully before anything else.

My changes are intact (the stash never happened; no new stash entry). A 0-byte `.git/index.lock` was left behind. Checking whether anything holds it and whether the disk is full.

The lock dates from 13:46 (mid-`just check`, ~40 min before my stash), no process holds it, and no git process is running; it's stale and would block the host's commit. Removing it.

Lock cleared. Backing up my changed files before retrying the base-tree check via stash.

9 of 19 bench nodes failed. Collecting each failure's reason, then I'll compare against the clean base.

Host load is high (load avg 33–52), which these stall-sensitive benches react to. Running the 9 failing nodes on the clean base for attribution.

Tree is now at the clean base. Running the failing bench nodes.

Base fails 7 of the 9 under the same load (budget/stall assertions). Restoring my changes and rerunning the same subset on my tree for a direct comparison.

It doesn't break stalls down by frame, so I'll record a self-contained snippet. Verifying it reproduces the before-numbers, then checking how to attach it to the bead.

Snippet reproduces the before-numbers exactly. The landing step expects measuring phases to record numbers on **sase-1tz.2**, so I'm checking how sibling phases formatted theirs.

No code changed since the second `just check` (the base-comparison round-trip restored an identical patch). Confirming the untracked test files also match the backup byte for byte.

All identical. Final self-review of the source diff.

`sase-1s4` already tracks the stale-lock problem, so I'll cite it. Recording the measurement (with the after-install script attached) on sase-1tz.2.

Now the PROPOSED FOLLOW-UP notes on my bead.

No epic-symbol leftovers. Closing the phase bead with the verification summary.

Closed. Submitting the final declaration.

I finished sase-1tz.2.1.11 and closed it. All three pieces of file-system work the plan named now run off the TUI's main thread. In the full `just check` run every lint gate passed and 62,160 tests passed. The 5 that failed trace to existing problems or flakes, not this change (details below). The host commits the work when this turn ends.

**What changed**
- **Project-change check (every 2 s):** the timer now only starts the check, and the file check plus config read run in a background task. Only one check runs at a time; ticks that land while one is running are skipped.
- **Hijack footer and leader mode:** building the hijack inputs now only copies row fields. Path resolution, which did a file check per path segment, now happens on the existing hijack worker the first time it's needed.
- **Project alias lookups:** apollo's stall stacks show the hot caller: each Agents-tab load called `get_artifacts_dir` for every agent, and each call re-read every project file. `sase tui` now opts into an in-memory alias map. The TUI's existing project-label refresh rebuilds it when a project file changes, and in-process project or alias edits drop it. Command-line runs still read fresh on every call.
  - Tradeoff: inside the TUI, an alias added from another process becomes visible at the next refresh (default every 10 s) rather than immediately. That's the same staleness project labels already accept under the existing "projects shown by name" decision.
- I added a short section to `docs/contribute/perf-runbook.md` describing these checks.

**Tests**
- A new helper, `tests/_main_thread_fs_guard.py`, records any `stat`, `lstat`, `scandir` or `Path.resolve` call made on the main thread.
- New and updated tests use it for all three paths. The guard tests fail against the old code, and one test checks that the guard catches the old uncached lookup.
- Of the 5 failures in the full run:
  - 3 were already flagged as known failures.
  - `test_artifact_directory_operation_sites_are_reviewed` fails the same way on the clean base. It flags `agents_sync/publication_scratch.py`, which an earlier commit added.
  - `test_git_runner_removes_persistent_index_lock_after_retries` passes when run alone.
- The j/k benches fail 9 of 19 under heavy host load (load average 33–48). Rerunning the failing nodes on the clean base failed 7 of 9 for the same budget and stall reasons. The one extra node on my tree, archive warm-open, scored 99.4 ms then 115.6 ms against a 100 ms budget with identical code, so it's noise.

**Apollo before-numbers** (recorded on sase-1tz.2 with the after-install script attached): of 1,717 recovered stalls, 1,255 had under 1 s of garbage-collection overlap, max 116.8 s.

| Target | Stalls | Max |
|---|---|---|
| Project-change check | 2 | 115.8 s |
| Hijack path resolution | 117 | 9.9 s |
| Alias map loading | 144 | 11.1 s |

The after-install goal is zero stalls for all three after the install time. The attached script is stored on athena only.

**One thing to know:** twice during this run, a test run left an empty `.git/index.lock` in the checkout, which made `git stash` fail. No process held it either time, so I deleted it by hand. While the lock was in place, a `git stash pop` I ran without checking first tried to pop an old, unrelated stash. It failed on the same lock, so nothing was applied, and I confirmed my diff was byte-identical afterward. I added the timestamps as evidence for the existing task sase-1s4.

**Follow-ups recorded on the bead**
- The Agents-tab load still checks each live agent's artifact path on the main thread, even with the alias part fixed.
- `LaunchContextSource._tick` still runs its own checks on the main thread, including the temporary-override read behind a 71.7 s stall on apollo.
- The Tools pane resolves the current project on the main thread when it opens.
- The artifact-directory audit failure needs the land agent to add `publication_scratch.py` to the reviewed sites.
