# Chat History - ace-run (1gt.w0--plan)

- **TIMESTAMP:** 2026-11-26 16:00:09 EST
- **MODEL:** claude/opus
- **AGENT:** 1gt.w0--plan
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261126_142623.md`

**Plan:** /home/bryan/.sase/plans/202611/master_gate_shard4_flakes.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/master_gate_shard4_flakes.md`

> # Green the Master Gate shard-4 red: self-diagnosing bead writers and hermetic real-startup update checks
> Governing decisions: `decisions:ci-two-speed-split` (Master Gate is the per-SHA fast
> gate this fixes), `decisions:check-full-is-explicit` and `decisions:guarded-recipes`
> (verify with `sase tool run check`, never `just check-full`).
> ## Evidence
> `actstat` shows one red sase workflow: Master Gate #3802 (run 45886580131) on master
> `ebe2eb17c4`. Only job `test (4)` failed, on
> `tests/test_bead/test_beads_db_single_owner.py::test_coordinated_writers_keep_unique_child_ids`.
> It raised `_queue.Empty` at line 332 after 120.47s. The same test, with the same
> signature, turned Master Gate 45843695662 red on `e251ae713d` (job 139991960239). Epic

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase GitHub Actions is failing for the sase repo. Can you run the `actstat` command to get more information about
the failing jobs, diagnose the root cause of these failures, and then fix them? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:@xlarge %w:1gt

## Response

I'll start by running `actstat` to see which jobs are failing.

The sase failure is in `Master Gate #3802`, shard `test (4)`. Let me pull that job's log.

Master Gate has failed repeatedly over the past day. I'll check whether the earlier failures hit the same test or different ones.

The fast lane runs through `tools/run_pytest`. I'll look at how it configures the environment and whether a startup hook reaches spawned interpreters.

There is a shared test gate (`SASE_TEST_GATE_DISABLED`, "shared token"). I'll check whether it can block spawned child interpreters.

The pane test uses `startup_policy="real"`, so real background workers run. Next I'll find what `AcePage` teardown waits on and where any ~120s timeout lives.

No 120s constant in the harness, so the stall probably isn't a fixed timeout in the TUI code. I'll check what a fresh spawned interpreter has to import to reach `ready_queue.put`.

Let me check whether a bead already tracks this flake, and time the test locally.

A plausible lead: `src/sase/sdd/_git_config.py` has `DEFAULT_NETWORK_GIT_TIMEOUT_SECONDS = 120.0`. I'll trace whether real artifacts discovery reaches network git calls.

Rather than keep guessing at a machine-wide stall, I'll measure what a spawned child actually imports, and whether anything in that path can block on shared state.

Import is fast (about 0.2s), so a healthy child should reach `ready` almost immediately. A crashed child usually leaves a traceback on stderr, so I'll check the full shard-4 log for one.

No timing artifacts, and the suite uses `worksteal` distribution. I'll run the three real-startup TUI tests locally to see their normal teardown cost.

Even locally, those teardowns take 3.5–4.8s, so some worker is still running when teardown begins. I'll instrument the drain to see which workers it waits on and for how long.

The drain itself takes 0.00s, so the time goes somewhere else in teardown. I'll dump all thread stacks partway through a slow teardown to see what it blocks on.

Each npm probe is capped at 5s, so one probe can't explain 120s. I'll look at the other sources `compute_update_status` gathers during this real-startup worker.

The update-check config has a `prebuild_rust` switch. A Rust build launched from a test would compete for the runner's 4 vCPUs, so I'll check what it actually does.

The prebuild only runs for an editable core install. CI uses the built wheel, so it doesn't apply. I'll check the remaining update sources (`incoming_commits` git/gh) for a ~120s bound.

Before ruling out "children crashed" completely, I need to confirm the assumption behind it: that pytest shows a spawned child's traceback for a failing test. Quick local experiment:

I need to wrap up the investigation. One last check is whether the update-status cache holds a cross-process lock while it computes. That would explain why several TUI teardowns stall together.

Before writing the plan, one more data check: does the earlier failing run also show a window where no worker made progress, like the 61s gap in the latest run?

The `sys.executable`-patching tests aren't in shard 4, which rules out spawn-executable poisoning. Next I'll look for process-killing code among the shard-4 files.

`update_toast.py` is the only ACE import site, so a single pin covers every real-startup path. Writing the plan now.

Validation needs `title` and `goal` in the frontmatter. Adding them:

The plan passes validation. Submitting it:

The proposal is staged. Finishing the turn through `/sase_final`.

I found the cause of the slow teardowns in the failing shard. I couldn't prove why the bead test's workers stall, so the plan makes that test report the cause next time instead of fixing it outright. The plan passed validation and is staged for your review. No repo files were changed.

**What `actstat` shows:** Master Gate #3802 on `ebe2eb17c4` failed in shard `test (4)` only. The test was `tests/test_bead/test_beads_db_single_owner.py::test_coordinated_writers_keep_unique_child_ids`, which raised `_queue.Empty` after waiting 120s. The same test failed the same way on `e251ae713d` earlier today, and no task bead tracks it.

**Finding 1: the bead test hides why it fails.**
- The test starts four worker processes and waits for each to report "ready". None did within 120s.
- Locally a worker gets there in about 0.3s and makes no network calls, runs no other programs, and takes no locks before reporting ready.
- The test discards every failure signal:
  - an error in a worker goes to a queue the parent never reads before giving up;
  - the parent never checks whether the workers are still alive;
  - no worker dumps its stack.
- I confirmed with a scratch test that a crashing worker's traceback would show up in pytest's output. CI shows none, so the workers hung (or were killed by a signal) rather than crashing.
- It wasn't the whole runner stalling: in the earlier failure, the other workers kept finishing tests during those 120s.
- I ruled out tests that override `sys.executable` (none are in shard 4) and the tests that send signals (they only signal their own children).

**Finding 2: real-startup TUI tests make live network calls.** This part is proven.
- Both failing runs, and neither passing run, had ~120s teardowns in shard 4. One was `test_agents_pane_mount`; in #3802 there were also two `test_artifacts_post_paint_publication` tests. Together they added about 170s to the shard.
- I reproduced the slow teardowns locally (3.5–4.8s each) and dumped thread stacks. Teardown waits on the app's automatic update check, which runs real `npm` commands and fetches from PyPI and GitHub.
- `startup_policy="fast"` turns that check off. `startup_policy="real"`, used by 13 test files, runs it for real unless the test supplies its own fake.

**The plan (single implementer, medium size):**
1. **Rewrite the bead test.** Workers become plain subprocesses that import only the bead modules. They hold at a ready/go barrier, so all four contend for the lock at once, which is a stronger test than today's. Each worker dumps its stack and exits if it stalls past 90s. The parent reports every worker's exit code and stderr instead of a bare `Empty`. All assertions and the 120s limit stay the same.
2. **Stop real-startup tests reaching the network.** When a test hasn't supplied its own fake, the update check gets an inert one. Scheduling and the worker still run for real, so the existing contract test still holds.
3. **Add regression tests** for both changes.
4. **File the shard-5 flake** `test_typed_clan_kill_after_pause_stays_cancelled` as a task bead, since nothing tracks it. The shard-1 warmup-GC flake is already tracked by `sase-1v2`, so it's out of scope.
5. **Verify** with stress runs, a deliberate stall to check the new diagnostics, teardown timings, and `sase tool run check`. Shard 4 of the next Master Gate is the real proof.

If the bead stall comes back after this, it will fail with the workers' stack traces showing where they hang.
