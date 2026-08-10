#gh:gh_sase-org__sase I'm pretty sure that task beads associated with sase agents that make commits
are sometimes left open.

- If that is true, can you help me fix this by auto-closing task beads associated with a
  sase agent when that agent makes a commit with the `sase commit` command unless the
  new `-B|--do-not-close-bead` CLI option is used.
- Make sure to document this CLI option in the /sase_git_commit xprompt skill. Make sure
  your changes to this skill are minimal (but useful) since every token in context
  either helps or hurts us.

#plan #m_opus