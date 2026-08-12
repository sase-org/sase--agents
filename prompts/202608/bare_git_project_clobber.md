- **PLAN:**
  [202608/bare_git_project_clobber.md](https://github.com/sase-org/sase--plans/blob/main/202608/bare_git_project_clobber.md)
- **AGENTS:**
  - [bbugyi200.athena.yh--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.yh.md)

The "sase" sase project keeps getting converted to a bare-git project (i.e. the
`WORKSPACE_DIR` key in the ~/.sase/projects/gh_sase-org**sase/gh_sase-org**sase.sase
file is changed to point to a ~/projects/git/ directory and the `BARE_REPO_DIR` key is
added). I'm not sure what's causing this. Can you help me diagnose the root cause of
this issue and fix it so this doesn't happen anymore? Think this through thoroughly and
create a plan using your `/sase_plan` skill. Choose and author the appropriate tier,
validate and revalidate until it passes, then submit it with `sase plan propose` (as the
skill instructs) before making any file changes.
