# Chat History - ace-run (g2--plan)

- **TIMESTAMP:** 2026-07-20 10:00:54 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** g2--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-g2__plan-260720_094817.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260720_094817.md`

**Plan:** /home/bryan/.sase/plans/202607/restore_epic_tribe_on_resume.md


## Prompt

#gh:gh_sase-org__sase When the `sase bead work` command launches an epic that is already partially complete, we don't seem to add it to the `@epic` agent tribe like we should (see #sshot). Can you help me diagnose the root cause of this issue and fix it? Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/restore_epic_tribe_on_resume.md`

> # Plan: Restore the epic tribe on resumed bead work
> ## Context and root cause
> `sase bead work` correctly renders a new epic clan with one create-only `%clan(<epic>, tribe=epic)` declaration and
> renders all later members as `%id(<member>, clan=<epic>)` joiners. On a retry or partial resume,
> `launch_epic_bead_work()` sees the durable clan reservation and intentionally renders every remaining phase and the land
> agent as a joiner so it does not violate the single-declaration clan lifecycle.
> The tribe, however, is currently transported only by the declaring prompt. The runner writes `clan_tribe` only when it
> sees `tribe=` on `%clan`, while the per-segment epic metadata carries the plan reference and bead IDs but no tribe. If
> the declarer fails before publishing metadata, is relaunched through the declaration-to-join retry rewrite, or is
> otherwise absent from the readable clan generation, the durable clan container still supplies membership and generation

*See full plan file for details.*

