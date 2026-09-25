#gh:gh_sase-org__sase Can you help me migrate the `Model:` field in the agent metadata panel to
`Shells:` when an agent family is selected (we should continue to use `Model:` when an
agent shell is selected) since not every shell is associated with a model?

- Monitors (i.e. proc shells), for example, do not have a model associated with them.
- As part of this change let's stop showing the model for monitor shell entries of this
  `Shells:` field.
- Instead, let's display the command that was used for the monitor if it is short enough
  to display on one line. Otherwise (if the command is too long to show on one line), we
  should show the reason string that was provided to the `sase monitor` command. Make
  sure we wrap this reason string across multiple lines if it is too long in a visually
  appealing way.
- #beau

#plan