- **PLAN:**
  [202608/hide_operational_lease_agent_rows.md](https://github.com/sase-org/sase--plans/blob/main/202608/hide_operational_lease_agent_rows.md)
- **AGENTS:**
  - [bbugyi200.athena.03w--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03w.md)

I keep seeing `[agent] bead_claim_checks:gh_sase-org__sase (STARTING)` rows in the
agents tab of the TUI. They show up randomly and then disappear pretty quickly
afterwards. Can you help me figure out where these are coming from and start hiding
these rows? I think we already have the infrastructure in place for hiding rows like
this so do some research into that before planning out your solution.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
