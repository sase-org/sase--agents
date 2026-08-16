# Chat History - ace-run (02w--plan)

- **TIMESTAMP:** 2026-08-15 18:55:36 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** 02w--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-02w__plan-260815_184829.md`
- 2. --code — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-02w__code-260815_184829.md`

**Plan:** /home/bryan/.sase/plans/202608/launch_control_panel.md


## Prompt

#gh:gh_sase-org__sase Can you help me make the "Models" panel (shown in #sshot) look a bit better and
also add a new launch setting?

- Let's get rid of the entire first column (which contains values like `role` or
  `bucket`, for example).
- The new launch setting we add should correspond with the sase config field that we use
  to configure the number of phases allowed in an epic before we consider it to be a
  "big" epic.
- Let's start adding a single blank line between each section.
- Let's rename this panel to something more appropriate, considering that we can do more
  than configure models from this panel. Think hard about this.
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202608/launch_control_panel.md`

> # Refine the Models panel into Launch Control
> ## Goal
> Turn the existing ACE `,m` modal into a clearer, more polished control surface for
> agent-launch behavior. The finished panel should be named **Launch Control**, remove the
> redundant row-kind column, separate its visible sections with one blank row, and expose
> `bead.big_epic_phase_threshold` as a safe persistent launch setting.
> The change must preserve the existing model-alias, effort, runner-limit,
> provider-disable, bucket, temporary-override, and persistent-edit behavior. Keep the
> internal `ModelsPanel` class/module names, `models_panel` action ID, CSS/widget IDs, and
> legacy action compatibility stable; this is a user-facing rename, not a risky

*See full plan file for details.*

