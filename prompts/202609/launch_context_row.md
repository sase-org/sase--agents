- **PLAN:**
  [202609/launch_context_row.md](https://github.com/sase-org/sase--plans/blob/main/202609/launch_context_row.md)
- **AGENTS:**
  - [bbugyi200.apollo.0s.f0.f0.w2--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.0s.f0.f0.w2.md)

  Can you help me move the `<model>/<effort>` text and `+project` text from the
  top-right middle row to the bottom row (the row below the middle row)?

- These should be on the same row as the agent status counts but to the far right
  instead of the far left.
- For example, in the ~/tmp/screenshots/20260920_154346.png screenshot, it is
  `opus@high` and `+sase` that should be moved one row down.
- The goal of this change is to make that middle row a little less crowded but also to
  give us room to more adequately describe (in some visually appealing and concise way)
  what these two text indicators are meant to indicate.
- As a part of this change, make sure that the tooltips we show when hovering over these
  text indicators have an excellent, concise, and useful description of what each text
  indicator does.
- I expect that the `just fix-tui-screenshots` command will update a lot of screenshots.
  You do NOT need to visually verify all of these.
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
