# Chat History - ace-run (0i--plan)

- **TIMESTAMP:** 2026-07-07 11:57:05 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** 0i--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-0i__plan-260707_114535.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260707_114535.md`

**Plan:** /home/bryan/.sase/plans/202607/gh_first_use_project_display.md


## Prompt

#gh:gh_sase-org__sase When the `#gh` VCS xprompt workflow is used with a new project, the GitHub org and repo need to be specified (ex: `#gh:foo-org/foo`). After this first use however, the user can just use `#gh:foo` to specify this project. The first agent that uses this project should not, however, look special. For example, it should show `foo` as its project, but we seem to be showing `foo-org/foo` instead (see #sshot for a real example with the `bbugyi200/actstat` project). Can you help me fix this? Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.
 %m:claude/claude-fable-5 %a:tale

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/gh_first_use_project_display.md`

> # Plan: First-use `#gh:org/repo` launches should display the repo name as the project, not `org/repo`
> ## Problem
> When the `#gh` VCS xprompt workflow is used with a brand-new project, the user must spell out the GitHub org and repo
> (e.g. `#gh:bbugyi200/actstat`). After that first use, `#gh:actstat` suffices. However, the _first_ agent launched this
> way looks special: the Agents-tab row title and the detail panel's `ChangeSpec:` field show `bbugyi200/actstat`, while
> every subsequent agent for the same project shows just `actstat` (see the real example in the screenshot at
> `.sase/home/tmp/screenshots/20260707_114227.png`).
> ## Root cause
> All launch paths funnel VCS-ref resolution through `resolve_ref_from_prompt()`
> (`src/sase/ace/tui/actions/agent_workflow/_ref_resolution.py`). That function returns the **raw matched ref** as the

*See full plan file for details.*

