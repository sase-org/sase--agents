#gh:gh_sase-org__sase Why do I still see 3 procs running on my machine for the service procs added by
the sase-11y epic bead (see the ~/tmp/screenshots/20260920_154346.png screenshot for
context)?

- Service procs are not supposed to have gear indicators associated with them.
- Also, when I update sase via the `,E` keymap, I receive a toast saying that the TUI
  will restart when those 3 procs finish running. This is wrong since service procs
  should never terminate (so the TUI never auto-reestarts).
- Strangely, neither of these symptoms are occurring on my apollo machine.

Can you help me fix these issues? #plan