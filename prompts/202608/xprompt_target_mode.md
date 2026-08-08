- **PLAN:**
  [202608/xprompt_target_mode.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_target_mode.md)
- **AGENTS:**
  - [bbugyi200.athena.vy--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.vy.md)

Can you help me make it much easier to edit existing xprompt definitions from the TUI by
giving the prompt input widget stack a special mode that associates the entire stack
with a particular, already defined xprompt?

- This mode should be automatically activated when loading an xprompt into the prompt
  input widget stack from any surface (e.g. the "Select XPrompt" panel, the "Jump to
  xprompt" panel triggered via the `<ctrl+]>` keymap, etc...) with the appropriate
  xprompt definition targeted.
- If the user presses `<enter>` when the prompt input widget stack is targeting an
  xprompt definition, then a new option should be added to the menu that pops up (which
  normally only pops up when there are multiple prompt input widgets visible) to save
  the new xprompt definition to the targeted xprompt (the user should be able to select
  this option via a single keypress just like the other options).
- If the user selects the option to save the xprompt, we should write it to the
  appropriate location on disk and then commit/push to that repo (make sure we have good
  support for chezmoi--see how we handle writing to chezmoi repos elsewhere for
  inspiration).
- In addition to the chezmoi integration that prompts the user (y/n) whether they want
  to apply the changes, we should also support similar integrations when xprompt memory
  or xprompt skill files are modified (e.g. by prompting the user to run the appropriate
  `sase init` command).
- Make sure that this new prompt input widget stack state and the targeted xprompt have
  excellent visual illustration in the TUI (it should be clear to the user when the
  prompt input widget stack is in this state).
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
