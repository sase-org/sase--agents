# Chat History - ace-run (sase-1tz.3.1.2)

- **TIMESTAMP:** 2026-11-20 10:52:39 EST
- **MODEL:** claude/opus
- **AGENT:** sase-1tz.3.1.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-1tz.3.1, bead=sase-1tz.3.1.2)
%model:@medium
%auto
Can you complete the work for bead sase-1tz.3.1.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1tz.3.1.2` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything. Only when the host notice said the bead was already
closed and the work is genuinely unfinished, run `sase bead open sase-1tz.3.1.2` first. Otherwise never run
`sase bead open` on your own bead: it demotes an `in_progress` bead back to `open`. To view a bead, run
`sase bead read sase-1tz.3.1.2 -r "<why you need this bead>"`. Read its
description and design file with `sase bead read sase-1tz.3.1.2 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1tz.3.1.2 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1tz.3.1.2`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1tz.3.1.2 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

I'm reading the bead, its epic plan, and the code it touches before building the swap reproducer.

Still reading the code-swap lock and chop runner code before I write the harness.

Still surveying: checking how the test suite isolates `SASE_HOME` so the harness never touches `~/.sase`.

Next I'm checking how the real installers replace files (in place vs. rename) — read-only.

I've finished reading the code paths; now checking the dev-update reconcile steps, then I'll write the harness.

Found evidence maturin removes the old module before copying; confirming that, then measuring a real `uv tool install` in a temp dir.

Measured: uv and git both replace files with new inodes, never in place. Checking sase-core for mmap usage (a candidate SIGBUS source).

Writing the harness now. First checking the repo's "test waits" lint so the harness's handshake polling complies.

The `test waits` lint wants deadline-clamped polls, so the harness will use those. Now finding where chop runs, the error ring, and update/install records live on disk, for the host measurement.

Checking the on-disk run records on athena (read-only) so the census matches their real shape.

Run history keeps only 40 runs per job, so I'll also need the scheduler logs. Checking the audit's F7 method first.

Mapping the scheduler log format for failed jobs before I write the read-only census.

Writing the harness now. Checking how `tests/dev_update` helper modules are imported first.

Writing the harness module.

Now the chop-scenario tests. Checking one preflight detail (scheduled vs. manual source) first.

Harness looks right. Writing the job-scenario tests.

5 pass, 5 strict xfails. Confirming each xfail fails for the intended reason, not a harness accident.

All five xfails fail for the intended reason (`success`, `missing_script`, exit 1 ×2, exit -7). Fixing a possibly-unbound variable, then writing the import and native-code scenario files.

16 pass, 6 strict xfails, including the partial-copy SIGBUS model. Checking the import xfail's failure reason, then running under parallel workers.

Reproducer is green in parallel too. Now the read-only host census for item 6 — inspecting the remaining record formats.

Found it: error digests are the durable error record. Looking at one entry's full shape.

The Nov 18 SIGBUS pair died 0.45 s after starting, with no output. Lining that up against the dev update's own step timeline.

Athena: 6 overlap failures in 7 days, all within 120 s of an update. Adding during/after/before-window classification (this tells which guard covers each event), then measuring apollo.

All 6 athena events fall inside an update window. Running the same read-only census on apollo over SSH.

Both hosts measured. Now checking which dev-update step was running at each SIGBUS, on both hosts (read-only, ad hoc).

Running the formatter and fixers before the full check.

Existing extensionless tools aren't format-enforced, but I'll apply ruff's formatting to mine anyway, then run the full check.

Now the full verification run (`sase tool run check`), inline with a long timeout.

The only failure is `lint (pyscripts)`: every tool must be referenced somewhere in the repo. Checking what counts as a reference.

`git grep` only sees tracked files, so the reference has to live in an already-tracked file. Looking for the docs page that covers the code-swap lock.

Per the routing table, a measurement runbook belongs under `docs/contribute/`. Finding the right page there.

Adding a short runbook subsection to `docs/contribute/development.md`, next to the install-mode section it relates to.

Rerunning the full check.

Both pass in isolation. Checking the failure output to rule out any link to my tests (for example a leaked thread or child process).

No epic symbols for this phase. Confirming from the run record that every lint stage passed on the second run.

Lint stages all passed; only the two tracked flakes failed. Checking whether the two missing-script events predate the existing deferral commit `ea7916d7a7`, which affects how I describe coverage.

Both missing-script events predate `ea7916d7a7` (Nov 17 08:10), so the existing deferral already covers that mode. Writing the bead notes now.

Verifying the notes were stored as text rather than file attachments.

Notes stored as text. Adding the follow-up notes and the one-line summary on sase-1tz.3.

Cleaning up my temp experiment dirs, then a final quick re-verification of the touched files.

Everything is verified. Closing this phase bead.

I've finished and closed sase-1tz.3.1.2: the update-overlap reproducer is built, and the host will commit it after this turn. Its tests give 16 passes and 6 strict xfails, each confirmed to fail for its intended reason.

**What it shows today**
- **Already handled:** a job script that vanishes while an update holds the lock is retried later (covered since `ea7916d7a7`). Host-owned epic launches already wait out an update and pick up the reinstalled binding.
- **Still failing, for `swap_chop_guards` to fix:**
  - A job starts and runs while an update is in progress.
  - A script still missing just after the update finishes is reported as a "missing script" error.
  - A job that loses `sase_core_rs` mid-run fails, both when the update is still running at exit and when it has just finished.
  - A job killed by SIGBUS during an update is recorded as a failure.
- **Still failing, for `swap_launch_guards` to fix:** a long-running process that loaded the old types module and later imports the new executor fails with `cannot import name 'BeforeSpawnCallback'`. Replacing files atomically doesn't prevent this. Importing the executor at startup or restarting after the update both avoid it. That phase still has to plug its guard into the test (`LONG_LIVED_SWAP_GUARD`) and remove the xfail.

**How the real installers replace files:** none of them rewrites a file in place.
- `uv tool install --force --reinstall` (`just install`, `just install-dev`) deletes and recreates the whole tool environment. In a temp-dir test, scripts were missing for about 0.46 s.
- `maturin develop` deletes the old extension, then copies the new one. On both hosts, long-running processes still map older, now-deleted copies of the extension, which confirms nothing is overwritten in place.
- The prebuilt-artifact install and the git fast-forward also create new files rather than editing old ones.

**Before-numbers (read-only, last 7 days):** every overlap failure on both hosts happened within 120 s of an update.
- **athena:** 6 of 6. All happened while an update was running: 3 SIGBUS, 2 missing scripts, 1 missing binding.
- **apollo:** 4 of 4: 3 SIGBUS, plus the `BeforeSpawnCallback` launch failure 36 s after an update.
- **All 6 SIGBUS exits** started during the update's Rust rebuild step (`maturin develop`). The likely cause is a job importing `sase_core_rs` while the 60 MB file is half-copied. `swap_chop_guards`' "no starts during an update" rule would have prevented all of them. Nothing here calls for versioned runtime instances.

To re-measure after the next install, run `tools/swap_overlap_census --days 7 --tz America/New_York --details` on athena, and `ssh apollo 'python3 - --days 7 --tz America/New_York --details' < tools/swap_overlap_census` for apollo. I added that read-only tool and a short paragraph about it in `docs/contribute/development.md`. The full findings and numbers are notes on the bead, with a one-line summary on sase-1tz.3.

**Checks:** `sase tool run check` passed every lint and format step. The test step ran the full suite: 62,291 passed and 2 failed. Both failures are in code I didn't touch, pass when run alone, and are already tracked as sase-1q8 and sase-t6.

**Proposed follow-ups on the bead:**
- Make the `rust-dev-install*` recipes install the extension by writing a temp file and renaming it, so nothing can load a half-copied file.
- Fix `docs/reference/integrations/plugins-update.md`, which names the lock file `code-swap.lock`; the code uses `code-swap-v2.lock`.
