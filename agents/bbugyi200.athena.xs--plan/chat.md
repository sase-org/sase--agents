# Chat History - ace-run (xs--plan)

- **TIMESTAMP:** 2026-08-11 06:28:52 EDT
- **MODEL:** claude/opus
- **AGENT:** xs--plan

**Plan:** /home/bryan/.sase/plans/202608/wait_modal_bead_selection.md


## Prompt

#gh:gh_sase-org__sase Can you help me add support to the `Wait` panel (triggered via the `w` keymap on the agents tab) for selecting beads that an agent should wait for (i.e. the agent shouldn't launch until all of those beads are closed)? I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful! Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %model:opus

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/wait_modal_bead_selection.md`

> # Plan: Select bead wait targets from the Agents-tab Wait panel
> ## Problem
> Bead gating already works end to end everywhere except the one surface where waits are
> edited.
> `%wait(bead=<id>)` parses into `PromptDirectives.wait_beads`
> (`src/sase/xprompt/_directive_values.py:73`), lands in `agent_meta.json` /
> `waiting.json` as `wait_for_beads` (`src/sase/axe/run_agent_wait.py:151`), and is
> resolved by the `wait_checks` chop plus the runner fallback against the waiting agent's
> project bead store (`src/sase/scripts/sase_chop_wait_checks.py:140`,
> `src/sase/axe/run_agent_wait_deps.py:58`). The TUI already renders those waits with live

*See full plan file for details.*

