# Chat History - ace-run (a4.w0.w0--plan)

- **TIMESTAMP:** 2026-07-16 07:41:59 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** a4.w0.w0--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-a4_w0_w0__plan-260716_071403.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260716_071403.md`

**Plan:** /home/bryan/.sase/plans/202607/required_plan_titles.md


## Prompt

#gh:gh_sase-org__sase %w:a4.w0 Can you help me start having the `sase plan validate` command always require (for both tiers) a `title` property in the frontmatter of the plan file? This title should be displayed as a field in the agent metadata panel's (in the TUI) "SASE PLAN" section (when that section is shown). Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %a:tale

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/required_plan_titles.md`

> # Plan: Require plan titles and show them in agent metadata
> ## Context and product contract
> The authoritative Rust plan validator currently treats `title` as epic-only: the tale schema omits it, a tale can
> validate without it, and a supplied tale title is only an inert-field warning. The CLI's expected-schema table and
> minimal example are generated from that core schema, while proposal, approval, epic creation, and post-cutover
> committed-plan checks reuse the same validation result. Separately, the Agents-tab detail enrichment reads associated
> plan frontmatter into an mtime/size-keyed cache, but its `SASE PLAN` summary carries and renders only the goal, tier,
> path, and (for epics) phases.
> Make frontmatter `title` a required, non-empty string for both authored tiers. Keep frontmatter authoritative: do not
> derive a missing title from the Markdown heading or filename. Strict callers must reject a missing, blank, or non-string

*See full plan file for details.*

