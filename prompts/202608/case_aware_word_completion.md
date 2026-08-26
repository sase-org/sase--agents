- **PLAN:**
  [202608/case_aware_word_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/case_aware_word_completion.md)
- **AGENTS:**
  - [bbugyi200.athena.0e3--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0e3.md)

Can you help me make the common words (i.e. words found in previous prompts) completion
in the prompt input widget smart about how casing is handled and case-insensitive? For
example, if the user is typing `SPECTAC` and uses the `<ctrl+t>` keymap and the correct
and only common words completion is `spectacular`, then we should auto-complete
`SPECTACULAR`.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
