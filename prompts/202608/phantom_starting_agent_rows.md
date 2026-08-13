- **PLAN:**
  [202608/phantom_starting_agent_rows.md](https://github.com/sase-org/sase--plans/blob/main/202608/phantom_starting_agent_rows.md)
- **AGENTS:**
  - [bbugyi200.athena.zy--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zy.md)

I feel like I am constantly (at least way too often) seeing `1 starting` on the agents
tab (see #sshot for context). If I had to guess, I'd say that this has the same root
cause as a bug that causes agent launches to take a while and for agents to jump from
the `RUNNING` state to the `STARTING` state and back again repeatedly before finally
launching. Can you help me confirm/deny my suspicion, diagnose the true root cause, and
fix the issue?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
