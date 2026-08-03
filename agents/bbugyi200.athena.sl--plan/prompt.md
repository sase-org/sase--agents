#gh:gh_sase-org__sase Can you help me start wrapping the description/note text displayed by
the `sase bead show` command at a specific line length?

- Default to 120 characters, but add a new CLI option to make this configurable.
- Also, let's remove the `-S|--style` options supported `color` value (which
  seems to be same as `rich`) and change the short-option for this CLI option
  from `-S` to `-s`.
- Make sure we don't wrap URLs or inline code snippets (ex: `foo bar baz`).
- #beau

#plan #m_opus