- **PLAN:**
  [202610/repair_agents_archive_view_callouts.md](https://github.com/sase-org/sase--plans/blob/main/202610/repair_agents_archive_view_callouts.md)
- **AGENTS:**
  - [bbugyi200.athena.0zd--plan](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zd.md)

Can you help me fix the ~/.sase/plans/202610/agents_archive_view.md file's validation
errors or, if it is the validation logic that is incorred, fix the validation logic? See
the command output below for context. Think this through thoroughly and create a plan
using your `/sase_plan` skill. Choose and author the appropriate tier, validate and
revalidate until it passes, then submit it with `sase plan propose` (as the skill
instructs) before making any file changes.

```
❯ sase bead work /home/bryan/.sase/plans/202610/agents_archive_view.md -Y
Epic plan  /home/bryan/.sase/plans/202610/agents_archive_view.md
✓ Validated       tier: epic · 8 phases · 10 dependency edges
✓ Store           sidecar_repos · beads at /home/bryan/projects/github/sase-org/sase/sase/repos/beads
Error: could not archive epic plan /home/bryan/.sase/plans/202610/agents_archive_view.md: committed plan validation failed:
/home/bryan/.sase/plans/202610/agents_archive_view.md:259: error [decision-branch-unknown] decision callout names unknown decision `view*name`
/home/bryan/.sase/plans/202610/agents_archive_view.md:943: error [decision-branch-unknown] decision callout names unknown decision `glossary*archive_term`
Resume with:
  sase bead work /home/bryan/.sase/plans/202610/agents_archive_view.md --yes
```
