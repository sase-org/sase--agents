# Chat History - ace-run (08d--plan)

- **TIMESTAMP:** 2026-08-19 18:35:48 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** 08d--plan

**Plan:** /home/bryan/.sase/plans/202608/shell_row_titles.md


## Prompt

#gh:gh_sase-org__sase At some point, we added the requirement that all agent family member nodes have
a name, like xprompt workflow Bash/Python steps do (see the `08b` agent family member
names like `main`, `sase`, and `research-swarm priority check` shown in #sshot). This is
only correct for xprompt workflow Bash/Python steps (which could use the clarity). Sase
shells should NEVER show these names (or have these names at all--check to make sure
there isn't some reason we actually need these, but I don't think we do). Can you help
me start showing these names only for xprompt workflow Bash/Python steps?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:grok-4.6

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/shell_row_titles.md`

> # Plan: Show Agents-tab row titles only for workflow bash/python steps
> ## Problem
> The Agents tab always paints a left-side title on every non-clan row. That title is
> correct for xprompt workflow `bash` / `python` steps (`setup`, `prepare`, `checkout`,
> `diff`), where the step name is the only identity the row has. The same path also titles
> **sase shells** — agent shells and proc shells — so family members look like named
> workflow steps.
> The `08b` family in `.sase/artifacts/home/tmp/screenshots/20260819_180741.png` shows the
> three unwanted titles next to the titles that should stay:
> | Row                                                | What is painted today                                     | What it actually is          | Wanted left-side title               |

*See full plan file for details.*

