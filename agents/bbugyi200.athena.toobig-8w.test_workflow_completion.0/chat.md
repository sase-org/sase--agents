# Chat History - ace-run (toobig-8w.test_workflow_completion.0)

- **TIMESTAMP:** 2026-10-31 01:49:51 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** toobig-8w.test_workflow_completion.0

## Prompt

%auto
%id(test_workflow_completion.0, clan=toobig-8w)
%model:@medium
%queue(capacity=5)
#gh:gh_sase-org__sase Can you help me split the `tests/test_workflow_completion.py` file into multiple files? Use your best
%wait:toobig-8w.test_agents_tab_graph_isolation.0
judgment, but keep every resulting file at 500 lines of code or fewer.

Preserve behavior and the original module's public import path. A facade may re-export
public names, but never `_private` names. Never import a `_`-prefixed name across the
new modules. If more than one new module needs a helper, give it a public name inside an
already-private (`_`-prefixed) module; move a helper used by only one other module into
that module instead. Keep test monkeypatch targets working, or retarget the tests.

Before finishing, run `just _lint-symvision`, `just _lint-mypy`, and `just _lint-toobig`
individually. Fix every issue in a file the split touched, even if an earlier
`just check` stage is already red. Then run `sase tool run check`.

## Response

I'll start by reading the split-file conventions and the current test module so the new files stay under 500 lines without breaking imports.

I'll pull the lint/split conventions and inspect the test file next so the split matches how this repo already does it.

I'll look at a recent split for the local pattern, then read the test file in chunks.

I'll look at a recent split for the local pattern, then read the rest of the test file.

I'll put shared helpers in a private module with public names, keep single-module helpers local, and turn the original file into a facade.

The invoke module is missing a `ProviderEvidence` import; I'll add it while writing the remaining files.

Tests passed. Next I’ll run the three lint recipes separately, then `sase tool run check`.

Symvision and mypy passed; the toobig failure is in an unrelated file. I’ll run `sase tool run check` next.

Check failed on stale Justfile epic-symbols I didn’t touch. I’ll inspect the diff, then file that unrelated lint as a task bead.

Split `tests/test_workflow_completion.py` into five modules, all under 500 lines, with the original public import path kept as a facade.

**Layout**
- `tests/test_workflow_completion.py` — facade re-exporting public tests plus `RUN_ID` and `PROVIDER_RESPONSE`
- `tests/_workflow_completion_helpers.py` — shared helpers under public names (`workflow_env`, `agent_identity`, `agent_evidence`)
- `tests/_workflow_completion_invoke.py` — invoke/prepare coverage
- `tests/_workflow_completion_executor.py` — executor suspension coverage
- `tests/_workflow_completion_settle.py` — stage/settle and host-admission coverage

Helpers used by only one module (`_fake_agent_invoke`, `_stage_and_settle`, `_script_identity`, `_resolve_plan`) stayed private in that module. No `_`-prefixed names are imported across the new files. Pytest still collects 21 tests at `tests/test_workflow_completion.py::...`; all 21 passed.

**Lint**
- `just _lint-symvision` passed
- `just _lint-mypy` passed
- `just _lint-toobig` failed on unrelated `tests/monitor/test_monitor_start_stage.py` (1163 lines)

**`sase tool run check`** failed on stale Justfile `--epic-symbol` entries for closed bead `sase-1q4.6` (`WaitTargetBinding`, `bind_wait_target`). That file was outside the split, so it was left unchanged.
