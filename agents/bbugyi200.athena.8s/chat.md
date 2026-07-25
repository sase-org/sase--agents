# Chat History - ace-run (8s--plan)

- **TIMESTAMP:** 2026-07-15 08:13:14 EDT
- **MODEL:** claude/opus
- **AGENT:** 8s--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-8s__plan-260715_080033.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260715_080033.md`

**Plan:** /home/bryan/.sase/plans/202607/agent_panel_plan_goal.md


## Prompt

#gh:gh_sase-org__sase We can be sure that sase plan files now contain a `goal` property in their frontmatter (see the sase-61 epic bead for context), so it would be nice to show that goal somewhere prominently when an agent row (root or child) is associated with that plan. Can you help me start showing this goal somewhere in the agent metadata panel on the "Agents" tab of the `sase ace` TUI?

I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful! Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/agent_panel_plan_goal.md`

> # Plan: Show the plan `goal` in the Agents-tab metadata panel
> ## Context
> Since the sase-61 epic, SASE plan files carry a structured `goal` string in their YAML frontmatter (authored per the
> `/sase_plan` skill; required for both `tale` and `epic` tiers). The `goal` is the single best one-line answer to "what
> outcome is this work driving toward." Today that intent is invisible in the TUI: when you highlight an agent on the
> **Agents** tab of `sase ace`, the metadata panel shows identity/lifecycle fields (Name, Bead, ChangeSpec, Model,
> Timestamps, …) but never the goal of the plan the agent is executing or drafting.
> This plan adds a **`Goal:`** field to that metadata panel, shown whenever the selected agent row — root or child — is
> associated with a plan file that has a `goal`. It must be **intuitive** (reads naturally next to the existing
> work-identity fields), **reliable** (correctly resolves the agent's plan across the several ways agents link to plans,

*See full plan file for details.*

