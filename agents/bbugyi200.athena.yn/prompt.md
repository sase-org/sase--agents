#gh:gh_sase-org__sase We recently merged the "Bugs" panel into the "Beads" panel and made it so ALL
external bugs and PRs result in a bead/patch being created for every enabled sase
project (see the sase-jd epic bead for context). Can you now help me refine and improve
this functionality?

- Let's start allowing users to configure bug/PR filters so we only create beads/patches
  for the bugs/PRs that the user wants us to.
- By default, we should continue to match all bugs, but we should start filtering out
  any PRs that were created by release-please or release-plz.
- The chops that sync bugs/PRs with beads/patches are pretty slow right now and seem to
  run over the 300s interval of their lumberjack. Let's move these out into their own
  lumberjack that has a generous interval (review the runtimes of these chops and decide
  how many lumberjacks / what intervals are appropriate).
- We need to start making sure that a bead linked with a bug stays in sync with external
  changes made to that bug (e.g. the STATUS field should be updated if a bug is closed).
  See how we do this for PRs/patches for inspiration.
- Dig for any related bugs / other objective improvements that you can make to this
  feature. If you find any, include those fixes / improvements in your plan.

#plan #m_opus