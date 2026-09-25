#gh:gh_sase-org__sase Can you help me add a new `sase bead read` command that agents should be
instructed to use instead of the `sase bead show` command (which is meant for humans
that don't need to be audited)?

- This command should wrap the `sase bead show` command but should require a reason for
  reading the bead be provided by the sase agent via the `-r|--reason` CLI option.
- See how we do this with the `sase memory read/show` commands for context and
  inspiration.
- The goal of this change is to make it easier to trace (in the TUI, for example) when
  and why an agent read a bead.
- This change is meant to complement the recent addition of the `Beads:` sub-sub-section
  in the `ARTIFACTS` sub-section of the `SASE CONTEXT` section in agent metadata panel.
- Had this feature already been implemented, for example, we would be able to see why
  the `0om` sase agent read the `sase-14j` bead (see the
  ~/tmp/screenshots/20260921_104159.png screenshot for context). NOTE: It is possible
  that the `0om` sase agent did not actually read this bead since I'm not sure that
  auditing of bead reads is properly implemented yet (you should look into this).

#plan %m:@xlarge