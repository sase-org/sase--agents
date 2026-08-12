- **PLAN:**
  [202608/sase_monitor.md](https://github.com/sase-org/sase--plans/blob/main/202608/sase_monitor.md)
- **AGENTS:**
  - [bbugyi200.athena.yy--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.yy.md)

Sase agents sometimes try to use their own "monitor" / "scheduled wake-up events" when
running slow commands like the `just check-full` command. These don't work in sase,
which expects agents to be single-turn! Can you help me fix this problem and add a
considerable tool to each sase agent's toolbelt by giving them access to a new
`/sase_monitor` skill?

- This skill, which agents should be instructed to use over any other monitor /
  scheduled wake-up utility they have access to, should be powered by a new
  `sase monitor start` command (the skill should briefly describe the other sub-commands
  discussed below too).
- In order to support this new feature, we will need to add support for a new "monitor"
  agent family member, which should be similar to a "bash" member (i.e. a bash step in
  an xprompt workflow), but with several improvements geared to support long-running
  commands better:
  - We should support live command output when a monitor member is selected.
  - We should support a live runtime that adds to the family's total runtime (like with
    agents).
  - We should support showing custom statuses when the monitor starts and stops, which
    should default to `MONITORING` and `MONITORED`, respectively.
  - Make sure that monitor members have first-class support for agent families (i.e.
    they should support all of the same UI surfaces for families that agents do).
  - Make any other objective improvements (when compared to bash steps) you can think
    of.
- The `sase monitor start` command should kill the currently running sase agent, if any,
  and then start a new monitor member. It should accept the following arguments (I think
  this is all of them but if more arguments are necessary or objectively useful then add
  support for them).
  - The full command that should be run and monitored.
  - The name of the agent lane that we should target (if this lane specifies a single
    agent, a new agent family should be created by appending the appropriate
    `--<suffix>` to that agent's name).
  - The reason for monitoring this command.
  - A command timeout, which specifies the number of seconds we will wait for the
    command to complete before it times out (the next agent in the family, if a next
    action was provided, should still be launched in this case, with details on the
    command's progress before the timeout).
  - (optional) The custom start/stop statuses mentioned above (default to
    `MONITORING`/`MONITORED`).
  - (optional) The next action, if any, that we should take after the command completes.
    If a next action was provided, the reason and next action should be provided to the
    next agent that is launched in the same family when the command we are monitoring
    completes. We should also provide an excellent breakdown of the command run, with
    information that helps the next agent debug the command if necessary.
- The `sase monitor` command should also support the following sub-commands:
  - `stop`: Stop a running monitor (no agent should be launched in this case, even if a
    next action was provided).
  - `list`: List all active monitors by default, but this command should be able to list
    historical monitors as well.
  - `show`: Show details about a specific monitor (support multiple formats for this and
    `list`).
- The agent that is launched in the family that started the monitor (only if a next
  action was provided) should be launched in the same workspace (with no files changed
  since the monitor was started).
- The sase agent that runs the `sase monitor` command should be killed, but the new
  agent should be launched with access to the previous conversation (see how the `#fork`
  xprompt workflow works for inspiration on how to implement this--maybe just use
  `#fork`?).
- We should instruct agents (in the sase/memory/build_and_run.md memory file) to only
  run `just check-full` as a sase monitor and to feel free to run `just check` as a
  monitor as well if it is taking a very long time.
- We should also start using this new functionality to launch epics by starting a
  monitor with the `sase bead work` command (instead of using background tasks for
  this). Figure out how this will work based on the above requirements. Don't add any
  special treatment for this use-case (it should be supported generically so any user
  could do the same directly by running the appropriate `sase monitor start` command).
  Use `EPIC APPROVED` and `EPIC CREATED` for the start/stop statuses, which should
  maintain current functionality Be careful that you do not break epic
  approvals/launches!
- The `/sase_monitor` skill should also instruct agents (in its description) to use it
  if they need to sleep for a certain amount of time (to wait for a CI job to finish,
  for example) by monitoring the appropriate `sleep` command, in which case (describe
  this part by using the `sleep` command in an example in the skill's main content)
  `SLEEPING FOR <N>s` and `SLEPT FOR <N>s` should be used as the monitor start/stop
  statuses, respectively.
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
