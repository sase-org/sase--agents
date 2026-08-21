# Chat History - ace-run (099--plan)

- **TIMESTAMP:** 2026-08-21 09:18:25 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 099--plan

**Plan:** /home/bryan/.sase/plans/202608/retire_artifact_links.md


## Prompt

#gh:gh_sase-org__sase Can you help me review the `artifact_links` feature flag (see @bead:sase-r8 for context), thoroughly end-to-end test the corresponding functionality, complete any remaining work, fix any discovered bugs, remove the `artifact_links` feature flag (and the old, deprecated code), and close the corresponding "feature" task bead? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/retire_artifact_links.md`

> # Plan: Graduate artifact links and retire the beta flag
> ## Outcome
> The behavior introduced by `sase-r8` becomes the only artifact-link implementation:
> - `sase artifact link add|list|rm|migrate-notes`, audited `sase artifact read` edges,
>   prompt-ref `cites` rows, Markdown `Links` / `Referenced By` projections, artifact
>   doctor checks, bead-event truth, and ACE relationship panes work without
>   `-f artifact_links` or configuration.
> - The deprecated flag-off path and v1-only Referenced By implementation are gone after
>   every live sidecar index is proven to be schema v2.
> - Current workspaces resolve the canonical ProjectSpec key before any artifact-link

*See full plan file for details.*

