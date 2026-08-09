# Chat History - ace-run (wl--plan)

- **TIMESTAMP:** 2026-08-09 09:42:54 EDT
- **MODEL:** claude/opus
- **AGENT:** wl--plan

**Plan:** /home/bryan/.sase/plans/202608/merge_commit_support.md


## Prompt

#gh:gh_sase-org__sase I want to stop squashing PR merges by default in my GitHub organizations (I'll
do this myself). Can you help me make sure that sase's VCS commit log functionality
(e.g. the "Commits" sub-tab of the "Artifacts" tab, the `sase vcs log` command, etc...)
has excellent support for merge commits?

- These should be clearly visually marked as merge commits somehow when shown.
- Merge commits should be hidden by default though so we just see the commits that were
  contained in the PR that was submitted.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/merge_commit_support.md`

> # Plan: Merge-commit support for the VCS commit log
> ## Why
> The project owner is turning off squash-merge in their GitHub organizations. Once that
> lands, every merged PR leaves behind a merge commit alongside the individual commits it
> contained. SASE's commit-log stack was built for a squash world: the git provider hard
> codes `--no-merges` in `src/sase/vcs_provider/plugins/_git_query_ops.py`, with no way to
> turn it off and no data on the wire that would let any surface even know a commit was a
> merge.
> Today's default is, happily, already the behavior the owner wants: `git log --no-merges`
> still traverses _through_ merges, so every commit a PR contained is shown while the

*See full plan file for details.*

