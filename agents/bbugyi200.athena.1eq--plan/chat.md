# Chat History - ace-run (1eq--plan)

- **TIMESTAMP:** 2026-11-20 18:13:45 EST
- **MODEL:** claude/opus
- **AGENT:** 1eq--plan

**Plan:** /home/bryan/.sase/plans/202611/housekeeping_retention_scan_speedup.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/housekeeping_retention_scan_speedup.md`

> # Stop the hourly artifact-retention housekeeping jobs from timing out
> ## Problem
> The axe error digest `digest_20261120_175619_e5de8115` reports three jobs killed at
> their 300s timeout around 17:29. Two of them are a recurring pattern, not a one-off:
> - `housekeeping/artifact_retention` and `housekeeping/artifact_run_prune` both run
>   hourly, start at the same moment, and have hit the 300s timeout about ten times since
>   2026-11-19 (for example 2026-11-19 10:18, 12:22, 13:51, 14:25, 19:36 and 2026-11-20
>   10:20, 15:05, 17:13, 17:29). Their successful runs on 2026-11-20 took 37s to 265s
>   while doing nothing (`trashed 0 rows`, `selected=0`). The spread follows host load:
>   athena ran at load average around 40 with 10-23% iowait from 15:00 to 17:40.

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase Is this something we can/should fix? If so, use your /sase_plan skill to plan the appropriate changes. See the ~/.sase/axe/error_digests/digest_20261120_175619_e5de8115.txt file for context. %m:@xlarge

## Response

Confirmed this is recurring (artifact_retention / artifact_run_prune have timed out ~10 times since Nov 19). Now reading the job code and related beads to find why no-op runs take minutes.

Profiling the protection scan pieces (read-only) — the projects tree has 1.2M files / 208k dirs, which both jobs walk every hour.

Root cause is clear for the two housekeeping jobs. Quickly checking whether the one-off agent_publication timeout has a code-level cause (its pass is supposed to self-bound at 4 min).

Checking in-flight beads (sase-1tz.4, sase-11h) so the plan doesn't overlap existing work.

No existing bead covers this. Measuring the plan-phase pieces of artifact_run_prune without profiler overhead to size the wins.

Checking the Rust run-retention owner's handling of recent-month candidates (decides whether Python can skip per-run scanning for runs that can never be selected).

Now writing the plan file.

Plan validates. Proposing it.

Yes, it's worth fixing, and I've proposed a plan. It covers the two housekeeping timeouts, which are a real bug. The publication timeout was a one-off that can't be traced from what's left, so the plan only makes the next one traceable.

**What's happening**

- **`artifact_retention` and `artifact_run_prune`** keep timing out. They've hit the 300s limit about ten times since Nov 19. Even when they have nothing to delete, they take 37–265s. Both are single-threaded Python scans of the same files every hour. On a quiet athena they still take 35–65s, so when the host is busy (load around 40 and 10–23% iowait from 15:00 to 17:40 today) they go past 300s. From profiling:
  - **`artifact_retention`:**
    - About 20s goes to one artifact-id regex over about 70k sidecar text files. Its optional `file:` prefix makes Python's regex engine slow. A cheap substring check plus a simpler regex finds the same 1,145 ids in 1.6s.
    - About 9.5s goes to walking all 1.2M files under `~/.sase/projects` to find about 20 `<project>.sase` files, which yields 0 ids. The `artifact_run_prune` version of the same walk already skips the `artifacts/`, `repos/` and `.git` folders.
  - **`artifact_run_prune`:**
    - About 8.7s goes to the `agent:` regex. The same substring-check trick gets it to about 1s with the same matches.
    - It sizes all 24,111 run folders (about 1M file-size lookups), although sizes are only used for runs it actually selects. Today it selected none.
    - It fully scans about 11.6k runs from the last two months, which the Rust side always protects.
- **`agent_publication`** timed out once, during the same busy window, and printed nothing. Its run log had already been deleted (it only keeps the last 10 runs, and it runs every 15s).

**The plan (one agent, medium)**

1. Make both protection scans faster without changing their results: the substring checks, skipping the same folders in both walks, and less per-file overhead.
2. Only size the runs that get selected, and stop recomputing the same path lookups for every run.
3. Skip the per-run scans for runs from the last two months. This is the plan's one decision, and skipping is the default. Selection and counts stay the same. The only visible change is that the JSON output lists fewer protection reasons for recent runs.
4. Have both housekeeping jobs print a progress line after each step, so a future timeout shows where the time went. Have `agent_publication` print progress only once a run passes 60s, so normal runs stay quiet.

Before and after the change, the implementing agent must check on your real data, without deleting anything, that every protected item and every selected run is exactly the same. Protection is what stops user data being deleted, so this check is required. Timing targets on a quiet host:

| Step | Now | Target |
|---|---|---|
| `artifact_retention` protection scan | ~35s | ≤ 8s |
| `artifact_run_prune` protection scan | ~16s | ≤ 8s |
| `artifact_run_prune` planning | ~27–47s | ≤ 15s |

No existing bead covers this, and no change in sase-core is needed. Rewriting the scans in Rust is left out unless these targets are missed. The plan is staged and waiting for your approval.
