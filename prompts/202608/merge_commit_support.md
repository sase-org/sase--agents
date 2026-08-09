- **PLAN:**
  [202608/merge_commit_support.md](https://github.com/sase-org/sase--plans/blob/main/202608/merge_commit_support.md)
- **AGENTS:**
  - [bbugyi200.athena.wl--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.wl.md)

I want to stop squashing PR merges by default in my GitHub organizations (I'll do this
myself). Can you help me make sure that sase's VCS commit log functionality (e.g. the
"Commits" sub-tab of the "Artifacts" tab, the `sase vcs log` command, etc...) has
excellent support for merge commits?

- These should be clearly visually marked as merge commits somehow when shown.
- Merge commits should be hidden by default though so we just see the commits that were
  contained in the PR that was submitted.
- I want you to lead the design on this one. Make sure you design this feature so it is
  intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
