#gh:gh_sase-org__sase Something is wrong with the bead store (see the command output below for context). Can you help me diagnose the root cause of this issue and fix it? When you're done, run the `sase update -y` command to update sase and then run the `sase bead work /home/bryan/.sase/plans/202608/primary_workspace_ownership.md -Y` command to launch the epic that just failed to launch.

#plan 
```
❯ sase bead work /home/bryan/.sase/plans/202608/primary_workspace_ownership.md -Y
Epic plan  /home/bryan/.sase/plans/202608/primary_workspace_ownership.md
✓ Validated       tier: epic · 7 phases · 8 dependency edges
✓ Store           sidecar_repos · beads at /home/bryan/projects/github/sase-org/sase/sase/repos/beads
✓ Archived        /home/bryan/projects/github/sase-org/sase/sase/repos/plans/202608/primary_workspace_ownership.md (already archived)
slow_launch_stage operation=bead_work stage=phase_creation elapsed_ms=200901.7 target=sase-mn
slow_launch_stage operation=bead_work stage=dependency_creation elapsed_ms=170376.8 target=sase-mn
✓ Epic bead       sase-mn — Enforce user-owned primary workspace boundaries
✓ Phase beads     sase-mn.1 Workspace ownership and mutation contract · sase-mn.2 Durable
operational workspace leases · sase-mn.3 Reset-and-replay conflict recovery · sase-mn.4
Approval and task launches off the primary checkout · sase-mn.5 Background bead mutations
off canonical primary clones · sase-mn.6 Generic primary-sidecar auto-sync · sase-mn.7
End-to-end ownership audit and regression gates
✓ Dependencies    8 edges · 5 waves
✓ Plan linked     bead_id: sase-mn ·
/home/bryan/projects/github/sase-org/sase/sase/repos/plans/202608/primary_workspace_owner
ship.md
Epic sase-mn — Enforce user-owned primary workspace boundaries: 7 phase agent(s) in 5 wave(s) plus 1 land agent (sase-mn.land).
  Clan: sase-mn · Tribe: @epic
  Wave 0: sase-mn.1 → sase-mn.1
  Wave 1: sase-mn.2 → sase-mn.2, sase-mn.6 → sase-mn.6
  Wave 2: sase-mn.3 → sase-mn.3
  Wave 3: sase-mn.4 → sase-mn.4, sase-mn.5 → sase-mn.5
  Wave 4: sase-mn.7 → sase-mn.7
  Land waits on: sase-mn.1, sase-mn.2, sase-mn.6, sase-mn.3, sase-mn.4, sase-mn.5, sase-mn.7
No agents were spawned; restoring 8 epic work preclaim(s) and restoring the epic's prior is_ready_to_work state.
Warning: failed to commit restored launch state for sase-mn: cannot publish non-append-only bead event stream sase-mk: worktree rewrote ancestor event 5
Error: epic graph commit failed before agent launch for sase-mn: cannot publish non-append-only bead event stream sase-mk: worktree rewrote ancestor event 5; rollback also failed: could not remove epic sase-mn: cannot publish non-append-only bead event stream sase-mk: worktree rewrote ancestor event 5
Resume with:
  sase bead work /home/bryan/projects/github/sase-org/sase/sase/repos/plans/202608/primary_workspace_ownership.md --yes
```