#gh:gh_sase-org__sase The `<ctrl+j>` keymap in the prompt input widget currently auto-inserts
a (properly indented) bullet if the current line belongs to a bullet. This is
normally what we want, but can sometimes be annoying since, when the user wants
to end the bullet list, they are likely to just hit `<ctrl+j>` and expect to be
able to do it that way. Can you help me make it so hitting `<ctrl+j>` twice
(i.e. `<ctrl+j><ctrl+j>`) works for this use-case by making it so the 2nd time
the user presses `<ctrl+j>` the current line (this line should have been created
by the first `<ctrl+j>` and should contain `- ` with some optional leading space
and no bullet contents) is cleared and a new newline is added (so the cursor
should be on a new line 2 lines below the line they were on before pressing
`<ctrl+j>` for the first time?

#plan