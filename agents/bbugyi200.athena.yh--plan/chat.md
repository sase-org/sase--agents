# Chat History - ace-run (yh--plan)

- **TIMESTAMP:** 2026-08-12 09:48:45 EDT
- **MODEL:** claude/opus
- **AGENT:** yh--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-yh__plan-260812_093908.md`
- 2. --code — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-yh__code-260812_093908.md`

**Plan:** /home/bryan/.sase/plans/202608/bare_git_project_clobber.md


## Prompt

#gh:gh_sase-org__sase The "sase" sase project keeps getting converted to a bare-git project (i.e. the `WORKSPACE_DIR` key in the ~/.sase/projects/gh_sase-org__sase/gh_sase-org__sase.sase file is changed to point to a ~/projects/git/ directory and the `BARE_REPO_DIR` key is added). I'm not sure what's causing this. Can you help me diagnose the root cause of this issue and fix it so this doesn't happen anymore? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/bare_git_project_clobber.md`

> # Stop `#git:` refs from converting existing projects into bare-git projects
> ## Problem
> The `sase` project (ProjectSpec key `gh_sase-org__sase`, a GitHub project) repeatedly
> gets silently converted into a bare-git project: its `WORKSPACE_DIR` is rewritten from
> the real GitHub checkout to a `~/projects/git/<key>/` path, and a `BARE_REPO_DIR` field
> is added. The user repairs the spec by hand; a later launch converts it again.
> ## Verified root cause
> Reproduced end to end in an isolated `HOME`/`SASE_HOME` sandbox. Given a spec file
> containing only:
> ```text

*See full plan file for details.*

