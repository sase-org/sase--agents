# Chat History - ace-run (a--plan)

- **TIMESTAMP:** 2026-07-06 13:13:45 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** a--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-a__plan-260706_130018.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260706_130018.md`

**Plan:** /home/bryan/.sase/plans/202607/humanize_prompt_display_surfaces.md


## Prompt

#gh:gh_sase-org__sase We still seem to be showing weird project names used as arguments to the `#gh` VCS xprompt workflow in prompt history (see #sshot for an example of this bad behavior). The project name that is configured in the project spec file should be used for all user-facing prompts. Can you help me fix this? Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.
 %m:claude/claude-fable-5 %a:tale

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/humanize_prompt_display_surfaces.md`

> # Plan: Show Configured PROJECT_NAME in All User-Facing Prompt Displays
> ## Problem
> Canonical project directory keys (e.g. `gh_sase_org__sase`) still leak into user-facing prompt displays instead of the
> configured `PROJECT_NAME` from the project spec (e.g. `sase`). Example (screenshot 20260706_125758): the Revive Agents
> modal shows `[agent] gh_sase_org__sase` in list rows and the preview header, and the response preview renders the
> recorded prompt as `#gh:gh_sase_org__sase @sdd/tales/...`.
> ### Root cause
> Prompts are deliberately canonicalized at the launch boundary (`canonicalize_project_aliases_in_prompt` — e.g.
> `src/sase/llm_provider/preprocessing.py:96`, `src/sase/ace/tui/actions/agent_workflow/_launch_body_impl.py:89`), so
> every stored artifact (prompt-history entries, chat-history markdown written by

*See full plan file for details.*

