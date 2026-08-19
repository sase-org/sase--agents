# Chat History - ace-run (toobig-34.split_file.tests.test_config_schema.0)

- **TIMESTAMP:** 2026-08-18 22:32:35 EDT
- **MODEL:** claude/opus
- **AGENT:** toobig-34.split_file.tests.test_config_schema.0
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260818_172323.md`

## Prompt

#gh:sase-org/sase
%id(split_file.tests.test_config_schema.0, clan=toobig-34)
%wait:toobig-34.split_file.tests.ace.tui.test_retry_edit_agent_name.0
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `tests/test_config_schema.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by looking at the file.

Now I'll write a splitter script that moves the test blocks verbatim.

All 41 test bodies moved verbatim. Now installing and running the suite.

Now the full check gate. This one runs long, so I'll hand it to a monitor.

Confirmed pre-existing on a clean HEAD tree. Filing that as a task bead per the project rules.

Root cause identified. Per the skill, this belongs on the in-progress epic rather than a new task bead.

`tests/test_config_schema.py` (736 lines) is now six files, each well under 500 lines:

| File | Lines | Covers |
|---|---|---|
| `test_config_schema.py` | 95 | schema packaging, default-config conformance, identity/`machine_name`, glossary shape |
| `test_config_schema_ace.py` | 183 | prompt completion, prompt spellcheck, current-project, agents-sync, artifacts |
| `test_config_schema_keymaps.py` | 99 | scoped `statistics`/`gate` keymaps |
| `test_config_schema_runtime_limits.py` | 164 | `max_running_agents`, `max_agent_pipe_chain`, `runner_slots` + their `config.core` accessors |
| `test_config_schema_extensions.py` | 155 | `artifact_refs` roots, `file_hooks`, `plugins.required` |
| `test_config_schema_beads.py` | 103 | `big_epic_phase_threshold`, `task_triage` |

The naming follows the existing `test_config_schema_<topic>.py` family already in `tests/`.

**How it was done**

- All 41 test bodies moved verbatim — I diffed every block against `HEAD` and the only differences were file-header boundaries. Collection is identical: 91 tests before, 91 after, all passing.
- `REPO_ROOT` moved into `tests/_config_schema_helpers.py` so the three files that read `default_config.yml` share one anchor instead of redefining it.
- Every new file keeps `pytestmark = pytest.mark.contract`, so always-on coverage is unchanged.

**Two things worth knowing**

1. **Contract-set budget.** These files are in the always-on contract set, so splitting one entry into six tripped `test_contract_set_manifest_entry_budget_has_no_hidden_headroom`. I regenerated `tests/contract_manifest.txt` and re-curated the cap 44 → 49, following the documented procedure and the precedent from the 2026-08-16 split. I measured the set at **29.8 s** (median of three) against the plan's **hard 30 s** serial budget — the same set measured 29.0 s pre-split on this host, so the split costs well under a second. It fits, but this is the least headroom the set has ever had; the next contract candidate should displace an entry rather than raise the cap again. The comment in `tests/test_contract_manifest.py` says so.

2. **Pre-existing failure, unrelated to this work.** `just check` is green except `tests/ace/tui/test_plugins_browser_pane_detail.py::test_plugins_pane_lazy_fetches_highlighted_latest_when_flag_on`, which fails 3/3 on a stashed, unmodified tree. I traced it: phase `sase-qn.2` added `_apply_plugin_latest`, which updates `_catalog`/`_grouped`; phase `sase-qn.4` then added the `_plugin_entry_by_name` identity map that `_apply_plugin_latest` never refreshes, so `_entry_by_name` returns the stale entry. It's user-visible — the Updates > Plugins detail panel re-renders from that map and never shows the lazily fetched version. Since epic `sase-qn` is still in progress with a credible causal link, `/sase_new_task` routed this to a `DISCOVERED ISSUE:` note on the epic rather than a new task bead.

Nothing is committed — say the word if you want a commit.

I'll commit the changes now.

These are my changes from this session. Let me do a quick verification before committing.

94 passed. Committing now.

Committed and pushed as `2633d3c2b`. Working tree is clean and `master` is in sync with `origin/master` (the commit rebased onto an upstream `build(deps)` commit that landed meanwhile).

## What was committed

`tests/test_config_schema.py` (736 lines) split into six modules, all under 500 lines:

| File | Lines | Covers |
|---|---|---|
| `test_config_schema.py` | 95 | schema packaging, default-config conformance, identity/`machine_name`, glossary shape |
| `test_config_schema_ace.py` | 183 | prompt completion, prompt spellcheck, current-project, agents-sync, artifacts |
| `test_config_schema_keymaps.py` | 99 | scoped `statistics`/`gate` keymaps |
| `test_config_schema_runtime_limits.py` | 164 | `max_running_agents`, `max_agent_pipe_chain`, `runner_slots` + `config.core` accessors |
| `test_config_schema_extensions.py` | 155 | `artifact_refs` roots, `file_hooks`, `plugins.required` |
| `test_config_schema_beads.py` | 103 | `big_epic_phase_threshold`, `task_triage` |

Naming follows the existing `test_config_schema_<topic>.py` family in `tests/`. All 41 test bodies moved verbatim; every module keeps `pytestmark = pytest.mark.contract`. `REPO_ROOT` moved into `tests/_config_schema_helpers.py` so the three modules reading `default_config.yml` share one anchor.

Splitting one always-on contract entry into six tripped the manifest entry budget, so `tests/contract_manifest.txt` was regenerated and the cap re-curated 44 → 49, with the measurement rationale recorded in `tests/test_contract_manifest.py`.

## Verification

Ran the six split modules plus `test_contract_manifest.py` before committing: **94 passed in 29.06 s**. The commit's `just fix` pre-hook ran clean.

I did **not** re-run the full `just check` gate in this pass. In the earlier pass it was green except for one pre-existing, unrelated failure — `tests/ace/tui/test_plugins_browser_pane_detail.py::test_plugins_pane_lazy_fetches_highlighted_latest_when_flag_on`, which fails 3/3 on a stashed, unmodified tree (`_apply_plugin_latest` from phase `sase-qn.2` doesn't refresh the `_plugin_entry_by_name` map added in phase `sase-qn.4`). That was already recorded as a `DISCOVERED ISSUE:` note on the in-progress `sase-qn` epic.
