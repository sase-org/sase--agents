# Chat History - ace-run (1dw--plan)

- **TIMESTAMP:** 2026-11-18 09:00:25 EST
- **MODEL:** claude/opus
- **AGENT:** 1dw--plan

**Plan:** /home/bryan/.sase/plans/202611/sdd_timeouts_not_unsafe.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/sdd_timeouts_not_unsafe.md`

> # Stop reporting SDD git timeouts as unsafe repositories
> ## Problem
> The `sdd-sidecar` / `workspace_sdd_clone_recovery` axe error keeps showing up in error
> digests with messages like:
> ```
> SDD repository ~/.sase/projects/gh_bbugyi200__body/repos/plans is not safe to write:
> not a valid Git worktree; detached HEAD; could not list unmerged index entries:
> deadline expired before git operation. Finish or abort the existing Git operation ...;
> machine-managed recovery failed: the checkout is not a valid Git worktree
> ```

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase Is this something we can/should fix? If so, use your /sase_plan skill to plan the appropriate changes. See the
~/.sase/axe/error_digests/digest_20261118_085119.txt file on my apollo machine for
context. %m:@xlarge

## Response

The deadline comes from the machine artifact-link chops, which pass a budget to the hidden-clone integration. Checking how often this has fired on apollo and which chop was running at 08:25.

Findings are complete; I'll check one more consumer set (bead sync), then write the plan.

I have enough to plan. Loading the planning skill.

Before writing the plan I need to see how the other `integrate_sdd_repository` callers branch on outcome status, so I can tell whether a new status is safe to add.

Last check before writing: how many places call `inspect_sdd_repository` and catch its exceptions, since the fix changes what it raises.

I have the full picture. Writing the plan as one tale.

Plan validates. Proposing it.

Yes, it's worth fixing, and I've proposed a plan for it. The repo was never broken: the error is a git timeout reported as repository damage. The plan is waiting for your approval in the plan gate.

**What happened:** The 08:25 report on apollo says the `body` project's `plans` clone is "not safe to write: not a valid Git worktree; detached HEAD". When I checked it afterwards it was on `main`, clean and up to date.

The chops that publish artifact links give the clone sync a time budget. When the budget runs out, every later git command fails with "deadline expired". The health check (`inspect_sdd_repository` in `src/sase/sdd/_repository_health.py`) reads each of those failures as a real finding: no worktree, detached HEAD, unknown conflicts. That turns into an "unrecoverable" result. Recovery then runs out of time the same way and gets the same result, so `pull_sdd_clone` sends it to the error digest.

**It recurs:** apollo has about 20 of these reports since early October. All but about two are timeouts, either the budget running out or a single git command exceeding its 30s limit. The earlier fix (`sase-9r`) only handled the lock-contention version of this error.

**Worse cases on the same path:**
- A timed-out upstream lookup is currently reported as **success**.
- A timed-out status check during a clone's upstream comparison can start the **destructive recovery** (snapshot, then `reset --hard`).
- If time runs out in the middle of a rebase, the undo runs with no time left, so it can't actually abort. That can leave a real stuck rebase behind.

**The plan (one agent, medium size):**
- Git results that timed out are marked as timeouts, and the health check stops treating them as evidence the repo is broken. Anything it misses still fails safely, as today.
- A new `TIMED_OUT` status, meaning "state unknown, nothing changed". It never starts recovery, never pauses future syncs, and never reaches the digest; the attempt is simply retried on a later run.
- Once a rebase or recovery has actually started changing the clone, the undo and its checks get their own 20-second allowance (`SDD_ROLLBACK_GRACE_SECONDS`) instead of running on an empty budget.
- Genuinely broken states (detached HEAD, a merge in progress, unmerged files, a leftover rebase) keep today's recovery and reporting.
- Ten targeted tests, including a real rebase that runs out of time partway through.

**Decision for you:** whether a clone that keeps timing out should still reach the digest eventually. The default is **never**, because every git timeout is already logged. The alternative reports once after three slow-command timeouts within 30 minutes.
