# Chat History - ace-run (95.f1--plan)

- **TIMESTAMP:** 2026-07-15 11:43:48 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 95.f1--plan

**Plan:** /home/bryan/.sase/plans/202607/enforce_sidecar_ssh_remotes.md


## Prompt

#gh:gh_sase-org__sase #fork:95 Can you help me also verify that the clone we create uses the proper SSH git remote (ex: `git@github.com:sase-org/sase--plans.git`--HTTPS git remotes are not allowed)? If not, use your /sase_plan skill to plan the appropriate changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/enforce_sidecar_ssh_remotes.md`

> # Plan: Enforce SSH remotes for sidecar clones
> ## Context
> Fresh numbered-workspace launches now recreate the required plans sidecar from the authoritative remote recorded in the
> durable SDD store. The clone helper currently passes that recorded value directly to `git clone`. Although configured
> GitHub sidecars are resolved elsewhere with canonical SSH URLs, a legacy store record can still contain
> `https://github.com/<owner>/<repo>.git`; the resulting fresh clone and its `origin` therefore use HTTPS. This is
> observable in the current plans checkout and violates the repository's documented SSH transport policy.
> The fix must preserve the authoritative-remote and fail-closed launch behavior from the fresh-workspace change. It must
> not restore durable-primary clone seeding, add interactive credential fallbacks, or make launch depend on first running
> `sase repo init`.

*See full plan file for details.*

