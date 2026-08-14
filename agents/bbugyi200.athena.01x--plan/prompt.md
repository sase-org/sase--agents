#gh:gh_sase-org__sase Can you help me (a) eliminate procs that run inside the ACE TUI process, make
every proc supervisor-owned and detached, and remove `-d|--detached` from
`sase proc run`; (b) merge sase monitors into sase procs via a new `--shell <name>`
option, with sase monitor wrapping that at the service level; and (c) adopt the taxonomy
agent lane → sase agent, plus agent shell, proc shell, and sase shell?

- See the proc_ownership_and_shell_taxonomy.md file in the research sidecar repo for
  context and inspiration.
- This research file recommends that this work be split up into three epics so I would
  expect (at least) three xlarge phases in the epic plan file you propose.
- Make sure you add excellent (but concise, remember that every token in context either
  helps or hurts us) glossary definitions for sase shell, proc shell, agent shell, and
  sase agent.
- #beau

#plan %m:@smartest