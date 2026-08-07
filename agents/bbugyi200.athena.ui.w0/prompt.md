#gh:gh_sase-org__sase %w:ui Can you help me start requiring that every tab in the notification panel have an icon associated with it?

- This new icon should be shown next to the tab name in the list of tabs shown at the top of the notification panel.
- We should also render this icon next to the notification counts that are shown for each tab in the notification visual
  indicator that is shown on the top right of the TUI.
- Make sure you associate an appropriate icon with any built-in notification panel tabs that we support. Also, make sure
  to do the same with any custom sase gates that we use and make sure that future gates (if they introduce new
  notification panel tabs) are required to configure/speicify this.
- Also, replace the `z` suffix we use for the snoozed notification count with an appropriate icon.
- #beau

#plan #m_opus