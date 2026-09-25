#gh:gh_sase-org__sase Can you help me add a new functionality to the prompt input widget that
triggers when the user types ` *` (i.e. the `*` character after a space)?

- This text should immediately expand to `%m:@`, which should trigger model alias
  completion.
- The goal of this new functionality is to make it very easy (and quick--i.e. as few
  keypresses as possible) to specify which model the user wants the agent to use using a
  model alias.
- This functionality should also trigger when `*` is typed at the beginning of a line.

#plan