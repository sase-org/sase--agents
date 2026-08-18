# Chat History - ace-run (05f--plan)

- **TIMESTAMP:** 2026-08-17 19:00:30 EDT
- **MODEL:** claude/opus
- **AGENT:** 05f--plan

**Plan:** /home/bryan/.sase/plans/202608/agent_pipe.md


## Prompt

#gh:gh_sase-org__sase Can you help me add a new `sase pipe` command?

- I've recently found it useful to have agents start pseudo-sase monitors using the
  `sleep 1` command and a next action (so an agent gets launched after the `sleep 1`
  command completes), but this is a bit of a hack.
- Instead I would like agents to be able to spawn their next family member agent using a
  new /sase_pipe xprompt skill (which delegates to the `sase pipe` command).
- The description for this new skill should instruct the agent to only use this skill
  when asked to by the user. Make sure this description also gives an excellent summary
  of how this skill can be used.
- In general think very hard about the skill description and contents. Make sure both
  are excellent but concise. Remember every token added to context either helps or
  hurts us.
- Also, we now have several locations in the code base, I'm assuming, where we launch
  agent family members (ex: sase monitors, coder agents that implement plans, etc...).
  Try your best to make sure all of that code uses the same shared logic.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/agent_pipe.md`

> # Plan: `sase pipe`: a first-class hand-off to the next agent family member
> ## Why
> An agent that wants its successor to pick up the work has no direct way to ask for one.
> Agent-initiated launches go through `LaunchApproval` (`/sase_run`), which is correct for
> fan-out but wrong for a hand-off: it needs a human answer, and the agent is asking to be
> _replaced_, not to gain a helper. So agents have learned a workaround:
> ```bash
> sase monitor start --command 'sleep 1' --reason '...' --next '<the real prompt>'
> ```
> That works only because `sase monitor start` already kills the calling agent and the

*See full plan file for details.*

