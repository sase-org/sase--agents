# Chat History - ace-run (y--plan)

- **TIMESTAMP:** 2026-07-06 22:40:54 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** y--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-y__plan-260706_222644.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260706_222644.md`

**Plan:** /home/bryan/.sase/plans/202607/sase_run_skill_prompt_guidance.md


## Prompt

#gh:gh_sase-org__sase Can you help me change the instructions for the /sase_run skill to tell the agent to think hard about whether it should use the wait directive and about what VCS xprompt workflow to use and with which project (or, occasionally, ChangeSpec)? In general make sure that the agent is aware of xprompts and what they are capable of. Use your best judgment on what to include and what not to include here. Every token counts, for better or worse. Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.
 %m:claude/claude-fable-5

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/sase_run_skill_prompt_guidance.md`

> # Plan: Teach the /sase_run skill to compose better launch prompts
> ## Context
> The `/sase_run` skill (source: `src/sase/xprompts/skills/sase_run.md`) tells agents how to request a SASE agent launch
> through `LaunchApproval` (`sase launch request`). Today it covers the request mechanics, family-member naming, and
> outcome handling — but says nothing about how to _compose_ the requested prompt. Agents therefore don't deliberate
> about:
> 1. **The wait directive** (`%w`/`%wait`) — whether the new agent should park until another agent lands successfully.
> 2. **The VCS workspace xprompt** (`#gh:`/`#git:`/`#hg:`/`#cd:`) — where the new agent runs, and whether the ref should
>    be a project name or (occasionally) a ChangeSpec name.
> 3. **xprompts in general** — that the requested prompt is a full sase prompt where `#` references expand templates and

*See full plan file for details.*

