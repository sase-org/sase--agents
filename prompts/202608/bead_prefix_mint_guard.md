- **PLAN:**
  [202608/bead_prefix_mint_guard.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_prefix_mint_guard.md)
- **AGENTS:**
  - [bbugyi200.athena.sf--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sf.md#member-plan)

Why do the beads we create when approving epics for the `bob-cli` sase project have the `gh_bobs-org__bob-cli` prefix
instead of the `bob-cli` prefix (see the output below)? Can you help me diagnose the root cause of this issue and fix
it? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs) before
making any file changes.

```
❯ sase bead work /home/bryan/.sase/plans/202608/priority_property.md -y
Epic plan  /home/bryan/.sase/plans/202608/priority_property.md
✓ Validated       tier: epic · 5 phases · 5 dependency edges
✓ Store           sidecar_repos · beads at /home/bryan/projects/github/bobs-org/bob-cli/sase/repos/beads
✓ Archived        /home/bryan/projects/github/bobs-org/bob-cli/sase/repos/plans/202608/priority_property.md (already archived)
✓ Epic bead       gh_bobs-org__bob-cli-5 — Priority bullet property that rolls a scheduled date
✓ Phase beads     gh_bobs-org__bob-cli-5.1 Config schema for `values: priority` · gh_bobs-org__bob-cli-5.2 Priority value stage and single-task write · gh_bobs-org__bob-cli-5.3
Counted-session priority writes · gh_bobs-org__bob-cli-5.4 Priority-derived suggestion in the date picker · gh_bobs-org__bob-cli-5.5 Docs, version bump, and vault deploy
✓ Dependencies    5 edges · 4 waves
✓ Plan linked     bead_id: gh_bobs-org__bob-cli-5 · /home/bryan/projects/github/bobs-org/bob-cli/sase/repos/plans/202608/priority_property.md
Epic gh_bobs-org__bob-cli-5 — Priority bullet property that rolls a scheduled date: 5 phase agent(s) in 4 wave(s) plus 1 land agent (gh_bobs-org__bob-cli-5.land).
  Clan: gh_bobs-org__bob-cli-5 · Tribe: @epic
  Wave 0: gh_bobs-org__bob-cli-5.1 → gh_bobs-org__bob-cli-5.1
  Wave 1: gh_bobs-org__bob-cli-5.2 → gh_bobs-org__bob-cli-5.2
  Wave 2: gh_bobs-org__bob-cli-5.3 → gh_bobs-org__bob-cli-5.3, gh_bobs-org__bob-cli-5.4 → gh_bobs-org__bob-cli-5.4
  Wave 3: gh_bobs-org__bob-cli-5.5 → gh_bobs-org__bob-cli-5.5
  Land waits on: gh_bobs-org__bob-cli-5.1, gh_bobs-org__bob-cli-5.2, gh_bobs-org__bob-cli-5.3, gh_bobs-org__bob-cli-5.4, gh_bobs-org__bob-cli-5.5
✓ Graph committed epic gh_bobs-org__bob-cli-5 · workers preassigned
✓ Graph published gh_bobs-org__bob-cli-5 · remote
```
