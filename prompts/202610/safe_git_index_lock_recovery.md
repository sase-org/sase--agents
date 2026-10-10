- **PLAN:**
  [202610/safe_git_index_lock_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202610/safe_git_index_lock_recovery.md)
- **AGENTS:**
  - [bbugyi200.athena.0zf--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zf.md)

We continue to have issues (mainly TUI update failures) that stem from `.git/index.lock`
files still existing. I don't know how these files get left behind but I thought that we
added retry logic that eventually deleted that file when necessary. We should never
block on this type of error since the only thing I've ever done to fix these in the past
is delete that file `.git/index.lock` file. With that said, we should try and be as safe
as possible and only do this when it's really necessary. See the TUI update failure in
the ~/tmp/git_index_lock_failure.txt file for context. Can you help me fix this?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose
and author the appropriate tier, validate and revalidate until it passes, then submit it
with `sase plan propose` (as the skill instructs) before making any file changes.
