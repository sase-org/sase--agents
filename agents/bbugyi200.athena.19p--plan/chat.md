# Chat History - ace-run (19p--plan)

- **TIMESTAMP:** 2026-11-07 12:31:32 EST
- **MODEL:** claude/opus
- **AGENT:** 19p--plan

**Plan:** /home/bryan/.sase/plans/202611/connect_unlaunched_project_sidecars.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/connect_unlaunched_project_sidecars.md`

> # Plan: Connect never-launched projects' sidecars so `artifact_run_prune` stops failing closed
> ## Problem
> Since 2026-11-07 ~07:00 EST, apollo's hourly `housekeeping/artifact_run_prune` job has
> reported `check_error · reason=protection_unavailable` on every run. That blocks the
> expired-trash purge, and the job shows up in every error digest:
> ```
> artifact_run_prune protection source unavailable: body:beads
> artifact_run_prune protection source unavailable: body:plans
> artifact_run_prune protection source unavailable: love:beads
> artifact_run_prune protection source unavailable: love:plans

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase I keep getting artifact prune errors on apollo (see the
~/.sase/axe/error_digests/digest_20261107_120308.txt file on that machine for context).
Can you help me diagnose the root cause of this issue and fix it?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:@xlarge

## Response

I'm reading the prune chop's protection-source code to see why `body` and `love` show up as unavailable on apollo.

The onboarding step list comes from the Rust planner in `sase-core`, so I'm weighing where the fix should go. Checking git history and existing beads for prior work on this failure.

I have the full picture, so I'm writing the plan file now.

The plan passes validation. Submitting it now.

The prune errors on apollo come from two projects that were added there but never used. `body` and `love` were added to apollo with `sase project add` today. That only cloned the main repos and skipped each project's separate beads and plans repos (the "sidecars"). Today, nothing sets those up until the first agent runs in the project on that machine, and none has run in either project on apollo. I've written a plan for the fix and submitted it for your approval; no code has changed yet.

**How the failure works**
- The hourly `artifact_run_prune` job deletes expired trash only after it has read every enabled project's beads and plans. That way it never deletes a run something still points to.
- On apollo, `body` and `love` have no `.sase/sdd-store.json` and no `sase/repos/`, so the job reports `body:beads`, `body:plans`, `love:beads` and `love:plans` as unavailable. It then skips the purge and reports an error every hour. Refusing to purge here is deliberate and should stay.
- Nothing ever fills the gap. `sidecar_auto_sync` sees those repos as `missing` every 30 seconds, but by design it only updates repos that are already cloned.
- Timeline: apollo cloned `love` at 06:33 EST and `body` at 07:40 EST. The remote `body--beads`/`body--plans` and `love--beads`/`love--plans` repos exist and have content. Apollo's `tailnet` project went through the same step on Oct 17 and was fixed 20 minutes later by its first agent run.
- Athena hits the same error briefly for brand-new projects (`sase-spotify`, `body`) while they are being created. It clears once creation finishes; on apollo it never clears.

**What the plan changes** (one agent, medium size)
1. **Backstop in `sidecar_auto_sync`:** for any enabled SASE-managed project that hasn't been set up on the machine yet, it runs the same clone-only setup a first agent run does. It never creates a repo on GitHub, handles at most one project per tick, and backs off after a failure. Every way a project can get registered is covered, and apollo heals itself once it has the new code.
2. **Clearer prune message:** a missing source will read like `body:beads (sidecars not connected on this machine)`, so the cause is obvious next time. The purge still refuses in that case.
3. **Tests and docs** for both changes, then `sase tool run check`.

**What you'll need to do**
- **Once the fix lands:** update apollo's install yourself (agents aren't allowed to reinstall). The next sync tick should then set up `body` and `love`, and the next hourly prune should show `unavailable=0`.
- **To stop the errors right away:** run any agent once in `body` and once in `love` on apollo. Their first run does the setup.

Separately, `sase repo list -p body` fails on apollo because it looks for `projects/body/body.sase` instead of the project's real directory. That's the existing bead `sase-zo`, which the plan leaves alone.
