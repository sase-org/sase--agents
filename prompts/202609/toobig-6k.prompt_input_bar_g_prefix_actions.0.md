- **AGENTS:**
  - [bbugyi200.athena.toobig-6k.prompt_input_bar_g_prefix_actions.0--4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.toobig-6k.prompt_input_bar_g_prefix_actions.0.md)

%queue(weight=1) %auto #fork:toobig-6k.prompt_input_bar_g_prefix_actions.0--3
%model:muse-spark-1.3-contributor %effort:xhigh

%xprompts_enabled:false

# Monitored command finished

**Command:**

```text
just check
```

**Directory:**

```text
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16
```

|              |                                                                                                                                                                                                                                                                                                                                                                         |
| ------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Outcome**  | FAILED — exit 1                                                                                                                                                                                                                                                                                                                                                         |
| **Started**  | 2026-10-01T01:53:43.305260+00:00                                                                                                                                                                                                                                                                                                                                        |
| **Finished** | 2026-10-01T02:42:46.804434+00:00                                                                                                                                                                                                                                                                                                                                        |
| **Elapsed**  | 49m 2s of a 1h 0m 0s budget                                                                                                                                                                                                                                                                                                                                             |
| **Output**   | 269 KiB · evidence refs: `file:monitor-diagnostic-manifest:5tn3hmk0kqc7`, `file:monitor-retained-log:5tn3hmk0kqc7`, `file:monitor-stage:lint-symvision-2789012-1790819814684918737-eca0ba39`, `file:monitor-stage:test-scoped-3774173-1790822562851411368-8949acab` · raw output omitted: `failed_diagnostics` · full log: `sase monitor show 5tn3hmk0kqc7 --all-lines` |
| **Tool run** | sase tool show 6b00116a1ba378bec6e048ff465f6832                                                                                                                                                                                                                                                                                                                         |

**Why this was monitored:** Verify g_prefix split before host completion

## Failure triage

verdict: no_new_failures — 7 KNOWN, 18 FLAKY; exit 1

KNOWN 7; FLAKY 18

sase tool show 6b00116a1ba378bec6e048ff465f6832 -j

## Selected diagnostics

<!--sase:budget-span:open:kind=newest_diagnostics;id=1-->

**Diagnostics (untrusted program output):**

```text
== lint (symvision) (failed exit 1) ==
[counts: output_bytes=1902, output_lines=15, retained_bytes=1902]
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.36.1 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.35.0,<0.36.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.
SASE_SYMVISION_BEAD_STATUS_ONLY=1 BD_COMMAND=tools/sase_bead .venv/bin/symvision src/sase --exclude-decorator gate_command_entrypoint --exclude-decorator builtin_chop
Unused public functions/classes. Make these private if they are used only within the file they are defined. If the functions/classes are completely unused, you should delete them:
  HandoffSubmitResult in src/sase/tool/handoff_launch.py
  StarterResolution in src/sase/tool/starter.py
  fit_next_word_ghost in src/sase/ace/tui/widgets/next_word_completion.py
  get_unread_set_generation in src/sase/ace/tui/actions/agents/_unread_set_generation.py
  has_unread_probe_cache_key in src/sase/ace/tui/actions/agents/_unread_set_generation.py
  note_unread_set_changed in src/sase/ace/tui/actions/agents/_unread_set_generation.py
  owner_ref in src/sase/tool/owner.py
error: recipe `_lint-symvision` failed on line 397 with exit code 1
== test (scoped) (failed exit 1) ==
[counts: output_bytes=247407, output_lines=3289, retained_bytes=247407]
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.36.1 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.35.0,<0.36.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: core-identity-changed); 4732 test files in scope
coverage contexts: not consulted — the run escalates to the full suite, so ground truth had nothing to add
escalating to the governed full test lane (rules: core-identity-changed)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16
configfile: pyproject.toml
testpaths: tests
plugins: hypothesis-6.168.0, cov-7.1.0, asyncio-1.4.0, inline-snapshot-0.35.4, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 4/4 workers
4 workers [51066 items]

........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  4%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  6%]
...................................

```

<!--sase:budget-span:close:1-->

## Your next action

Diagnose failures or stale verification, then finish the requested change.
%xprompts_enabled:true
