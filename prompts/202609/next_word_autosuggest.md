- **PLAN:**
  [202609/next_word_autosuggest.md](https://github.com/sase-org/sase--plans/blob/main/202609/next_word_autosuggest.md)
- **AGENTS:**
  - [bbugyi200.athena.0u0--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u0.md)

Can you help me make the next word prediction/completion we recently added to the prompt
input widget available in more contexts and without needing to press `<ctrl+t>` to see
the ghost text?

- See the sase-1cj epic bead for context on this new next word prediction/completion
  functionality.
- It's fine to move the existing functionality that we support when `<ctrl+t>` is
  pressed after a space to some other unused keymap (I don't use this functionality
  much).
- Also, is ghost text always able to be shown? Even when typing in the middle of a
  sentence? If not, find another visually appealing way to offer the next word to the
  user when appropriate.
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
