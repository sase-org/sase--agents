#gh:gh_sase-org__sase %w:sase-ag.land We recently added support for more bullets with links
to rich GitHub pages (like commit URLs or `sase--agents` agent / agent family
README.md files) in sase plan files. See the sase-ag epic bead for some context
behind these new bullets. We also split the beads/ directory out into its own
`sase--beads` sidecar repo (the sase-a8 epic bead for context on this one). Can
you now help me have the `sase commit` command start publishing rich pages to
the new `sase--beads` repo when the current agent is associated with a sase bead?

- These beads GitHub pages should have great GitHub links to related artifacts
  (for example, other bead pages, commits, `sase--agents` agents that
  worked/modified those beads, etc...).
- When the `sase commit` command currently creates a commit that is associated
  with a bead, we automatically append ` (<bead_id>)` to the headline of the
  commit message currently. Instead of doing this, let's start adding a new `SASE_BEAD`
  commit tag to the commit message that links to the corresponding bead page.
- #beau

#plan #m_opus