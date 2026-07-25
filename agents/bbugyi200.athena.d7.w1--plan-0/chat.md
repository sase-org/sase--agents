# Chat History - ace-run (d7.w1--plan)

- **TIMESTAMP:** 2026-07-18 08:24:30 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** d7.w1--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-d7_w1__plan-260718_073839.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260718_073839.md`

**Plan:** /home/bryan/.sase/plans/202607/family_plan_root_rename.md


## Prompt

%wait(d7)
#gh:gh_sase-org__sase We recently added the distinction between agent clans and agent
families but The main goal was essentially to leave agent families the way they
were and add support for this new concept of agent clans (see the sase-6n epic
bead for context).

- This seems to mostly work as planned but we've started to use the `--plan-0`
  suffix instead of `--plan` for agents that proposed a plan that the user
  approved and the root / top-level agent row no longer keeps the original agent
  name (see ~/tmp/screenshots/20260718_063757.png). This is not correct.
- When agent families are created they should take on the name of the first
  agent that was in that family and the first agent should be renamed (in this
  case, we should use the `--plan` suffix).
- Agent family names must be supported as input arguments for the `#fork`
  xprompt and the `%wait` directive (the previous bullet allows for this, but
  make sure it actually works).
- Make sure that all other previously supported standard ways that we create
  agent families (e.g. when the user answers a question, gives feedback on a
  plan, etc...) are supported / working as they were from the user's standpoint.

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:claude/claude-fable-5 

## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/family_plan_root_rename.md`

> # Plan: Bare `--plan` family roots and family-name references
> ## Context
> sase-6n.4 (commit 01da41927) introduced rename-on-attach: when the first member attaches to a bare agent `cx`, the
> original is persistently renamed into a member slot and the bare name becomes a family container. The implementation
> reused the old display-slot spellings — `--plan-0` for plan proposers and `--0` for generic roots — and deleted the
> display-only collapse that used to keep the top-level row labeled with the bare name. Two user-visible regressions
> resulted:
> 1. **Wrong root suffix.** A plan proposer is now persisted as `cx--plan-0`. That name is overloaded: `--plan-N` is the
>    namespace for plan feedback rounds and plan-phase question follow-ups (the `--plan-@` allocation template), and the
>    suffix classifier reads `--plan-0` as a feedback row. The proposer must instead take the canonical unnumbered planner

*See full plan file for details.*

