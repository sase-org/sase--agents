# Chat History - ace-run (a6--plan)

- **TIMESTAMP:** 2026-07-16 07:50:39 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** a6--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-a6__plan-260716_074604.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260716_074604.md`

**Plan:** /home/bryan/.sase/plans/202607/glossary_project_key.md


## Prompt

#gh:gh_sase-org__sase I think there is some conflicting information in the memory/glossary.md file regarding project spec file names. These files are stored in `~/.sase/project/<project>/<project>.sase` files, but `<project>` is often (in particular for GitHub projects that use the `#gh` VCS xprompt workflow) not equivalent to the project name (ex: for the `sase` sase project, the project spec file is `~/.sase/projects/gh_sase-org__sase/gh_sase-org__sase.sase`). Can you help me make these instructions clearer / more accurate? Remember to keep things concise (every token in context either helps or hurts us). Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %a:tale %m:claude/claude-fable-5

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/glossary_project_key.md`

> # Plan: Clarify project directory key vs project name in the glossary memory
> ## Context
> `memory/glossary.md` (Tier 1, always loaded) says a project's ProjectSpec is `~/.sase/projects/<name>/<name>.sase`. The
> path segment is actually the project **directory key**, which equals the user-facing name only for `#git:<name>`
> projects. `#gh:<org>/<repo>` projects use `gh_<org>__<repo>` — ex: the `sase` project's spec is
> `~/.sase/projects/gh_sase-org__sase/gh_sase-org__sase.sase`, with `PROJECT_NAME: sase` inside. The ChangeSpec entry has
> the same `<project>` placeholder problem and additionally says specs are stored in `.gp` files: the canonical extension
> today is `.sase` (`.gp` is a legacy fallback only — see `src/sase/workflows/utils.py:14`), and active ChangeSpecs live
> inside the ProjectSpec file itself.
> Verified facts to rely on:

*See full plan file for details.*

