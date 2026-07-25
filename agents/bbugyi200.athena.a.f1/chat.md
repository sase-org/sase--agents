# Chat History - ace-run (a.f1--plan)

- **TIMESTAMP:** 2026-07-06 14:44:01 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** a.f1--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-a_f1__plan-260706_142311.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260706_142311.md`

**Plan:** /home/bryan/.sase/plans/202607/eradicate_raw_project_keys.md


## Prompt

#gh:gh_sase-org__sase #fork:a I am still seeing "gh_sase-org__sase" in parts of the UI (see #sshot). Let me be clear: I should NEVER see "gh_sase-org__sase" (I'm also incorrectly seeing it pre-filled in the prompt input widget when using the `f` keymap to fork a done agent, for example). Anytime that I would have seen "gh_sase-org__sase", I should see "sase" after you've finished your changes. Fix EVERY violation of this rule. Think this through thoroughly and create a plan using your `/sase_plan` skill. Submit your plan with the
`sase plan propose` command (as the skill instructs) before making any file changes.
 %m:claude/claude-fable-5 %a:tale

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/eradicate_raw_project_keys.md`

> # Plan: Eradicate Raw Project Directory Keys From Every User-Facing Surface
> ## Problem
> The rule: the user must NEVER see a raw project directory key (e.g. `gh_sase-org__sase`) anywhere in SASE's user-facing
> output. Anywhere the raw key would have appeared, the configured `PROJECT_NAME` (e.g. `sase`) must appear instead.
> Storage, identity, launch canonicalization, JSON/machine output, and on-disk files stay canonical.
> Commit `228fc78af` (and `285600348` before it) humanized the prompt-display and prefill surfaces they targeted, but a
> full sweep of the repo found many remaining violations. Evidence from screenshot `20260706_141758`: the agent detail
> panel's COMMITS section shows `gh_sase-org__sase` as the repo group label. The user also reports the fork (`f`) keymap
> pre-filling the prompt input with `#gh:gh_sase-org__sase ...`.
> This plan fixes every confirmed violation and adds shared helpers + a test convention so new surfaces stay clean.

*See full plan file for details.*

