# Chat History - ace-run (43--plan)

- **TIMESTAMP:** 2026-07-10 06:47:27 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 43--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-43__plan-260709_195142.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260709_195142.md`

**Plan:** /home/bryan/.sase/plans/202607/remove_github_local_sdd.md


## Prompt

#gh:gh_sase-org__sase We recently added support to the GitHub VCS xprompt workflow/integration for storing SDD artifacts outside of the main repo in their own distinct repo. We currently support storing SDD files locally as well for GitHub projects but this was always meant to be a temporary state. Can you help me remove support for local SDD files from the GitHub integration? There should be no need for a sase sdd migrate command or a config variable for this anymore.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/remove_github_local_sdd.md`

> # Plan: Make Companion SDD Storage Mandatory for GitHub Workflows
> ## Objective
> Remove local SDD storage as a supported state for GitHub-backed projects. A GitHub `#gh` workflow must resolve to a
> provider-backed companion SDD repository before agent work begins; if that repository cannot be created, adopted, or
> cloned safely, setup must stop with an actionable error instead of writing to a standalone local store.
> This change also retires the user-facing machinery that only existed to choose or transition between storage modes:
> - remove `sase sdd migrate` and its options;
> - remove `--storage` from `sase sdd init`;
> - stop using or writing `sdd.storage` and the legacy `sdd.version_controlled` alias as storage selectors;
> - keep `sdd.repo.name` because it selects the companion repository identity, and keep `sdd.push_after_commit` because it

*See full plan file for details.*

