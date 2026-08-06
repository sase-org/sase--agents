- **PLAN:**
  [202608/bead_snooze_and_notification_indicator.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_snooze_and_notification_indicator.md)
- **AGENTS:**
  - [bbugyi200.athena.uh--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.uh.md)

Can you help me add a new `snoozed` sase task bead status and help improve the notification panel's visual indicator
(shown on the top-right of the TUI)?

I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but
not least) beautiful! Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author
the appropriate tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill
instructs) before making any file changes.

### Notification changes

- Let's use one count (in the visual indicator) per notification panel tab that would be displayed if the notification
  panel were opened.
- There is one exception / special case to the above bullet's rule: The count associated with snoozed notifications
  should be hidden if any other tab exists. Otherwize, we should show the count as `<N>z` (note the `z` suffix) with a
  grey, dim syntax highlighting.
- Use your best judgment about which color to use for the notification panel visual indicator in other cases (I'm
  thinking that the user / notification senders should have some control over this?).
- Make sure to show great, useful information about the notification panel's contents if the user hovers over the
  indicator with their mouse.
- POSSIBLE EXISTING BUG: Make sure that no tab on the notification panel can contain the same notification. I feel like
  I've seen instances where I've dismissed a single notification and then multiple tabs disappear but I am not sure if
  this is really happening or not. You will need to investigate.
- Snoozing a task bead should always snooze the corresponding sase notification.

### New "snoozed" sase task bead status

- When snoozing a task bead, the operation should accept a required time argument, an optional number of +1s argument,
  and an optional reason argument.
- Make sure these arguments are displayed appropriately across all UI surfaces that currently support showing a sase
  bead's details/metadata.
- When either the task bead has reached the requested number of +1s or the specified time has been reached we send a
  send gate notification.
  - If the number of +1s was reached, we should place the bead in a ready status with a good (preset) reason for
    re-opening the task bead (and let an existing builtin chop handle sending the sase gate notification).
  - If the time was reached, the sase gate notification should be new. The primary button/command should be to close the
    bead with a preset reason where the reason can be overridden by the user. Secondary buttons should exist for
    changing the bead status to ready and for snoozing the bead for a longer amount of time, which should be specified
    by the user.
- Make sure the user is able to snooze sase task beads from all appropriate surfaces (e.g. CLI, TUI, Telegram, etc...).
