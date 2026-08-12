- **PLAN:**
  [202608/external_mirror_refinement.md](https://github.com/sase-org/sase--plans/blob/main/202608/external_mirror_refinement.md)
- **AGENTS:**
  - [bbugyi200.athena.yn--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.yn.md)

We recently merged the "Bugs" panel into the "Beads" panel and made it so ALL external
bugs and PRs result in a bead/patch being created for every enabled sase project (see
the sase-jd epic bead for context). Can you now help me refine and improve this
functionality?

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

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
