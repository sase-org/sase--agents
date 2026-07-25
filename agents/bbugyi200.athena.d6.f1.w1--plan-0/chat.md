# Chat History - ace-run (d6.f1.w1--plan)

- **TIMESTAMP:** 2026-07-18 08:41:43 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** d6.f1.w1--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-d6_f1_w1__plan-260718_083125.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260718_083125.md`

**Plan:** /home/bryan/.sase/plans/202607/gate_primary_enter.md


## Prompt

#gh:gh_sase-org__sase When a sase gate is shown in the TUI's notification panel, the `<enter>` key should always trigger the submission of the primary button/option offered by the gate (make sure that every sase gate has to provide this and update all existing sase gates if necessary--e.g. this should be the "Tale" option for tale plan gates and the "Epic" option for epic plan gates), but it currently toggles the "Launch coder agent" option when a tale plan is proposed (the `<space>` keymap can be used for this; `<enter>` should submit the primary option). Can you help me fix this? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %w:d6.f1

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/gate_primary_enter.md`

> # Plan: Make Enter submit every notification gate's primary action
> ## Context
> ACE's shared plan/custom gate controls currently bind Enter to activation of the focused widget. A tale plan opens with
> the `Launch coder agent` checkbox focused, so Enter toggles that checkbox instead of pressing the gate's `Tale` submit
> button. The renderer cannot correct this generically because the durable gate request describes branches and groups but
> does not identify which displayed branch is the primary action.
> The fix should establish one source of truth in the gate protocol and consume it across the TUI. The tale plan primary
> branch is `approve AND commit` and renders as `Tale`; the epic plan primary branch is the singleton `approve` option and
> renders as `Epic`. Existing question, launch, workflow HITL, and custom gate producers also need explicit primary
> declarations so omission or ambiguity is a creation-time error rather than a UI convention based on ordering.

*See full plan file for details.*

