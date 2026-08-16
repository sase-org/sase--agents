- **PLAN:**
  [202608/mid_word_common_word_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/mid_word_common_word_completion.md)
- **AGENTS:**
  - [bbugyi200.athena.03s--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03s.md)

We already support completion for common words used in previous prompts in the prompt
input widget via the `<ctrl+t>` keymap, but this only works when the cursor is at the
end of the word. Can you help me add support for common word completion from the middle
of a word as well?

- We should only consider the text to the left of the cursor when determining completion
  candidates and should add a space in-between the selected word and the text to the
  right when the user selects a completion entry (e.g. by pressing `<enter>`).
- For example, pressing `<ctrl+t>` when the cursor is at `<cursor>` in the text
  `foo<cursor>baz` would trigger completion for `foo`.
- If the user then selects the `foobar` entry, the text should be tranformed to
  `foobar<cursor> baz`.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
