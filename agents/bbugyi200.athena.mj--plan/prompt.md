#gh:gh_sase-org__sase Can you help me figure out why launching this epic failed (see the output below), fix the underlying issue, and then re-run that command to launch the epic? #plan

```
❯ sase bead work ~/.sase/plans/202607/beads_sidecar_repo.md -y

Epic plan  /home/bryan/.sase/plans/202607/beads_sidecar_repo.md
✓ Validated       tier: epic · 10 phases · 16 dependency edges
✓ Store           sidecar_repos · beads at /home/bryan/projects/github/sase-org/sase/sase/repos/plans/beads
✓ Archived        /home/bryan/projects/github/sase-org/sase/sase/repos/plans/202607/beads_sidecar_repo.md (already archived)
Error: failed to commit bead_id sase-a7 to approved plan /home/bryan/projects/github/sase-org/sase/sase/repos/plans/202607/beads_sidecar_repo.md
Resume with:
  sase bead work /home/bryan/projects/github/sase-org/sase/sase/repos/plans/202607/beads_sidecar_repo.md --yes
```