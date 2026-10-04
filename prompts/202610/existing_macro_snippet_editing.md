- **PLAN:**
  [202610/existing_macro_snippet_editing.md](https://github.com/sase-org/sase--plans/blob/main/202610/existing_macro_snippet_editing.md)
- **AGENTS:**
  - [bbugyi200.athena.0w7--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0w7.md)

I want to make it easier for the user to edit an existing macro / snippet using the
`<ctrl+g>x` / `<ctrl+g>t` keymaps, respectively, in the prompt input widget. Can you
help me accomplish this by adding a new `e` (existing) option to the panel that pops up
prompting the user to select a macro/snippet storage location when they use one of these
keymaps?

- If the user selects this option, they should be able to then fuzzy search for and
  select an existing macro/snippet (defined in any one of the supported files).
- Also, make sure that attempting to redefine an existing macro/snippet in any file
  (e.g. attempting to override a builtin macro by defining one of the same name in a
  user config file, for example) displays a useful warning message to the user
  (regardless of what storage location they chose).
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
