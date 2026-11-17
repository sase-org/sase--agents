# Chat History - ace-run (1d9--plan)

- **TIMESTAMP:** 2026-11-17 06:52:32 EST
- **MODEL:** claude/opus
- **AGENT:** 1d9--plan

**Plan:** /home/bryan/.sase/plans/202611/unmanaged_project_axe_noise.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/unmanaged_project_axe_noise.md`

> # Plan: Stop Unmanaged Projects From Tripping `agent_publication` And Artifact Retention
> ## Problem
> An enabled project whose repository is **not sase-managed** (no `is_sase_managed: true`
> in its `sase.yml`) is a supported configuration. It launches agents, but it never gets
> SDD sidecars: `auto_connect_sdd_store` returns `False` for it, and the
> `sidecar_auto_sync` connect leg classifies it as `not_applicable`. Two scheduler jobs
> still treat such a project as broken, and one of them does so in a hot loop.
> Observed on a machine where a fresh `gh` project (`nut`: a one-commit repo with only a
> `README.md` and no `sase.yml`) was registered and enabled. Its axe error digest held 44
> errors in 12 minutes:

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase Is this something we can/should fix? If so, use your /sase_plan skill to plan the appropriate changes. See the
~/.sase/axe/error_digests/digest_20261117_064547.txt file on the apollo machine for
context. %m:@xlarge

## Response

The digest on apollo has two errors, both caused by the `nut` project. I'm reading the code for each.

Quick update: both errors come from the new `nut` project on apollo. It was created yesterday and has no sidecars. I'm checking whether this is a setup gap or a code bug.

Confirmed so far: `nut` is an enabled project on apollo whose repo has no `sase.yml`, so it can never get sidecars. I'm checking how the code is meant to handle unmanaged projects like this.

Root cause is clear for the retention error. I'm checking why the publication error repeats every ~18 seconds, which looks like a doorbell feedback loop.

I'm checking one edge case before writing the plan: managed projects that keep SDD data locally rather than in sidecar repos.

Both errors are code bugs, and both are worth fixing. Opening the planning skill.

The plan passed validation. Submitting it for approval.

Yes, both errors should be fixed, and I've submitted a plan for approval. Both come from the new `nut` project on apollo. Its repo has only a `README.md` and no `sase.yml`, so SASE treats it as unmanaged and it can never have sidecars. That setup is supported, but two scheduled jobs treat it as broken.

**1. `agent_publication` (43 of the 44 errors, about every 15–18 seconds).** `nut` has no agents sidecar, and `sase agent sync --check -p nut` already reports that as a skip, not an error. But the publication job in `src/sase/agents_sync/publication_job.py` counts any project without a publish target as an error. It also touches that project's doorbell file, and the scheduler re-runs the job whenever the doorbell changes. So the job keeps re-triggering itself, and this will continue until fixed. `nut` has nothing queued to publish, so the errors are pure noise.

**2. `artifact_run_prune` (hourly).** Cleanup of old agent run directories refuses to delete anything while any enabled project is missing its beads or plans sidecars. It doesn't tell apart "not connected yet" from "can never connect". `nut` can never connect, so all 7,698 candidates are held and cleanup on apollo has been stopped since `nut` was added last night. The artifact-file cleanup job uses the same rule and is blocked the same way.

**What the plan does (one agent, medium size):**
- **Unmanaged check:** adds one check meaning "this project is definitely unmanaged and has no SDD store on this machine". Anything ambiguous, like an unreadable `sase.yml` or store record, still counts as missing, so cleanup stays blocked as it does today.
- **Cleanup jobs:** both skip a missing beads or plans sidecar only when that check passes. Managed projects that just haven't connected yet still block cleanup, as now.
- **Publication job:**
  - A skipped project with nothing queued is no longer an error.
  - It only reports an error when publish requests are actually stuck.
  - It stops ringing the doorbell for projects it can't publish; the job still runs at least every 5 minutes on its own.
  - It no longer counts a target error twice.
- **Docs and tests:** covers both docs pages and adds tests for each case.

**If you want the noise gone before the fix lands,** either make `nut` a managed project (add `is_sase_managed: true` to its `sase.yml` and run `sase repo init` there), or disable the `nut` project on apollo. Either one clears both errors.

The digest's summary line also shows `parked=2`. Those are two old publication rows in `job` and `bob-cli` that are still waiting for their agents to finish. They aren't errors, and the plan leaves them alone.
