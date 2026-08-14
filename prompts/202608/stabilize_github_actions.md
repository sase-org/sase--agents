- **PLAN:**
  [202608/stabilize_github_actions.md](https://github.com/sase-org/sase--plans/blob/main/202608/stabilize_github_actions.md)
- **AGENTS:**
  - [bbugyi200.athena.01o--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.01o.md)

GitHub Actions is failing for the sase repo. Can you run the `actstat` command to get
more information about the failing jobs, diagnose the root cause of these failures, and
then fix them?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes. In
this plan, make sure to include instructions to use the /sase_monitor skill to wait for
a new GitHub Actions run to complete and have the next agent verify the fix worked and
that the `actstat` command shows the sase project has passed its last GitHub actions
run. If not, the agent should produce a new plan using the /sase_plan skill that
instructs the next agent to verify its changes by using the /sase_monitor in the same
way. This should continue in a loop until GitHub Actions is stable and passing all
checks.
