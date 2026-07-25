# Chat History - ace-run (49--plan)

- **TIMESTAMP:** 2026-07-10 10:24:44 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 49--plan
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260710_101715.md`

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-49__plan-260710_101715.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260710_101715.md`

**Plan:** /home/bryan/.sase/plans/202607/remove_hg_xprompt_references.md


## Prompt

#gh:gh_sase-org__sase I think we might have lingering references to the old `#hg` VCS xprompt workflow, which belonged to the (now obsolete) ../sase-google sase plugin repo. Can you help me remove all of these references? Make sure you are thorough and catch all references. Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.
 %a:tale

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/remove_hg_xprompt_references.md`

> # Remove obsolete `#hg` xprompt references
> ## Goal
> Remove the retired `#hg` workspace-xprompt workflow from SASE's active surface so core no longer documents, recognizes,
> or synthesizes it when no workspace provider registers it. Preserve the provider-neutral workspace architecture: a
> future plugin must still be able to register any workflow name through `WorkflowMetadata` without core code knowing the
> name in advance.
> The repository audit found literal `#hg` references across user documentation, runtime comments/docstrings, generated
> skill source, and tests, plus less-visible behavioral assumptions: `hg` remains in prompt fallback/alias allowlists,
> agent-workflow prefix matching, and the default `vcs_type` for CRS, mentor, fix-hook, and mentor-change workflows. Those
> implicit paths can still classify or emit `#hg` even if all literal examples are removed.

*See full plan file for details.*

