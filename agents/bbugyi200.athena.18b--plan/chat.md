# Chat History - ace-run (18b--plan)

- **TIMESTAMP:** 2026-11-04 15:22:43 EST
- **MODEL:** claude/opus
- **AGENT:** 18b--plan

**Plan:** /home/bryan/.sase/plans/202611/cleanup_workspace_retention_serialization.md


## Proposed Plan Preview

*Plan submitted for review.*

**Plan file:** `/home/bryan/.sase/plans/202611/cleanup_workspace_retention_serialization.md`

> # Plan: Fix "Cleanup task failed: Object of type AgentWorkspaceRetention is not JSON serializable"
> ## Symptom
> Killing or dismissing agents in the ACE TUI (single `x`, bulk `X` cleanup, clan
> kill/dismiss) shows the usual "Dismissed N agents → Archive" / "Killed agent" toast,
> then an error toast:
> > Cleanup task failed: Object of type AgentWorkspaceRetention is not JSON serializable
> `~/.sase/logs/tui_toasts.jsonl` has five of these today across separate TUI sessions.
> The matching `tui.log` tracebacks all end in
> `sase.procs.submission._write_operation_request` → `sase.ops.io.write_private_json` →
> `json.dumps` →

*See full plan file for details.*

## Prompt

#gh:gh_sase-org__sase Why do I keep getting these messages about being unable to cleanup sase agents
after killing/dismissing them? See the ~/tmp/screenshots/20261104_151315.png screenshot
for context. Can you help me diagnose the root cause of this issue and fix it?

Think this through thoroughly and create a plan using your `/sase_plan` skill. Choose and author the appropriate
tier, validate and revalidate until it passes, then submit it with `sase plan propose` (as the skill instructs)
before making any file changes.
 %m:@xlarge

## Response

Reproduced: dismissing an agent with no retention still fails when an unrelated agent in the roster snapshot has a retained workspace. Writing the plan now.

Validation passed. Submitting the plan.

Those toasts come from a field added on Nov 1 that breaks every kill and dismiss while any agent in your roster has a retained workspace. I've written a fix plan and submitted it for your approval. No code has changed yet.

**Root cause.** Commit `31a28d9618` (Nov 1) added `Agent.workspace_retention`. It holds an `AgentWorkspaceRetention` object for each finished agent whose retained workspace hasn't been released, which is roughly the "22 stranded" in your header. The field was never added to `_RUNTIME_ONLY_BUNDLE_FIELDS` in `src/sase/ace/tui/models/agent_bundle.py`, so the raw object goes into every kill/dismiss cleanup request. The submit worker then fails when it tries to write that request as JSON.

**Why it hits almost every cleanup.** Each cleanup request also includes the whole agent list (`agents_with_children`), not just the agents you selected. So one stranded agent anywhere in the list breaks every kill and dismiss, even for unrelated agents. A throwaway script reproduced this: dismissing a plain agent failed because a different agent in the list had a retained workspace.

**Evidence.** `~/.sase/logs/tui_toasts.jsonl` on athena has 5 of these toasts today. The tracebacks in `tui.log` all end at `json.dumps` inside the code that writes the cleanup request to disk.

**What each failure costs you.** The rows disappear from the TUI and killed agents get SIGTERM, but the cleanup step never runs. So:
- Nothing is archived.
- No workspace or artifact cleanup happens.
- Agents that ignore SIGTERM are never force-killed.
- The hidden rows come back after a TUI restart.

**The plan** (one small single-agent task):
1. Add `workspace_retention` to `_RUNTIME_ONLY_BUNDLE_FIELDS` so it's never saved. It's display-only data that is reloaded from disk anyway, and dismissal reads the record from disk itself. This one line also fixes archive writes for dismissed agents.
2. Add regression tests, including the exact failing case where only an unrelated agent in the list has a retained workspace.
3. Add a guard test that checks every saved `Agent` field's type and fails if a non-JSON type has no encoder. This is the third bug of this kind, after `EpicFollowView` (fixed in `682e52fc71`) and the clan-wave fields. The guard would have caught this one, and the plan has the implementer prove that by temporarily removing the fix.
4. File a follow-up bug: when a cleanup fails before it even starts, the hidden rows aren't brought back and the force-kill fallback never runs.

**After it lands:**
- Restart `sase tui` on both athena and apollo.
- Re-dismiss the rows that reappear: dismissals that failed were only hidden for that TUI session.

The other toast in your screenshot, "The selected clan row has no agent reference", is unrelated: it's the copy-to-clipboard action declining a clan row, which is expected.
