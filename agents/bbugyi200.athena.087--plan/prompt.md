#gh:gh_sase-org__sase Can you help me add a new functionality to the prompt input widget that
triggers when the user types ` *` (i.e. the `*` character after a space)?

- This text should trigger model alias completion for all of the builtin / user / plugin
  model aliases.
- Once selected, by hitting `<enter>`, the `*` should be transformed/expanded into
  `%m:@<model_alias>`, where `<model_alias>` is the model alias the user selected.
- The goal of this new functionality is to make it very easy (and quick--i.e. as few
  keypresses as possible) to specify which model the user wants the agent to use using a
  model alias.
- This functionality should also trigger when `*` is typed at the beginning of a line.
- #beau

#plan %m:@xlarge