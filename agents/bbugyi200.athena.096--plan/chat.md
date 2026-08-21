# Chat History - ace-run (096--plan)

- **TIMESTAMP:** 2026-08-21 09:05:18 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 096--plan

**Plan:** /home/bryan/.sase/plans/202608/retire_pluggable_finalizers.md


## Prompt

#gh:gh_sase-org__sase Can you help me review the `pluggable_finalizers` feature flag (see @bead:sase-rn for context), thoroughly end-to-end test the corresponding functionality, complete any remaining work, fix any discovered bugs, remove the `pluggable_finalizers` feature flag (and the old, deprecated code), and close the corresponding "feature" task bead? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/retire_pluggable_finalizers.md`

> # Plan
> ## Context and current-state findings
> The implementation epic `sase-rn` is closed and all seven of its phases landed. Its
> dedicated beta-removal task is `sase-ro` (`task(flag)`, currently open), whose removal
> rule is to delete the disabled branch and make the enabled branch unconditional. The
> current process has `pluggable_finalizers` forced on through `SASE_FEATURE_FLAGS`, but
> the code-owned default is still off.
> The retirement is not a four-call-site edit. The audit found all of the following:
> - `invoke_agent()` still chooses between `run_finalizers()` and the old
>   `run_commit_finalizer()` and records a legacy/pluggable parity metric.

*See full plan file for details.*

