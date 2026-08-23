# Chat History - ace-run (0bd--plan)

- **TIMESTAMP:** 2026-08-23 11:39:17 UTC
- **MODEL:** claude/opus
- **AGENT:** 0bd--plan

**Plan:** /home/bryan/.sase/plans/202608/agent_wait_command.md


## Prompt

#gh:gh_sase-org__sase Can you help me add a new `sase agent wait` command that takes an agent name as
an argument and waits for that agent to complete before terminating?

- This command will be used to run certain commands only once certain agents have
  finished running.
- It should exit with a non-zero status code if the agent failed.
- It should have excellent, practically useful output.
- It should accept a `-a|--all` option that allows the command to run without an agent
  name argument. When this option is used, we should wait for all currently running
  agents to finish before the command terminates.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/agent_wait_command.md`

> # Plan: `sase agent wait`
> ## Goal
> Add `sase agent wait`, a gate command that blocks until the agents you name (or every
> agent running right now) reach a terminal state, then exits with a status code that says
> what happened. It is the missing primitive for "run this only after those agents
> finish".
> ```bash
> sase agent wait sase-s7.2 && just check-full
> sase agent wait -a -t 2h
> sase monitor start -s WAITING -S WAITED -n 'agents finished; land the epic' -- sase agent wait -a

*See full plan file for details.*

