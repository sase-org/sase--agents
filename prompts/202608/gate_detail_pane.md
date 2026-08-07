- **PLAN:** [202608/gate_detail_pane.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_detail_pane.md)
- **AGENTS:**
  - [bbugyi200.athena.ui--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.ui.md)

Custom sase gate notifications don't currently show any content in the right pane when selected in the notifiction
panel. Can you help me fix this by showing appropriate content in the right pane always?

- It's possible that we'll need to change the expected required parameters for constructing a custom sase gate in order
  to make this work.
- Also let's start grouping these in a tab named `Gates` instead of `HITL`.
- See #sshot for what these notifications look like in the notification panel currrently.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last
  but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate tier,
validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs) before making
any file changes.
