- **PLAN:**
  [202609/fix_tui_screenshots_never_fail.md](https://github.com/sase-org/sase--plans/blob/main/202609/fix_tui_screenshots_never_fail.md)
- **AGENTS:**
  - [bbugyi200.apollo.1i--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.1i.md)

The `just fix-tui-screenshots` command is meant to basically never fail (it should
always figure out a way to update the screenshots that it needs to--or succeed with a
warning otherwise), but seems to be fail sometimes (search throough recent sase agents
on this machine to find evidence of these failures). Can you help me fix this?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
