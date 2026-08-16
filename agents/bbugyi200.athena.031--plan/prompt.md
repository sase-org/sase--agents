#gh:gh_sase-org__sase Can you help me have the `sase bead work` command start automatically replacing the `bead` frontmatter field's value instead of failing (see the command output below for context)? Make sure this change gets committed and pushed properly. #plan 
```
❯ sase bead work /home/bryan/.sase/plans/202608/high_impact_task_bead_sweep.md -Y
Epic plan  /home/bryan/.sase/plans/202608/high_impact_task_bead_sweep.md
✓ Validated       tier: epic · 7 phases · 10 dependency edges
✓ Store           sidecar_repos · beads at /home/bryan/projects/github/sase-org/sase/sase/repos/beads
✓ Archived        /home/bryan/projects/github/sase-org/sase/sase/repos/plans/202608/high_impact_task_bead_sweep.md (already archived)
Error: plan /home/bryan/projects/github/sase-org/sase/sase/repos/plans/202608/high_impact_task_bead_sweep.md links bead_id sase-mi, but that bead is missing; remove the stale bead_id or restore the bead store
```