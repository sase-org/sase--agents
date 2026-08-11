# Chat History - ace-run (sase-jd.4--plan)

- **TIMESTAMP:** 2026-08-11 06:13:33 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** sase-jd.4--plan

**Plan:** /home/bryan/.sase/plans/202608/external_issue_mirror_1.md


## Prompt

#gh:gh_sase-org__sase
%id(4, clan=sase-jd, bead=sase-jd.4)
%model:@large_worker
%auto
%w(bead=sase-jd.1)
Can you complete the work for bead sase-jd.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close the bead with
`sase bead close sase-jd.4 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself: record discovered
follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-jd.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.
Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/external_issue_mirror_1.md`

> - **PARENT:**
>   [202608/external_artifact_ingestion.md](202608/external_artifact_ingestion.md)
> - **BEAD:** sase-jd.4
> # Plan: Mirror external tracker issues into task beads
> ## Scope and invariants
> Implement phase `issue_mirror` from the external-artifact-ingestion design. The mirror
> is project-scoped by the stable ProjectSpec key and provider-neutral: it uses the
> existing issue-listing capability and `IssueWire`, while tracker-specific commands
> remain inside provider plugins. It creates task beads with status `open`, no size, no
> tier, a normalized `external_ref`, the matching `bug:` reference, the remote body, and

*See full plan file for details.*

