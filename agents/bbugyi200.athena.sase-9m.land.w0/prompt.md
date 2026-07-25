#gh:gh_sase-org__sase %w:sase-9m.land Can you help me start treating raw placeholders (i.e.
`<foobar>` without surrounding backticks) in the prompt input widget like input
arguments?

- If the user attempts to submit a prompt with them, they should be prompted for
  the values that should be replace each of the unique raw placeholders that
  were found in the prompt.
- We should display these input prompts on a new panel (or re-use an existing
  panel if it closely fits this use-case) all on the same page.
- Also, if the user attempts to create a new local (e.g. the `<ctrl+g>X` keymap)
  or global (e.g. the `<ctrl+g>` keymap) xprompt using the contents of the
  current prompt input widget / prompt input widget stack, the unique
  placeholder values should be used to determine the names of the new xprompt's
  input arguments, which should all be given a type of `text` (the user can
  change them manually if needed).
- #beau

#plan