- **PLAN:**
  [202610/finalizing_overlay_working_tale.md](https://github.com/sase-org/sase--plans/blob/main/202610/finalizing_overlay_working_tale.md)
- **AGENTS:**
  - [bbugyi200.athena.0w9--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0w9.md)

We don't currently seem to show the `FINALIZING` node status when a coder agent is
working a tale plan. Instead, we always show `WORKING TALE` status until the coder agent
completes. This is not correct. We should prefer to show the `FINALIZING` status like we
do in other cases (i.e. for agent nodes that are not working tale plans). Can you help
me confirm/deny my suspicion, diagnose the true root cause, and fix the issue?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
