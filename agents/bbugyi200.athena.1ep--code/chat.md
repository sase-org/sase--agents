# Chat History - ace-run (1ep--code)

- **TIMESTAMP:** 2026-11-20 18:20:10 EST
- **MODEL:** grok/grok-4.6
- **AGENT:** 1ep--code

# Monitor handoff

This agent delegated the remaining work to a monitor turn.
Monitor ID: 69df0h2xbbfa
Inspect with: sase monitor show 69df0h2xbbfa
Monitor turn: 1ep--mon
Directory: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20

Command:

```sh
just check
```

Reason:

Verify hijack WORKING TALE status fix before host completion


## Prompt

%model:@small
#gh:gh_sase-org__sase @plan:202611/hijack_working_tale_status.md

The above plan has been reviewed and approved. Implement it now.

%macros_enabled:false
Reviewer decisions for this plan (final · reviewer via ACE):
- alias_scope = all (planner default: all). Implement the "alias_scope = all" branch; ignore "alias_scope = working". Context: "Should hijack also treat a live EPIC APPROVED or PLAN COMMITTED member as RUNNING?".
Implement only the branches selected above.
%macros_enabled:true


## Response

I'll start by reading the plan from the sidecar and the skills this implementation depends on.

I'll read the approved plan as an audited artifact and pull the memory this work depends on.

The plan is a Python facts-adapter fix. I'll inspect the current hijack status path and tests next.

I'll add the alias set, normalize live display labels in `_status`, and write the three tests the plan names.

I'll run the three targeted test files the plan names.

Targeted tests passed. Next I'll format, then stage prepared host completion with `just check`.

Hijack now treats a live TUI row labeled `WORKING TALE`, `WORKING PLAN`, `EPIC APPROVED`, or `PLAN COMMITTED` as `RUNNING`, so `,k` matches `sase agent hijack`.

The TUI paints those labels over a live session member whose runner status is still `RUNNING`. The hijack facts adapter was forwarding the display label into Rust eligibility, which only accepts `RUNNING | STARTING | RETRYING`.

What landed (`alias_scope = all`):

- `RUNNING_DISPLAY_ALIAS_STATUSES` in `src/sase/agent/status_buckets.py` covers the two working labels plus `EPIC APPROVED` and `PLAN COMMITTED`.
- `_status` in `src/sase/agent/hijack/_facts_resolve.py` maps an alias to `RUNNING` only when the process is alive. A dead alias row keeps its label; a dead `RUNNING` row is still `LOST`.
- `_row_status` is unchanged. No hijack decision reads `HijackTarget.status`.

Tests: 45 passed in `tests/test_agent_hijack_facts.py`, `tests/ace/tui/test_agent_hijack_tui_parity.py`, and `tests/test_agent_loader_status_override_gate_turn_agent_session.py`.

`just check` is staged as the prepared host-completion gate. On green the host commits; on red a recovery successor starts.
