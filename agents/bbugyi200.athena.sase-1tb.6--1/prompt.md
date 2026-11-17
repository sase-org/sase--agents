%queue(weight=1)
#fork:sase-1tb.6--plan
%model:muse-spark-1.3-contributor@xhigh

%macros_enabled:false
# Monitored command finished

**Command:**

```text
just check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_30
```

| | |
| --- | --- |
| **Outcome** | FAILED — exit 1 |
| **Started** | 2026-11-17T22:38:42.441661+00:00 |
| **Finished** | 2026-11-17T22:47:41.441046Z |
| **Elapsed** | 5m 44s of a 1h 0m 0s budget |
| **Output** | 3 KiB · evidence refs: `file:monitor-diagnostic-manifest:e8j96e511nsa`, `file:monitor-retained-log:e8j96e511nsa`, `file:monitor-stage:lint-docs-contract-938961-1794955658913859144-45f013c8`, `file:monitor-stage:lint-symvision-933321-1794955652866910571-eca0ba39` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show e8j96e511nsa --all-lines` |
| **Tool run** | sase tool show ef92d09886bce4d9eb55e00633ec9474 |

**Why this was monitored:** Verify before host completion

## Failure triage

verdict: undetermined — 1 UNKNOWN, 1 KNOWN; exit 1

UNKNOWN lint (docs contract): error: recipe `docs-lint` failed on line 1087 with exit code 1 — extractor_generic; no owner
KNOWN 1; FLAKY 0

sase tool show ef92d09886bce4d9eb55e00633ec9474 -j

## Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=1-->
**Diagnostics (untrusted program output):**

```text
== lint (docs contract) (failed exit 1) ==
[counts: output_bytes=810, output_lines=7, retained_bytes=810]
.venv-format/bin/python tools/check_docs
warning: contribute/development.md: over budget at 12504 words (cap 8000 for contribute/). This page may not grow. Split it: anything longer than one goal is two guides.
warning: contribute/perf-runbook.md: over budget at 12941 words (cap 8000 for contribute/). This page may not grow. Split it: anything longer than one goal is two guides.
warning: contribute/rust-backend.md: over budget at 10780 words (cap 8000 for contribute/). This page may not grow. Split it: anything longer than one goal is two guides.
error: reference/agent-attachments.md: over budget at 6171 words (cap 6000 for reference/). This page may not grow. Split it: anything longer than one goal is two guides.
check_docs: 1 error(s)
error: recipe `docs-lint` failed on line 1087 with exit code 1
== lint (symvision) (failed exit 1) ==
[counts: output_bytes=1468, output_lines=7, retained_bytes=1468]
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop --epic-symbol "sase-1t3.10.1.3(agent_artifact_list_wire_schema_version)" --epic-symbol "sase-1t3.10.1.3(build_done_agent_from_compact_record)" --epic-symbol "sase-1t3.10.1.3(is_compact_done_record)" --epic-symbol "sase-1t3.10.1.3(load_done_agents_from_compact_snapshot)" --epic-symbol "sase-1t3.10.1.3(load_running_home_agents_from_compact_records)" --epic-symbol "sase-1t3.10.1.3(load_running_home_agents_from_compact_snapshot)" --epic-symbol "sase-1t3.10.1.3(query_agent_artifact_index_list)" --epic-symbol "sase-1t3.10.1.3(query_agent_artifact_index_list_bounded)" --epic-symbol "sase-1t3.10.1.3(resolve_compact_running_home_records)" --epic-symbol "sase-1t3.10.1.3(scan_agent_artifact_dir_list)" --epic-symbol "sase-1t3.10.1.3(scan_agent_artifact_dirs_list)" --epic-symbol "sase-1t3.10.1.3(scan_agent_artifacts_list)" 
Unused public functions/classes. Make these private if they are used only within the file they are defined. If the functions/classes are completely unused, you should delete them:
  MemoryAuditRow in src/sase/memory/_read_log_query_facade.py
error: recipe `_lint-symvision` failed on line 565 with exit code 1

```

<!--sase:budget-span:close:1-->

## Your next action

Inspect the monitor result, repair any failed or timed-out verification, and finish the original task.
%macros_enabled:true