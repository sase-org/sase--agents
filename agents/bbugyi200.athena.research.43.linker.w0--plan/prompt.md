%auto
#gh:gh_sase-org__sase There are some procs that are created by agents by running the `sase tool`
command. Can you help me implement this?

- These procs are not linked with the TUI session (they do not block TUI restarts, for
  example) and are a fundamentally different type of proc than one that is triggered by
  a user action in the TUI.
- We already use a specific icon for `sase tool` calls (in the sticky footer shown above
  deck panels , for example).
- I would like to start using that icon for these types of procs too.
- We should start showing this icon (with the corresponding count) in a new `tools:`
  section in the 2nd row of status indicators shown at the top of the TUI instead of as
  blue gears in the `procs:` section.
- As a part of this change, we should start using `bg:` instead of `procs:` for the
  section with the blue gears, since these should now only represent background
  processes associated with the TUI.
- Finally, we should make it clearer in agent tribe panels and nodes when a sase tool is
  running in that panel/node (make sure we support agent clan nodes).
- Review the tools_bg_split_and_tool_run_visibility.md file in the research sidecar repo for context and inspiration
  before planning. I agree with all of the requirements recommended in that research
  file.
- #beau

#plan %m:@xlarge %w:research.43.linker