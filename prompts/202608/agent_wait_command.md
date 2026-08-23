- **PLAN:**
  [202608/agent_wait_command.md](https://github.com/sase-org/sase--plans/blob/main/202608/agent_wait_command.md)
- **AGENTS:**
  - [bbugyi200.athena.0bd--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0bd.md)

Can you help me add a new `sase agent wait` command that takes an agent name as an
argument and waits for that agent to complete before terminating?

- This command will be used to run certain commands only once certain agents have
  finished running.
- It should exit with a non-zero status code if the agent failed.
- It should have excellent, practically useful output.
- It should accept a `-a|--all` option that allows the command to run without an agent
  name argument. When this option is used, we should wait for all currently running
  agents to finish before the command terminates.
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
