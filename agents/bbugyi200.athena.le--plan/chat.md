# Chat History - ace-run (le--plan)

- **TIMESTAMP:** 2026-07-26 07:55:32 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** le--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-le__plan-260726_073500.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-le__code-260726_073500.md`

**Plan:** /home/bryan/.sase/plans/202607/deprioritize_epic_agents.md


## Prompt

#gh:gh_sase-org__sase Can you help me add `%wait(priority=15)` to the `#bd/land_epic` and `#bd/next` xprompts so agents that are associated with epics are prioritized below new agents that the user launches without specifying a priority (since `priority` defaults to 10)? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/deprioritize_epic_agents.md`

> # Plan: Deprioritize Epic-Associated Built-in XPrompts
> ## Goal
> Make agents launched through `#bd/land_epic` and `#bd/next` yield runner-slot admission to newly launched agents that
> use the implicit priority of `10`, while preserving the existing bead-selection, implementation, integration, and
> landing instructions.
> ## Context
> Both built-ins are config-backed xprompts defined in `src/sase/default_config.yml`. Xprompt bodies are expanded before
> launch directives are extracted, so a `%wait(priority=15)` directive authored at the start of each body becomes launch
> metadata and is stripped before the prompt reaches the model. Runner-slot admission gives lower numeric values
> precedence; therefore explicit priority `15` is below the default priority `10` and receives the existing bounded

*See full plan file for details.*

