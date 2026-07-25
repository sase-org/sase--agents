# Chat History - ace-run (3w--plan)

- **TIMESTAMP:** 2026-07-09 14:52:23 EDT
- **MODEL:** claude/opus
- **AGENT:** 3w--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-3w__plan-260709_144332.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260709_144332.md`

**Plan:** /home/bryan/.sase/plans/202607/xprompts_memory.md


## Prompt

#gh:gh_sase-org__sase Can you help me add a new memory/xprompts.md file that contains a long-term memory that agents should read whenever working with xprompts or launching sase agents? This memory file should contain practical advice on how all xprompt directives work, how xprompts are invoked in prompts, and how they are defined. This memory file should also describe VCS xprompt workflows (just `git` and `gh`) , which should be included in the agent prompt whenever we launch an agent that is working on a task for a particular sase project. Make sure you take care to keep this memory file short but informative and useful (every token either helps or hurts, so make sure all of the ones you add help).

Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/xprompts_memory.md`

> # Plan: Add `memory/xprompts.md` long-term memory note
> ## Goal
> Add a new **Tier 2 (long-term) memory note** at `memory/xprompts.md` that agents read on demand (via
> `/sase_memory_read`) whenever they work with xprompts / prompt directives **or** launch sase agents. It must cover,
> densely and accurately:
> 1. How xprompts are **invoked** in prompts (`#`/`#!` reference syntax, argument grammar, shorthands).
> 2. How all **prompt directives** (`%`-prefixed) work.
> 3. How xprompts are **defined** (`.md` single-part vs `.yml` workflows; discovery order; swarms).
> 4. **VCS xprompt workflows for git and GitHub (`gh`)** — the workspace + rollover/commit block that should be appended
>    to an agent's prompt whenever we launch an agent to work on a task for a particular sase project.

*See full plan file for details.*

