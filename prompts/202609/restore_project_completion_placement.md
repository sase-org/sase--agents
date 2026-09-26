- **PLAN:**
  [202609/restore_project_completion_placement.md](https://github.com/sase-org/sase--plans/blob/main/202609/restore_project_completion_placement.md)
- **AGENTS:**
  - [bbugyi200.apollo.1w--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.1w.md)

When the `+` character is typed after a space or at the beginning of a line in the
prompt input widget or in external editors (via LSP support), we trigger sase project
completion. When a completion item is selected (via the `<ctrl+f>` keymap), we are
supposed to replace any other existing project tags in that prompt. We do seem to
correctly delete any other project tags in the prompt, but we don't move the selected
project tag to where it is supposed to go (the same position in the prompt that the
deleted project tag was--or to the beginning of the prompt, if there was no other
project tag). This just started happening after project tags were implemeneted (I'm
pretty sure this worked perfectly before that). Can you help me confirm/deny my
suspicion, diagnose the true root cause, and fix the issue?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
