# Chat History - ace-run (32--plan)

- **TIMESTAMP:** 2026-07-08 20:34:22 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** 32--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-32__plan-260708_202510.md`
- 2. --plan-0 — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-32__plan_0-260708_202510.md`
- 3. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260708_202510.md`

**Plan:** /home/bryan/.sase/plans/202607/xprompt_swarms_terminology.md


## Prompt

#gh:gh_sase-org__sase sase currently has the concept of multi-agent xprompts that use three dashes to separate prompts that are used to launch different agents. Can you help me do an audit of this codebase, the sase-core repo and all of sase's plugin repos, for any instance of this name being used to describe this concept being used and update the text appropriately to use the name "xprompt swarms" instead, which is the new term I would like to use for these xprompts? You should also update the memory/glossary.md file to use this new name.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/xprompt_swarms_terminology.md`

> # XPrompt Swarms Terminology Plan
> ## Goal
> Rename the current concept called "multi-agent xprompts" to "xprompt swarms" wherever current repo text describes
> markdown xprompts whose body uses top-level `---` segment separators to launch multiple agent prompts.
> ## Read-Only Audit Summary
> - Main `sase` repo: the old terminology appears in canonical memory, generated instruction files, docs, runtime prose,
>   comments/docstrings, and tests around the Python dispatch-time expansion implementation.
> - `sase-core`: no direct "multi-agent xprompt" or equivalent separator-description hits. Broader hits are generic prompt
>   fan-out / xprompt LSP language and do not name this concept.
> - Plugin repos checked with the required linked-workspace flow:

*See full plan file for details.*

