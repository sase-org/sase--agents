- **PLAN:**
  [202610/update_skew_agent_auto_restart.md](https://github.com/sase-org/sase--plans/blob/main/202610/update_skew_agent_auto_restart.md)
- **AGENTS:**
  - [bbugyi200.athena.research.47.linker.w0--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.47.linker.w0.md)

A number of sase agents just failed on this machine with the following error:
`ImportError: cannot import name 'auto_launch_prefix' from 'sase.monitor.continuation_delivery'`

- This error was clearly caused by updating sase while agents were running, which is
  something I would like to support.
- I would like to start automatically detecting errors like this and attempting to
  automatically resolve the issue by dismissing and re-launching the sase agent that
  failed.
- We should try to restart an agent exactly once when a detected error pattern matches.
  Think hard about which error patterns we should check for.
- This operation should be very similar to what happens when the user selects a failed
  agent on the "Agents" tab, uses the `,x` keymap to dismiss and edit it, and then
  submitting the prompt (e.g. via the `<ctrl+g><enter>` keymap) that loads in the prompt
  input widget without modifying it.
- We should send an excellent and thorough sase notification to the user when we restart
  a failed agent like this.
- Review the update_skew_agent_auto_restart.md file in the research sidecar repo for
  context and inspiration before planning. I agree with all of the requirements
  recommended in that research file.
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
