- **PLAN:**
  [202608/clan_dismiss_cascade.md](https://github.com/sase-org/sase--plans/blob/main/202608/clan_dismiss_cascade.md)
- **AGENTS:**
  - [bbugyi200.athena.07t--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07t.md)

Dismissing agent clans doesn't always work. And when it does it can take a while for all
of the agents in the clan to be dismissed (i.e. the agent clan shells remain visible for
a while after the user uses the `x` keymap to dismiss the clans). See #sshot for context
(the DONE agents in the `@epic` agent tribe panel were just dismissed but are still
visible for some reason). Can you help me diagnose the root cause of this issue and fix
it?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
