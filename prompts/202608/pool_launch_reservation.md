- **PLAN:**
  [202608/pool_launch_reservation.md](https://github.com/sase-org/sase--plans/blob/main/202608/pool_launch_reservation.md)
- **AGENTS:**
  - [bbugyi200.athena.0cc--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0cc.md)

I suspect that when we launch epics, each model alias pool does not always respect the
given configuration of the pool (i.e. the models in the pool, their specified weights,
and which models were used last for each model alias). Can you help me confirm/deny my
suspicion, diagnose the true root cause, and fix the issue?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
