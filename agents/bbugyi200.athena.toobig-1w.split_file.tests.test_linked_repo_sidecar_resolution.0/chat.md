# Chat History - ace-run (toobig-1w.split_file.tests.test_linked_repo_sidecar_resolution.0)

- **TIMESTAMP:** 2026-08-07 12:26:00 EDT
- **MODEL:** claude/opus
- **AGENT:** toobig-1w.split_file.tests.test_linked_repo_sidecar_resolution.0
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260807_110611.md`

## Prompt

#gh:sase-org/sase
%id(split_file.tests.test_linked_repo_sidecar_resolution.0, clan=toobig-1w)
%wait:toobig-1w.split_file.tests.test_bead.test_task_gate.0
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `tests/test_linked_repo_sidecar_resolution.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by looking at the file.

No external references. Splitting into four concern-focused modules.

Now trim the original to the configured-sidecar resolution concern.

All 19 cases (18 functions, one parametrized) carried over. Now the repo gate:

`just check` is green. The 648-line module is now four concern-focused files:

| File | Lines | Concern |
|---|---|---|
| `tests/test_linked_repo_sidecar_resolution.py` | 172 | Explicitly configured sidecars: role/slug/remote resolution and how a pinned config interacts with the SDD store record |
| `tests/test_linked_repo_sidecar_defaults.py` | 186 | Implicit default sidecars (inject, disable, override, opt-out, missing) plus `sdd_sidecar_clone_dirname` defaults/store mapping |
| `tests/test_linked_repo_sidecar_hidden_agents.py` | 186 | The hidden `agents` role: injection, explicit overrides, never resolving for launch, machine-scoped clone dir |
| `tests/test_linked_repo_sidecar_config.py` | 134 | Parsing `repos.sidecar` bucketed config: legacy list form, role ordering, layer merge, bucket precedence, bad shapes |

All 18 test functions carry over unchanged (19 cases with parametrization) and pass. Naming follows the existing `tests/test_linked_repo_*.py` family, and every module reuses the shared `tests/_linked_repo_resolution_helpers.py` builders, so no helper duplication was needed. Nothing outside the file referenced the old module path.

The split is in place. Committing now.

Committed and pushed; working tree is clean and level with `origin/master`.

**What was done:** `tests/test_linked_repo_sidecar_resolution.py` (648 lines) was split into four concern-focused modules, all under 500 lines:

| File | Lines | Concern |
|---|---|---|
| `test_linked_repo_sidecar_resolution.py` | 172 | Explicitly configured sidecars — role/slug/remote resolution, pinned config vs. SDD store record |
| `test_linked_repo_sidecar_defaults.py` | 186 | Implicit default sidecars (inject, disable, override, opt-out, missing) plus `sdd_sidecar_clone_dirname` defaults/store mapping |
| `test_linked_repo_sidecar_hidden_agents.py` | 186 | The hidden `agents` role — injection, explicit overrides, never resolving for launch, machine-scoped clone dir |
| `test_linked_repo_sidecar_config.py` | 134 | Parsing bucketed `repos.sidecar` config — legacy list form, role ordering, layer merge, bucket precedence, bad shapes |

All 18 test functions (19 cases with parametrization) carried over unchanged and share the existing `tests/_linked_repo_resolution_helpers.py` builders, so no helper duplication was needed. Nothing outside the file referenced the old module path. `just check` passed before the commit, and the commit's own `just fix` hook ran clean.
