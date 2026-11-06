#gh:gh_sase-org__sase I would like to add support for "hijacking" a stalled sase agent. Can you help me
implement this?

- An "agent hijack" (aka "hijack"--we should add a good new glossary term for this) is
  meant to describe the process of killing a sase agent without releasing its workspace
  or dismissing it.
- The agent node should then be rendered with the new "HIJACKED" status on the "Agents"
  tab.
- If the `<enter>` keymap is used when a "HIJACKED" agent is selected a new panel should
  be triggered that allows the user to select (with a single keypress) between one of
  the following options. Think hard about what other options (if any) this panel should
  support:
  - Restart the agent by dismissing it (and releasing its workspace) and relaunching it
    using the exact same prompt.
  - Dismiss (and release the workspace) and edit the agent prompt (similar to what the
    `,x` keymap does).
  - Escalate to a smarter model. We should use the `@xlarge` model alias if the `@large`
    model alias was used for the previous prompt; otherwise, we should use the `@large`
    model alias. We should NOT release the workspace in this case since the smarter
    model needs to have access to all of the previous agent's file changes.
- We may want to add support for one or more new sase config fields to support this new
  functionality, but I'll let you decide.
- Review the agent_hijack_held_workspace_recovery.md file in the research sidecar repo
  for context and inspiration before planning. I agree with all of the requirements
  recommended in that research file (but keep in mind that you are responsible for
  planning and splitting up this work appropriately).
- #beau

#plan %m:@xlarge %w:research.33.linker