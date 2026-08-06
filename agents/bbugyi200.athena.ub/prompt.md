#gh:gh_sase-org__sase We currently already support a robust and reliable set of ways to
auto-generate a dash character prefix (e.g. `- ` or ` -`, depending on the
indentation of the current line) for a bullet in a prompt that is being typed in
the prompt input widget (e.g. via integrations with the `o` / `O` / `<ctrl+j>`
keymaps). Can you now help me add support for doing the same for numbered lists?

- These numbered list bullets should start with `<N>. `, where `<N>` is some
  positive integer that can have zero or more spaces before it (we determine how
  many spaces to use based on the indentation of the current line).
- Make sure this works with all of the same keymaps that work for unordered
  lists.
- Unlike unordered lists, however, we should make sure to auto
  increment/decrement other members of the ordered list when adding a new member
  if necessary.
- #beau

#plan #m_opus