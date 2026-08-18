- **PLAN:**
  [202608/agent_restart_command.md](https://github.com/sase-org/sase--plans/blob/main/202608/agent_restart_command.md)
- **AGENTS:**
  - [bbugyi200.athena.05t--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05t.md)

Can you help me add a new `sase agent restart <agent_name>` command?

- This command should re-launch (after killing/dismissing) the sase agent named
  `<agent_name>`.
- See how the `,x` keymap on the agents tab in the TUI works for inspiration.
- Make sure this command has excellent, useful output.
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
