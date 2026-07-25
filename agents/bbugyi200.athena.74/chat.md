# Chat History - ace-run (74--plan)

- **TIMESTAMP:** 2026-07-12 15:41:33 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** 74--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-74__plan-260712_152745.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260712_152745.md`

**Plan:** /home/bryan/.sase/plans/202607/amd_agents_template.md


## Prompt

#gh:gh_sase-org__sase Is there a single markdown template that I can edit to change the base contents used by the `sase memory init` command for the agent files (e.g. AGENTS.md)? Ideally this exists because we want to make it easy for humans to edit this content. If not, use your /sase_plan skill to plan the appropriate changes.
 %m:claude/claude-fable-5

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/amd_agents_template.md`

> # Plan: Extract the `sase memory init` AGENTS.md Skeleton into a Human-Editable Markdown Template
> ## Problem / Product Context
> Users want a single markdown file they can edit to change the base ("skeleton") contents that `sase memory init` writes
> into agent instruction files (`AGENTS.md` plus its byte-for-byte provider copies `CLAUDE.md`, `GEMINI.md`, `QWEN.md`,
> `OPENCODE.md`). Today no such template exists — the skeleton is hardcoded as Python string lists, so changing prose like
> the "IMPORTANT: You should not modify..." preamble or the Tier 1/Tier 2 intro text requires editing Python code. That is
> a poor editing experience for humans and hides agent-facing prose (which deserves the same review attention as any other
> prompt text) inside rendering logic.
> ## Current State
> - **Managed skeleton** — `src/sase/amd/_memory.py::_render_managed_agents` hardcodes the full document frame:

*See full plan file for details.*

