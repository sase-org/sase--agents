#gh:gh_sase-org__sase Can you help me add a new `sase agent wait` command that takes an agent name as
an argument and waits for that agent to complete before terminating?

- This command will be used to run certain commands only once certain agents have
  finished running.
- It should exit with a non-zero status code if the agent failed.
- It should have excellent, practically useful output.
- It should accept a `-a|--all` option that allows the command to run without an agent
  name argument. When this option is used, we should wait for all currently running
  agents to finish before the command terminates.
- #beau

#plan