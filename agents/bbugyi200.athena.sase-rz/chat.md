# Chat History - ace-run (sase-rz)

- **TIMESTAMP:** 2026-08-22 16:47:57 UTC
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-rz

## Prompt

#gh:gh_sase-org__sase
%id(sase-rz, bead=sase-rz)
%m:@small
Can you complete the work for task bead sase-rz by running the `sase bead show sase-rz` command,
reviewing the command's output, doing the work, and then closing the bead by running the
`sase bead close sase-rz --note "<what you verified>"` command?

If you discover genuinely distinct follow-up work that is outside this task, use `/sase_new_task` with details
identifying the current bead; it will corroborate a duplicate, attach a causally related active-epic issue, or
create a sized task as appropriate.

## Response

I'll start by inspecting the task bead and the bead/memory guidance so I can complete `sase-rz` and close it with a verification note.

The bead is a memory update for the `%final` directive. I’ll read the bead/xprompt notes and the related landing work so the docs match the shipped contract.

The memory note still omits `%final` and still describes the old commit-finalizer path. Next I’ll pull the shipped syntax and the related landing docs so the update matches the real contract.

I have the shipped `%final` contract. Next I’ll update the memory note, regenerate the derived instruction files, and verify the result.

Verification passed. I’ll close `sase-rz`, then check whether the leftover public-docs wording is follow-up for the still-open epic.

Follow-up is recorded on the epic. Next I’ll submit the host-owned finalizer declaration for this turn.

Closed **sase-rz**. The xprompt memory note now documents the shipped `%final` contract.

**Memory update (`sase/memory/xprompts.md`):**
- Added `%final` to the Directives table as a repeatable, keyword-free selector.
- Documented the full syntax: omit `%final` to keep `finalizers.defaults`; slugs add; `!name` removes; `none` clears removable defaults; operations replay left to right; the host then orders by configured `after` edges; required instances cannot be dropped; bare `%final` fails at launch.
- Replaced the stale “provider-neutral finalizer → `/sase_git_commit` → `sase commit`” rule with the host-owned protocol: `/sase_final` → `sase final context` / `sase final submit` → `sase stitch create`.

**Verified:** `sase memory init --no-commit`, `sase memory init --check` (no drift), audited `sase memory read`, `git diff --check`, and `just check` (all lint gates plus scoped tests).

**Follow-up:** `docs/commit_workflows.md` still describes the old skill-wrapper path at the top of the file while the later section already matches the new protocol. That is leftover from epic **sase-rr** (phase 3 docs sync), so it was recorded there as a discovered issue instead of a new task.
