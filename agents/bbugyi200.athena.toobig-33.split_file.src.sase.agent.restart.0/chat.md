# Chat History - ace-run (toobig-33.split_file.src.sase.agent.restart.0)

- **TIMESTAMP:** 2026-08-18 17:01:31 EDT
- **MODEL:** claude/opus
- **AGENT:** toobig-33.split_file.src.sase.agent.restart.0
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260818_114231.md`

## Prompt

#gh:sase-org/sase
%id:toobig-33.split_file.src.sase.agent.restart.0
%clan(toobig-33, tribe=chop, summary=[[[bold #D75FFF]◆ TOOBIG SPLIT · 2 FILES[/bold #D75FFF]
[bold #87D7FF]MISSION[/bold #87D7FF]
[dim #D7D7FF]Decompose oversized Python modules into focused, reviewable units[/dim #D7D7FF]
[dim #D7D7FF]without changing behavior.[/dim #D7D7FF]

[bold #87D7FF]TARGETS[/bold #87D7FF]
[#87D7FF]• 806  src/sase/agent/restart.py[/#87D7FF]
[#87D7FF]• 760  tests/test_vcs_xprompt_mru.py[/#87D7FF]

[dim #A8A8A8]2 scan roots · limits 1,000 / 850 / 700 lines · sequential queue[/dim #A8A8A8]]])
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `src/sase/agent/restart.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by looking at the file.

Now let me check consumers and the repo's private-symbol lint rules.

Now I'll create the split modules.

Now the facade:

Now update the two audit-test keys for the moved `_write_recovery_files`:

Formatting is clean. Now running the full check gate:

Lint gates that fail (mypy, symvision, toobig) are all pre-existing on master and unrelated to my files. Now the tests:

All 49 pass. Now the scoped test lane that `check` would have run:

Confirmed: those failures reproduce on clean master with my changes stashed. Let me verify my split is complete and behavior-preserving, then file the pre-existing breakage.

Now let me file the pre-existing master breakage as a task bead:

Let me verify no logic was lost in the move:

Split `restart.py` (825 lines) into six modules, following the `family_attach.py` convention already used in `src/sase/agent/` — private `_`-prefixed modules behind a thin public facade.

| File | Lines | Contents |
|---|---|---|
| `restart.py` | 48 | Facade: re-exports the 12 public names, `__all__` |
| `_restart_types.py` | 96 | `AgentRestartError`, the three dataclasses, `NameReuseSource`, `ProgressFn` |
| `_restart_reads.py` | 45 | Tolerant artifact reads: `read_json_dict`, `read_raw_prompt`, `optional_str`, `resolved_path` |
| `_restart_preview.py` | 308 | `build_restart_preview` + warnings, labels, `restart_needs_confirmation`, `wipe_deletes_label` |
| `_restart_planning.py` | 265 | `plan_agent_restart` + the refusal/name-reuse/identity helpers |
| `_restart_recovery.py` | 83 | The `~/.sase/restarts` bundle writers |
| `_restart_execute.py` | 168 | `execute_agent_restart` + outcome/detail helpers |

The seam is the plan/execute split the original docstring already described: read-only planning, display-only preview, mutating execution, and the recovery bundle that has to outlive a failed relaunch.

Two structural changes beyond pure moves, both to avoid the planning module importing a dozen preview helpers: the `AgentRestartPreview` construction that was inline in `plan_agent_restart` became `build_restart_preview(...)`, and three refusal branches became `_require_raw_prompt`, `_refuse_multi_segment`, `_rewrite_prompt_identity`. Four helpers had to shed their `_` prefix (`read_json_dict` et al.) because symvision forbids importing private symbols across files.

I verified every moved function body is byte-identical to the original after normalizing those renames — only `plan_agent_restart` and `execute_agent_restart` differ structurally. I also updated the two marker-audit tests that key `_write_recovery_files` by file path.

**Verification:** `ruff` and `ruff format` clean; the 49 restart + marker-audit tests pass; `toobig` and `symvision` report nothing in the new files.

**Three gates are red on master, all pre-existing** — I confirmed each reproduces with my changes stashed:

- `src/sase/main/project_handler.py:16` imports `project_accent_map`, which `a3765f857` privatized on the wrong premise that it had no consumer. This breaks mypy and cascades into **208 test failures + 151 errors** across the full suite. Recorded as a `DISCOVERED ISSUE:` note on in-progress epic `sase-pw`, which wrote that consumer in `a6e374d00`.
- symvision unused publics — `+1`'d ready task `sase-q5` (the two ledger symbols) and noted the three newer ones from `7a2906e13` on in-progress epic `sase-q0`.
- `toobig`: `tests/_suite_gate.py` at 1197/1000 lines — filed as ready task **`sase-q7`**.

Because of the first one, I could not get a green `just check` run to sign off on; the suite is unusable on this commit regardless of my change. The restart-specific and audit tests I ran directly all pass.

These are my changes from this session. Committing them now.

Committed as `daa095ec3`; working tree is clean and `master` is level with `origin/master`.

**What landed:** `src/sase/agent/restart.py` (825 lines) split into six modules behind a 48-line facade that re-exports the same twelve public names, so no importer changed.

| File | Lines |
|---|---|
| `restart.py` (facade) | 48 |
| `_restart_types.py` | 96 |
| `_restart_reads.py` | 45 |
| `_restart_preview.py` | 308 |
| `_restart_planning.py` | 265 |
| `_restart_recovery.py` | 83 |
| `_restart_execute.py` | 168 |

Two changes beyond pure moves: the inline `AgentRestartPreview` construction became `build_restart_preview`, and three refusal branches in `plan_agent_restart` became named helpers — both so the planning module doesn't have to import a dozen preview internals. Four read helpers shed their `_` prefix because symvision forbids cross-file private imports. Every other moved function body is byte-identical.

**Verified:** `ruff`, `ruff format`, `toobig`, and symvision are clean on the new files; the 49 restart + marker-audit tests pass. The pre-commit `just fix` hook ran clean.

**Not verified — three gates are red on master independent of this change**, each confirmed to reproduce with my changes stashed:
- `src/sase/main/project_handler.py:16` imports `project_accent_map`, privatized by `a3765f857`. This breaks mypy and cascades into 208 test failures + 151 errors across the full suite, so no green `just check` was obtainable on this commit. Noted on in-progress epic `sase-pw`.
- symvision unused publics — `+1`'d ready task `sase-q5`, noted three newer ones on epic `sase-q0`.
- `toobig`: `tests/_suite_gate.py` at 1197/1000 lines — filed as ready task `sase-q7`.

One warning from the commit: the project has 39 quarantined agent-hood publication requests, so the hood link on this commit may not resolve until someone runs `sase agent sync --retry-quarantined`. That's a pre-existing backlog, not something this commit caused.
