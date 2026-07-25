# Chat History - ace-run (hy--plan)

- **TIMESTAMP:** 2026-07-22 08:36:44 EDT
- **MODEL:** claude/opus
- **AGENT:** hy--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-hy__plan-260722_082403.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260722_082403.md`

**Plan:** /home/bryan/.sase/plans/202607/claude_cli_orphan_npm_detection.md


## Prompt

#gh:gh_sase-org__sase The agent CLI update for claude code keeps failing (see #sshot). Can you help me diagnose the root cause of this issue and fix it? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
  %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/claude_cli_orphan_npm_detection.md`

> # Plan: Fix Claude Code agent-CLI update failing with exit 217
> ## Symptom
> The ACE comprehensive update ("SASE updated") repeatedly finishes with the warning toast **"⚠ SASE updated with Agent
> CLI issues"** and the line:
> > • Claude Code: failed — command failed with exit 217. See https://code.claude.com/docs/en/installation
> SASE itself updates fine; only the Claude Code agent-CLI leg fails, and it fails on every update attempt.
> ## Root cause (confirmed end-to-end)
> The failure is a **install-method misdetection** caused by a leftover ("orphaned") npm global package coexisting with a
> native Claude Code install. The chain:
> 1. **Claude Code is a _native_ install.** `claude` resolves to `~/.local/bin/claude`, a symlink into

*See full plan file for details.*

