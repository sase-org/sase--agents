# Chat History - ace-run (031--plan)

- **TIMESTAMP:** 2026-08-15 19:52:59 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 031--plan

**Plan:** /home/bryan/.sase/plans/202608/replace_stale_epic_bead_link.md


## Prompt

#gh:gh_sase-org__sase Can you help me have the `sase bead work` command start automatically replacing the `bead` frontmatter field's value instead of failing (see the command output below for context)? Make sure this change gets committed and pushed properly. Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 
```
❯ sase bead work /home/bryan/.sase/plans/202608/high_impact_task_bead_sweep.md -Y
Epic plan  /home/bryan/.sase/plans/202608/high_impact_task_bead_sweep.md
✓ Validated       tier: epic · 7 phases · 10 dependency edges
✓ Store           sidecar_repos · beads at /home/bryan/projects/github/sase-org/sase/sase/repos/beads
✓ Archived        /home/bryan/projects/github/sase-org/sase/sase/repos/plans/202608/high_impact_task_bead_sweep.md (already archived)
Error: plan /home/bryan/projects/github/sase-org/sase/sase/repos/plans/202608/high_impact_task_bead_sweep.md links bead_id sase-mi, but that bead is missing; remove the stale bead_id or restore the bead store
```

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/replace_stale_epic_bead_link.md`

> # Plan: Replace stale epic bead links during plan work
> ## Context
> `sase bead work <epic-plan.md>` currently interprets every non-empty managed `bead_id`
> as a resume request. When the archived plan survived but its linked bead did not, launch
> stops after archiving with an instruction to remove the field manually. The archived
> plan is the durable source of truth, so retrying the original scratch plan continues to
> select that preserved stale link and fails in the same way.
> Valid linked epic beads must continue to resume without duplication. A link to an
> existing non-epic bead remains a consistency error rather than being silently replaced.
> The recovery path must also retain the current launch lock, store-health, commit,

*See full plan file for details.*

