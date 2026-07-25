# Chat History - ace-run (a4.w0--plan)

- **TIMESTAMP:** 2026-07-16 07:23:07 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** a4.w0--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-a4_w0__plan-260716_064336.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260716_064336.md`

**Plan:** /home/bryan/.sase/plans/202607/ace_plan_approval_tiers.md


## Prompt

#gh:gh_sase-org__sase The `Tier:` field shown in the "SASE PLAN" section only supports two values today I believe, `plan` and `epic`. That is not correct. We should support three: `plan` (the user approved the plan without committing it), `tale` (the user approved the plan as a tale), or `epic` (the user approved the plan as an epic). Can you help me fix this? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %a:tale %w:a4

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/ace_plan_approval_tiers.md`

> # Plan: Correct ACE SASE PLAN approval tiers
> ## Context
> ACE currently models the SASE PLAN section's effective tier as `plan`, `epic`, or `none`. Its derivation collapses tale
> and commit-only approvals into `plan`, treats an explicitly uncommitted approval as `none`, and maps an authored tale to
> `plan`. That loses the distinction already preserved by the plan-approval protocol: a user can approve without an SDD
> commit, approve and commit as a tale, or approve and commit/launch as an epic.
> This is an ACE presentation-model correction, not an expansion of bead-tier storage. Plan beads continue to use their
> separate `plan`/`epic` execution classification, and the existing canonical-path and phase-roadmap rules remain intact.
> ## Approval-tier contract
> Make explicit approval metadata authoritative over commit success and authored frontmatter:

*See full plan file for details.*

