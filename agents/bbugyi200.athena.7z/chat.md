# Chat History - ace-run (7z--plan)

- **TIMESTAMP:** 2026-07-13 11:39:17 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** 7z--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-7z__plan-260713_112704.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260713_112704.md`

**Plan:** /home/bryan/.sase/plans/202607/land_epic_xprompt_integration.md


## Prompt

#gh:gh_sase-org__sase Can you help me improve the `#bd/land_epic` xprompt?

- Instruct the agent that they are responsible for integrating this change into any other changes that were committed since the epic started. It's possible that previous agents didn't integrate with this new feature that this epic added properly because the feature wasn't complete yet.
- Try not to remove anything that is needed from the prompt but look into how you can make it more concise and useful. Every token in context is either helping or hurting us. Other than that I want you to do your own research and lead the design on this one.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.
 %m:claude/claude-fable-5

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/land_epic_xprompt_integration.md`

> # Improve the `#bd/land_epic` xprompt: integration duty + tighter prompt
> ## Context
> `#bd/land_epic` is the built-in xprompt (defined in `src/sase/default_config.yml` under `xprompts:`) rendered for the
> final "land agent" that `sase bead work <epic_id>` launches after every phase agent finishes. Launch mechanics that
> shape the prompt design:
> - The land agent is named `<epic_id>`, waits (`%w`) on all phase agents, runs with `%auto:tale`, and receives
>   `SASE_BEAD_ID=<epic_id>` (`src/sase/bead/work.py::render_multi_prompt`).
> - Because of `%auto:tale`, any plan the land agent submits via `/sase_plan` is auto-approved as an SDD tale and a
>   **follow-up coder agent** executes it — the land agent itself terminates after proposing. Whatever landing steps are
>   not written into that plan never happen.

*See full plan file for details.*

