# Chat History - ace-run (1fd--plan)

- **TIMESTAMP:** 2026-11-22 19:05:23 EST
- **MODEL:** claude/opus
- **AGENT:** 1fd--plan

**Plan:** /home/bryan/.sase/plans/202611/fix_master_gate_deterministic_failures.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/fix_master_gate_deterministic_failures.md`

> # Turn Master Gate green: fix the five deterministic failures on master
> ## Context
> Master Gate (`.github/workflows/master-gate.yml`, 8 test shards) has failed on all of
> the last 300 master pushes. The failure notification behind this task is run 45076753261
> on `bcaa3a8c0e`. The same failures persist through the latest run, 45081096230, on HEAD
> `1b9e88513b`. Across 16 recent runs, five failures recur on every run, and each has a
> known, precise root cause. All five reproduce locally on HEAD with direct `pytest`.
> Fixing them should leave only the known intermittent flakes listed under "Out of scope".
> The five failures and their causes:
> 1. **Collection ImportError, plus a downstream contract-manifest failure.**

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase Is this something we can/should fix? If so, use your /sase_plan skill to plan the appropriate changes. See the ^fix-failed-ci task in
the ~/bob/sase.md file for context. %m:@xlarge

## Response

Investigating the failed Master Gate run on bcaa3a8: five separate failures across seven shards. I'm checking each against current master now.

Two deterministic fixes found so far: a stale re-export facade and a stale audit allowlist path. Next I'm checking the video-frame, canary, and convergence failures.

Status: Master Gate has failed on all of the last 300 master pushes, so this goes beyond one bad commit. I'm checking whether the gate has ever passed and which failures are chronic.

Status: six of the failures are untracked or deterministic. I'm tallying failure frequency over the last dozen Master Gate runs to separate real breakage from flakes.

All reproduce locally. Next I'm finding the root cause of the canary regression in 3dc72ddd4c.

Now the temporary experiment: skip the failure-frontier mirror when the root's status is a settled hijack state.

The guard makes the canary pass (14s, versus a 60s timeout before). The revert stalled on an interactive `cp` prompt, so I'm restoring the file with git instead.

That covers the investigation. Before drafting the plan, I'm collecting the specific details for the video-frames fix.

I have enough to write the plan. Loading the planning skill.

Before writing the plan, I'll check whether an empty-PATH pytest run is a workable no-ffmpeg reproduction recipe for the implementer.

An empty PATH reproduces exactly the five CI video failures and nothing else, so that's the verification recipe. Writing the plan now.

Validation passed. Before proposing, I'll check two claims the plan makes about the lumberjack facade and the current `__all__` exports.

The facade has no loader calls, so the audit swap is correct. The plan's facade instruction is broader than needed, so I'm narrowing it to the three renames.

Validation passes and the working tree is clean; the plan file is ignored by git. Proposing the plan now.

Yes, this is fixable, and I've staged a plan for it.

**What I found:** Master Gate has failed on all of the last 300 master pushes, so the bcaa3a8 run is one more red in a long streak. Over the last 16 runs, five failures recur every time. All five reproduce locally on HEAD (`1b9e88513b`), and each has a known cause:

1. **Collection ImportError (shards 3 and 6).** `tests/ace/tui/models/test_agent_session_members.py` is a file that only re-exports tests. It still imports three tests by names that 3dc72ddd4c changed. That also breaks `test_contract_manifest`.
2. **Hijack canary timeout (shard 5).** This is a real TUI bug, not a flake, despite an epic note calling it intermittent. It started at 3dc72ddd4c: the run on its parent commit passed, and every run since has failed. A new "newest failed child" rule copies FAILED onto a root row whose status is HIJACKED. The FAILED comes from the runner step the hijack killed. A temporary guard skipping that rule for hijack-settled roots made the canary pass (14s instead of a 60s timeout); I reverted it.
3. **Lumberjack audit path (shard 1, bead sase-1uz).** The audit still points at `lumberjack.py`, but `_run_tick` moved to `_lumberjack_tick.py`.
4. **Video-frame tests (shard 7, bead sase-1u8).** The tests fake `subprocess` but not `shutil.which`, so they fail on GitHub runners, which have no ffmpeg. Running them with an empty PATH reproduces exactly these five failures.
5. **Convergence repro (shard 8, new at HEAD).** d1cc8bfd45 split a method, and the test's stand-in object lacks the new `_surface_token_consumer_drifted`.

**The plan** (`sase_plan_fix_master_gate_deterministic_failures.md`, size small) fixes all five:
- Fix the three stale imports.
- Make the failure rule leave HIJACKED/ESCALATED/CONTINUED roots alone, add a regression test, and turn that set of statuses into a shared public constant.
- Point the audit at `_lumberjack_tick.py`.
- Add a fake `shutil.which` fixture to the video tests.
- Add the missing method to the stand-in.

Each fix has a direct pytest check (including the empty-PATH video run), then `sase tool run check`, then closing sase-1uz and sase-1u8.

The gate can still go red now and then, from two flakes that already have their own beads. sase-1v2 is a GC-leak test, seen in about 5 of the last 22 runs, including bcaa3a8. sase-1ty is a video modal test that loads frame 0 twice. I left both out of this plan.

The plan proposal is staged for your approval.
