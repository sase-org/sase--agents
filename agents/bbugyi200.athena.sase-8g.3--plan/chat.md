# Chat History - ace-run (sase-8g.3--plan)

- **TIMESTAMP:** 2026-07-20 16:37:31 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** sase-8g.3--plan

## Linked Chats

- **1. --plan** — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-sase_8g_3__plan-260720_163159.md`
- 2. --code — `~/.sase/chats/202607/gh_sase_org__sase-ace_run-260720_163159.md`

**Plan:** /home/bryan/.sase/plans/202607/runner_slot_wait_regressions.md


## Prompt

#gh:gh_sase-org__sase
%id(3, clan=sase-8g)
%model:@phase_worker
%auto
Can you complete the work for bead sase-8g.3? The bead has already been claimed for you (status=in_progress,
assignee set). Read its description and design file, do the work, and close the bead. Do NOT close the parent
epic. Do NOT create new beads.
Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.


## Response

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202607/runner_slot_wait_regressions.md`

> # Plan: Fix runner-slot wait regressions
> ## Context and invariants
> Runner-slot admission is a process-local polling loop coordinated by the global runner-slot lock. The ACE wait editor
> already persists edits in a tracked worker under the same lock, but its Run Now branch currently writes a dependency
> `ready.json` marker that the slot poll never consumes. The question continuation path also drops the persisted
> `%wait(priority=...)` value when it reacquires a slot, and the slot poll replaces `waiting.json` with a fixed payload
> that removes conditions or extension fields owned by other wait mechanisms.
> Keep the existing admission model intact: the shared priority normalization and priority-then-FIFO queue remain
> authoritative; Run Now restores the implicit global-cap threshold rather than bypassing capacity; TUI disk work remains
> in the tracked background task; and all waiting-marker edits serialize through the existing runner-slot lock. Preserve

*See full plan file for details.*

