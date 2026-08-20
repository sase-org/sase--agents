#gh:gh_sase-org__sase I would like to add a new "Snippets" panel that allows users to
view/edit/add/delete sase snippets. Can you help me implement this?

- As a part of this change, we should add a new `sase snippet` command. This command
  should support the following sub-commands:
  - `add`: Allows the user to define new snippets.
  - `delete`: Allows the user to delete existing snippets.
  - `list`: List all snippets (should support multiple formats).
  - `show`: Display a single snippet's definition.
- Make sure that the logic used by this new command is shared with this new snippets
  panel.
- Make sure this panel has excellent support for linkage between snippets (a snippet is
  linked to another if it calls that snippet using the special `#[foo]` syntax) and
  provide a keymap that allows us to jump to/from linked snippets.
- The user should be able to trigger this panel from the prompt input widget using the
  new `<ctrl+g>T` (insert-mode) / `gT` (normal-mode) keymaps.
- You should lean heavily on the recently implemented "Glossary" panel (and recently
  implemented `sase glossary` command) for inspiration.
- #beau

#plan