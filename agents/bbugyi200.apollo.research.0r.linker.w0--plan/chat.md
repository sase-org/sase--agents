# Chat History - ace-run (research.0r.linker.w0--plan)

- **TIMESTAMP:** 2026-10-09 18:49:34 EDT
- **MODEL:** codex/gpt-6-astra
- **AGENT:** research.0r.linker.w0--plan

**Plan:** /home/bryan/.sase/plans/202610/muse_workflow_reply_streaming.md


## Prompt

#gh:gh_sase-org__sase Muse reply streaming is still not working correctly. I never see any text in a
Muse sase agent's "Reply" card until that agent completes. Can you help me fix this?
Review the muse_reply_card_follow_skips_workflow_agents.md file in the research sidecar repo for context and inspiration
before planning.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:gpt-6-astra %auto %w:research.0r.linker

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202610/muse_workflow_reply_streaming.md`

> # Restore live Reply updates for workflow-backed Muse agents
> ## Outcome
> When an active Muse agent writes assistant text to `live_reply.md`, its selected Reply
> card must display and extend that text before the provider exits or the agent becomes
> DONE. This must work for workflow-backed agent rows, workflow agent steps, and the
> current agent turn shown inside a sequential session, as well as the existing RUNNING
> row shape. Watcher delivery and the existing polling backstop must both work without
> selection changes, pending tools, or full agent reloads.
> This is a medium tale: one coding agent can make the small presentation fix and add the
> loader-to-mounted-TUI regressions needed to prove it. There are no separate

*See full plan file for details.*

