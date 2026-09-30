- **PLAN:**
  [202609/unread_ack_reliability_and_tui_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202609/unread_ack_reliability_and_tui_responsiveness.md)
- **AGENTS:**
  - [bbugyi200.athena.0uc--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0uc.md)

I just used the `,u` keymap on the "Agents" tab to mark all unread nodes as read, but it
didn't seem to work (see the ~/tmp/screenshots/20260930_060248.png screenshot for
context). The unread indicators have been a bit flakey in general and always very slow
(when using the `,j` keymap, for example). I would like to make the TUI much more
responsive when working with these indicators. I'm not sure how to implement this, but
my first thought was that we could use a proc to run any expensive work (anything that
causes a delay in the TUI) in the background.

Can you help me fix this issue and make the TUI more responsive in general by
implementing the changes recommended in the
unread_ack_reliability_and_tui_responsiveness.md file in the research sidecar repo?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
