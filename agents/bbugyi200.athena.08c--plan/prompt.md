#gh:gh_sase-org__sase Can you help me complete sase's new remote dispatch feature?

- Review the tailnet_dispatch_setup/tailnet_dispatch_setup.md file in the research sidecar repo for context and inspiration
  before planning.
- Note that it seems like we probably need to add a new `sase machine bootstrap` command
  as well (see the `088.f0` sase agent's chat for context).
- Once you are confident that the work is done, initialize sase's remote dispatch config
  by running the appropriate command(s) and then end-to-end test this feature by
  launching 1-3 remote agents (think hard about the appropriate way to end-to-end test
  this functionality) on my Apollo machine and attempting to manage those agents
  remotely from this machine using the TUI (after finishing this feature, updating this
  machine's and the apollo machine's versions of sase, and restarting `sase axe` on both
  machines, you can use the `sase ace --tmux` command to launch a TUI on this machine in
  a new tmux pane and then emulate keypresses to that pane, for example).

#plan %m:claude-fable-5