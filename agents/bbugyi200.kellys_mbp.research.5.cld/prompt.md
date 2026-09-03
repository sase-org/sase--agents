%id(cld, clan=research.5) %wait(priority=20) %m:@research_b #gh:gh_sase-org__sase I've been thinking about ways we could allow sase to dispatch
to other known machines so the user can open up one TUI on one machine and manage all of
their agents across all machines.

- In practice, I plan to use this to manage all (e.g. launch, view, kill, etc...) sase
  agents that are running on any of my Tailscale devices from the `sase ace` TUI on my
  MacBook.
- We can therefore rely on the machines having their names or IP addresses configured
  somewhere and will likely need a lightweight, fast way of communicating between the
  different devices (ZeroMQ would be my choice, but do your own research to determine
  which external framework, if any, we should use).
- Some lag is to be expected across network devices. But, once fully synced, I should be
  able to view and manage (e.g. from the "Agents" tab in the TUI) sase agents running on
  different machines in all of the same ways I can view and manage sase agents that are
  running on the local machine (i.e. the same machine as the TUI).

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution. Make sure that the solution you
recommend is reliable and robust. #research