- **PLAN:**
  [202608/notification_tab_sections.md](https://github.com/sase-org/sase--plans/blob/main/202608/notification_tab_sections.md)
- **AGENTS:**
  - [bbugyi200.athena.0ed--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ed.md)

Can you help me add support to sase notifications for a way to group the notifications
within a particular tab into sections?

- These sections should be separated by blank lines.
- These sections should support custom, richly formatted section headers.
- We should add a new keymap (choose an appropriate trigger key) that toggles between
  this custom grouping (specific to the particular notification tab--I'm not sure how
  this will be configured, so you'll have to figure that out) and sorting all
  notifications on the tab based on which was received last (more recent notifications
  should be shown above notifications that were received earlier--this is what we should
  already do now). The default sorting/grouping strategy should be the custom strategy
  with sections (if one is configured for that tab).
- As our first use-case, we should start sorting the bead notifications in the `Beads`
  tab based on the task bead type and/or notification type (we receive stale bead
  notifications on this tab too, for example).
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
