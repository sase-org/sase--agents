#gh:gh_sase-org__sase Why did the `16h.f0` sase agent start before the `16h` sase agent finished its
work? The `16h.f0` sase agent had `fork:16h` in its prompt so I was expecting it to wait
for the `16h` sase agent to complete before starting. With that said, since we have the
ability to specify that coder agents wait for another agent (in the coder options for a
tale's gate in the TUI, for example), it would be useful to be able to specifify whether
an agent should target the agent session or the currently running turn for that agent
(this seems to be what the `16h.f0` sase agent targeted). Can you help me implement
this?

- We could implement this with a new `target=<target>` input on the `fork` macro.
- The `<target>` input value would be required to be either "session" or "turn" (with a
  default of "session"). We should enforce this using an enum macro input type (this is
  the same type we use for inputs that accept model names I believe).
- Review the fork_wait_session_vs_turn_target.md file in the research sidecar repo for
  context and inspiration before planning. I agree with all of the requirements
  recommended in that research file (but keep in mind that you are responsible for
  planning and splitting up this work appropriately).

#plan %m:@xlarge %w:research.5j.linker