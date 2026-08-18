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

#plan