#gh:gh_sase-org__sase Can you help me add a new `H` keymap to the "Launch Control" panel that
triggers a new pop-up panel that allows the user to view all of the previous sase agents
(up to a limit that should be configurable via a new sase config field--default to
remembering the last 10 agents for each model alias) that ran using the selected model
alias?

- Make sure to show useful information about the sase agent, including the model that
  was used, a snippet of the prompt, whether the alias was used via another alias or by
  default because the `%model` directive wasn't used in the prompt, and more...
- #beau

#plan #m_opus