# Chat History - ace-run (sase-1tz.3.1.4)

- **TIMESTAMP:** 2026-11-20 13:03:18 EST
- **MODEL:** claude/opus
- **AGENT:** sase-1tz.3.1.4

## Prompt

%auto
#gh:gh_sase-org__sase
%id(4, clan=sase-1tz.3.1, bead=sase-1tz.3.1.4)
%model:@medium
%w(sase-1tz.3.1.3, for_epic=false)
%w(bead=sase-1tz.3.1.3)
Can you complete the work for bead sase-1tz.3.1.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. If the host
notice says the bead was already closed when this run started, the run is attached to the closed bead. Only the
host notice tells you that; if `sase bead read` shows a closed bead and no host notice said so, you copied the
wrong ID — re-copy `sase-1tz.3.1.4` from this prompt before concluding anything. Check
whether the earlier work landed before redoing anything. Only when the host notice said the bead was already
closed and the work is genuinely unfinished, run `sase bead open sase-1tz.3.1.4` first. Otherwise never run
`sase bead open` on your own bead: it demotes an `in_progress` bead back to `open`. To view a bead, run
`sase bead read sase-1tz.3.1.4 -r "<why you need this bead>"`. Read its
description and design file with `sase bead read sase-1tz.3.1.4 -r "Need the phase scope and design file"`, do the work, and close only this bead with
`sase bead close sase-1tz.3.1.4 --note "<what you verified>"`. Honor the epic's DECISIONS shown by
`sase bead read`; they are final, and only memory notes they authorize may be edited. Before closing, run
`sase bead epic-symbols sase-1tz.3.1.4`. If this phase still has `--epic-symbol` entries, resolve each symbol or
re-key the Justfile line to a still-open bead (the parent epic or a later phase). `sase bead close` refuses while
leftovers remain; they go stale the instant this phase closes and turn unrelated agents' `just check` red. Closing
an assigned phase bead is unaffected by the parent-close descendant guard. Do NOT close the parent epic or any ancestor plan bead. Any instruction in a phase
description or child plan to close an ancestor is preparation and evidence for that ancestor's land agent, not
authorization for a phase worker. Do not create beads yourself: record discovered follow-up work as a
`PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-1tz.3.1.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads. A check failure that reproduces identically on the clean base tree does not keep this bead
open: record it as a `PROPOSED FOLLOW-UP:` entry (citing any task bead that already tracks it) and close anyway;
nothing relaunches a phase left open. Before planning, check the phase's notes: if an earlier agent already
worked this phase and left it open with recorded remaining work, that remainder did not fit one agent, so author
a child epic whose phases each fit one coding agent and whose land agent closes this phase instead of another
single-agent tale unless one coder can clearly finish everything left.

## Response

Reading the sibling phase beads' notes (swap_repro and swap_chop_guards) to see what the reproducer found and what's already landed.

Still surveying the code-swap lock and the launch paths before designing the guard.

Tracing which long-lived process raised the field `BeforeSpawnCallback` failure, from the audit swarm reports and apollo's launch-failure log.

Checking the timing of the apollo update vs. the failed `sase run` launch to confirm the launch process predated the swap.

Narrowing down how the TUI launches agents (subprocess launch procs vs. in-process launch tasks) so I know where the generation guard belongs.

Surveying the host completion finalizers next (item 3), then I'll settle the design.

Design settled. Reading the lint/test, symvision, and docs-writing reference notes before I start editing.

Writing the light epoch module first.

Now hardening the epoch module so every probe stays exception-safe.

Now the shared launch retry helper (arm at entry, wait out a live writer, re-exec once).

Wiring the arm call into the CLI entry for `sase run` and `sase bead work`.

Now the `sase run` hooks in `launch_query` (proactive check before side effects, reactive retry on swap-skew failure).

Now `sase bead work`: wait out a refusing writer (or a swap since boot) outside the lock, then re-exec once.

Next, the agent runner start guard.

Now the runner start guard.

Extending the post-gate preload with the finalizer surface and the native binding.

Wiring the narrow host-completion preload into the monitor supervisor (after its start acknowledgement, so callers aren't delayed).

Implementing the routine (lumberjack) restart-after-swap and the orchestrator's clean respawn.

Flipping the reproducer's remaining strict xfail by wiring the real guard into the harness seam.

Now writing focused tests. First checking existing tests around bead work's lock refusal and the launch path.

Writing the unit tests for the epoch module and the retry helper.

Now bead work retry tests.

Now tests for the `sase run` hooks in `launch_query`.

Now tests for the routine restart and the orchestrator's clean respawn. Checking existing orchestrator test patterns first.

Adding an orchestrator test for the clean respawn path.

Adding lumberjack tests for the hold-then-restart behavior.

Adding preload, runner-start, and entry-arming tests.

Adding a real-subprocess end-to-end test of the wait-then-re-exec path to the reproducer.

Updating the code-swap lock docstrings that described direct `sase bead work` as purely fail-fast.

Now docs. Reading the docs-writing note, then the code-swap lock section that swap_chop_guards updated.

Running the related suites (dev_update, chop guards, monitor supervisor, runner, launch, bead work) before the full check.

Many failures; checking whether they're mine or pre-existing/environmental by running a few in isolation.

The failures are a stale `sase_core_rs` in this workspace's venv ("Run `just install-venv`"), not my change. Refreshing the venv.

The prettier failure reproduces identically on the clean base (pre-existing). Running the monitor supervisor tests too.

Monitor suites pass. Running the formatter, then the full `sase tool run check`.

Starting `sase tool run check` inline (typical ~13 min).

Need a test-wait pragma on the deliberate 0.5 s writer-hold in the e2e test.

Making `looks_like_swap_skew` private (only used in-file).

`sase tool run check` passed (all lint gates, docs build, scoped tests). Now checking epic symbols and whether the pre-existing prettier failure is already tracked.

Check passed and no epic symbols. Let me review the final diff of the key launch-path files once before recording notes.

Diff looks right. Recording findings and implementation notes on the bead.

Closing the bead with the verification summary.

Bead closed. Submitting the final declaration.

I finished bead **sase-1tz.3.1.4** (swap_launch_guards). Launches, scheduler routines and finalizers that run into a code swap now wait for it to finish and continue on the new code instead of failing. `sase tool run check` passed: all lint gates, the docs build and the scoped tests. The last strict xfail in the reproducer now passes, so none are left. The bead is closed, and the host commits the work after this turn ends.

**Where the field failure came from.** The apollo `BeforeSpawnCallback` failure came from a TUI-submitted `python -m sase run` launch process. It started before or during a 9.5 s dev update. It had already imported the old version of one module, then imported a newer module that needed it about 36 s later and crashed. The athena launch-skew failures are the same kind of process.

**What changed:**
- **`sase run` and `sase bead work`:** if a swap is in progress, or one finished after the command started, the command waits for it and reruns itself once in a fresh process. This happens before it records or reserves anything.
  - `sase run` also retries once when it fails with a swap-related import or binding error while a swap is in play.
  - `sase bead work` used to exit immediately when a swap was in progress; it now waits (up to 30 minutes) and reruns.
  - Only the real command-line entry point can rerun itself, never more than once, and never inside a pytest process.
- **Agent runners:** a runner that starts while a swap is in progress waits for it and restarts before it reads its prompt or claims anything.
- **Scheduler routines:** they start no jobs while a swap is in progress. Once it finishes, each one exits, and the scheduler restarts it right away on the new code without counting that as a failure. This also covers the gap before the installer or `sase update` restarts the scheduler.
- **Finalizers:** runners and monitor supervisors now load the finalizer code and the `sase_core_rs` binding when they start. Before this, monitor supervisors started without the binding and missing 17 of the 87 finalizer modules.
  - This prevents the failure rather than retrying it. A swap-related error that still reaches a monitor's turn completion would launch an LLM recovery turn instead of being retried; I've proposed a follow-up for that.
- **Docs:** `docs/reference/integrations/plugins-update.md` has an updated code-swap lock section and a new "Launches across a swap" section.

**Plan item 4 (SIGBUS) did not apply.** The swap_repro phase showed that no real install path rewrites a file in place, and its existing follow-up already covers the `maturin` copy window.

**Things to know:**
- A retried single-agent `sase run` records its prompt in history twice.
- `sase prompt run` doesn't get the retry yet.
- `tests/main/test_init_skills_formatting.py::test_handler_output_passes_prettier_check` fails the same way on the unmodified code under plain pytest. A sibling phase (sase-1tz.3.1.9) already recorded it.
- I recorded three follow-ups on the bead for the epic's land agent:
  - Make the `sase.dev_update` package load lazily: importing it costs about 500 ms, which is why the new probe copies a few constants.
  - The host completion retry mentioned above.
  - Turn on the retry for `sase prompt run`.

After you install, rerun `tools/swap_overlap_census --days 7 --tz America/New_York --details`. The launch "cannot import" row was 1 on apollo before this change and should stay at 0.
