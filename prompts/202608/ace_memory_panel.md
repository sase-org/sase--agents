- **PLAN:**
  [202608/ace_memory_panel.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_memory_panel.md)
- **AGENTS:**
  - [bbugyi200.athena.07j--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07j.md)

I want to add a new memory file panel to the TUI that allows user to
view/add/modify/delete sase memory files from the TUI. Can you help me implement this?

- This panel should support filtering by project and should respect the current project
  (i.e. filter by that project by default--see how we do this on "Artifacts" sub-tabs
  for inspiration).
- This panel should be triggered by the new `<ctrl+g>m` (insert-mode) / `gm`
  (normal-mode) keymaps.
- This panel should support navigating memory files individually but should also support
  jumping to linked (via a memory file's optional `parent` frontmatter field) memory
  files.
- See how the recently added glossary panel (triggerd via the `<ctrl+g>G` / `gG`
  keymaps) works for inspiration.
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
