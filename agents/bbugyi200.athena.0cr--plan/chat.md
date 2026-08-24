# Chat History - ace-run (0cr--plan)

- **TIMESTAMP:** 2026-08-24 14:06:53 EDT
- **MODEL:** claude/opus
- **AGENT:** 0cr--plan

**Plan:** /home/bryan/.sase/plans/202608/finalizer_sealed_config.md


## Prompt

#gh:gh_sase-org__sase Can you help me figure out why I keep getting these `Step 'main' failed: Error: live refusal policy for 'commit' drifted from the sealed plan` error messages from failes sase agents (see #sshot for context)? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/finalizer_sealed_config.md`

> # Seal the effective finalizer config so a mid-turn host change cannot kill the turn
> ## Symptom
> Agent turns die at the very end with:
> ```
> WorkflowExecutionError: Step 'main' failed: Error: live refusal policy for 'commit'
> drifted from the sealed plan
> ```
> The agent has already done all of its work. The turn is destroyed at finalizer time, no
> commit happens, and the workspace is left dirty with nothing disclosed. On the reporting
> host this killed five agents in one window, including two epic agents that had been

*See full plan file for details.*

