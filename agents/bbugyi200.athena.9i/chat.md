# Chat History - ace-run (9i--plan)

- **TIMESTAMP:** 2026-07-15 13:52:52 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 9i--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-9i__plan-260715_134501.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260715_134501.md`

**Plan:** /home/bryan/.sase/plans/202607/agents_sase_plan_metadata.md


## Prompt

#gh:gh_sase-org__sase We recently added the new goal field to the metadata panel on the agents tab, which is shown when the agent has proposed a plan, which always has the goal property in their frontmatter now. The top-level fields in the agent metadata panel do not feel like the right place for this though. Can you help me add a new `SASE PLAN` section to the metadata panel that is shown when an agent has proposed a plan? 

- We should stop showing the "Goal:" section in the metadata panel. Instead the `goal` will be listed under this section.
- We will also list two other fields: `tier` and `path`
- `tier` should be either `plan`, `epic`, or `none` (if the user specified that the plan should be approved but not committed).
- `path` should be the path to the plan file, which should be relative to the agent's workspace directory (e.g. `sase/repos/plans/202607/ace_prompt_input_demo.md`) or, iff the plan file was not committed, absolute (e.g. `~/.sase/plans/202607/ace_prompt_input_demo.md`).
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/agents_sase_plan_metadata.md`

> # Plan: Add a SASE PLAN section to agent metadata
> ## Product contract
> Replace the selected agent's top-level `Goal:` row with a dedicated `SASE PLAN` major section. Place it immediately
> after the ordinary agent identity/runtime fields (ending with `Timestamps`) and before other optional major sections so
> the panel reads as agent context first, plan context second, and execution outputs afterward. Omit the entire section
> when the agent has no known plan association.
> Render exactly three labeled rows in this order:
> 1. `Goal:` contains the complete normalized frontmatter goal. Preserve the existing responsive behavior: no truncation,
>    hanging indentation, Unicode- aware folding, and an 80-cell maximum line width on wide panels.
> 2. `Tier:` is the user-facing enum `plan`, `epic`, or `none`. While a proposal is awaiting a decision, map authored

*See full plan file for details.*

