#gh:gh_sase-org__sase Sase agents are running the `just check-full` command much more than they
should because of this project's instructions / memories. Can you help me fix this by
instructing agents to only run the `just check-full` command when they are explicitly
instructed to do so (i.e. to fix a CI failure)?

- Epic lander agents should stop running this command too which means we should, as a
  part of this change, stop giving them a default capacity (via the `%queue` directive)
  of `2`.
- The idea is that, if an agent makes changes that do not trigger the `just check`
  command to fail, but trigger the `just check-full` command to fail, we should treat
  that as a test infrastructure bug that is out-of-scope for the current agent's work.
- The `just check` command can still escalate to the full test suite if necessary (which
  should ideally be rare).

#plan %m:grok-4.6@xhigh