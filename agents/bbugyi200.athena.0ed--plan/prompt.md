#gh:gh_sase-org__sase Can you help me add support to sase notifications for a way to group the
notifications within a particular tab into sections?

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
- #beau

#plan #m_opus