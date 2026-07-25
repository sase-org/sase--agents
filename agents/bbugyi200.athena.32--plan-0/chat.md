# Chat History - ace-run (32--plan-0)

- **TIMESTAMP:** 2026-07-08 20:45:49 EDT
- **MODEL:** codex/gpt-5.5
- **AGENT:** 32--plan-0

## Linked Chats

- 1. --plan — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-32__plan-260708_202510.md`
- **2. --plan-0** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-32__plan_0-260708_202510.md`
- 3. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260708_202510.md`

**Plan:** /home/bryan/.sase/plans/202607/xprompt_swarms.md


## Prompt

#gh:gh_sase-org__sase sase currently has the concept of multi-agent xprompts that use three dashes to separate prompts that are used to launch different agents. Can you help me do an audit of this codebase, the sase-core repo and all of sase's plugin repos, for any instance of this name being used to describe this concept being used and update the text appropriately to use the name "xprompt swarms" instead, which is the new term I would like to use for these xprompts? You should also update the memory/glossary.md file to use this new name.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.


### Additional Requirements

- Make sure your review is thorough and you catch all references.

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/xprompt_swarms.md`

> # Rename multi-agent xprompts to xprompt swarms
> ## Goal
> Audit the main SASE repo, `sase-core`, and the SASE plugin repos for references to the current concept name "multi-agent
> xprompt" and update the affected prose and code-facing terminology to the new term "xprompt swarm" / "xprompt swarms".
> The requested canonical glossary update is in scope: update `memory/glossary.md`. Because the generated provider
> instruction shims and `AGENTS.md` currently contain the same glossary entry, treat those exact glossary mirrors as in
> scope too, while avoiding unrelated memory or instruction churn.
> ## Scope
> Repos to audit:
> - `sase`

*See full plan file for details.*

