# Chat History - ace-run (research.3a.gem)

- **TIMESTAMP:** 2026-11-04 15:27:12 EST
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.3a.gem
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261104_150927.md`

## Prompt

%id(gem, clan=research.3a)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.3a.cdx`, `research.3a.cld`, `research.3a.grk`, `research.3a.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I want to start working through this project's task beads, starting with the 10 most
important / impactful ones that I should work. Can you do some research to help me
determine what those 10 beads are? If <10 actually need to be worked, then recommend
only the task beads that you feel should be worked. Make sure that you review any
running sase agents on this machine and my athena machine before selecting the task
beads, to make sure that an ongoing epic (for example) isn't going to conflict with any
of them.

End your analysis with a ranked list of task beads that you think should be worked, with
justification and a recommended solution for each. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__gem` suffix, i.e. `<stem>__gem.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example
`research:202609/topic__a.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

# Research Synthesis: Top 10 Most Impactful Task Beads for SASE

**Researcher:** `research.3a.gem`  
**Report File:** [`top_10_impactful_task_beads__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202611/top_10_impactful_task_beads__gem.md)  
**Registered Artifact:** `research:202611/top_10_impactful_task_beads__gem.md` (`explicit:f68ec3e9c953e00ce62ec1c4`)

---

## 1. Executive Summary & Host Audit

An independent census of all **391 active task beads** in `gh_sase-org__sase` (143 bugs, 12 CI failures, 90 flakes, 102 features, 30 memory, 5 untyped) was conducted to determine the **10 most impactful beads** to work on.

### Cross-Host Running Agent & Epic Audit
To prevent conflicts with ongoing work, running agents and active epics across both `apollo` (local) and `athena` (remote) were audited:
- **`apollo`**: `cd--code` (implementing `codex_exec_final_answer_integrity.md`) and research swarm `research.3a.*`.
- **`athena`**: `18a` (working on `actstat:sase-core`), `18b` (investigating agent dismiss cleanup), epic `sase-1qz` (*Agent Hijack*), epic `sase-1r8` (*Agent Publication & Drain*), epic `sase-1r2` (*v0.19.0 Release & Green Full CI*), and epic `sase-1n6`/`sase-1n6.11` (*Release Train & Steward*).

**Conflict Verification:** Every recommended bead was screened against the files, subsystems, and execution scopes of these in-flight epics; **zero conflicts exist**.

---

## 2. Ranked List of Top 10 Task Beads

### Rank 1: [`sase-1ot`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sdd/beads/events/issues/sase-1ot.jsonl) — Rotate and Purge Historical Secret-Scanner Hits in Public Repo History
* **Type / Size / Status:** `bug` / `large` / `ready` (+1 confirmation)
* **Justification:** **Critical Security Exposure**. A private audit of public sidecar `sase-org/sase--agents` at tip `5066d26a` using core scanner rules v1 identified **27 secret-scanner hits** across 138,525 files. While forward publications are protected, historical commits in the public repo contain exposed credentials. Repository owner Bryan already approved credential rotation and a git history purge via approval gate `custom-57bc7a62`, but no bead was assigned to execute the remediation.
* **Recommended Solution:**
  1. Coordinate with Bryan to verify rotation/revocation of the 27 credential values in private report `audit-report.md`.
  2. In a clean workspace, run `git-filter-repo` (or BFG) over `sase-org/sase--agents` using the path/string map from `audit-report.md` to purge exposed tokens across all historical commits and tags.
  3. Validate with core scanner rules v1 that 0 findings remain.
  4. Force-push to `sase-org/sase--agents` and notify connected hosts to re-sync their tracking branches without triggering re-push storms (addressing `sase-1or`).

---

### Rank 2: [`sase-1r7`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sdd/beads/events/issues/sase-1r7.jsonl) — Adopt SSH Publickey Credential Retries in Network Git Call Sites
* **Type / Size / Status:** `feature` / `large` / `ready` (Filed 2026-11-04 following active incident)
* **Justification:** **Infrastructure Resilience**. During GitHub's SSH outage on 2026-11-04, background jobs and turn-end landing pushes aborted immediately on transient `Permission denied (publickey)`. Epic `sase-1r5.1` introduced `CredentialRetry` (`src/sase/git_credential_retry.py`), but four critical network git call sites were left unadapted:
  1. `src/sase/sdd/_sidecar_git.py:push_sidecar`
  2. `src/sase/axe/runner_workspace_sidecar.py:_run_sidecar_push`
  3. `src/sase/vcs_provider/plugins/_git_commit_dispatch.py:_push_with_retry`
  4. `src/sase/bead/_sync_worker_run.py`
* **Recommended Solution:**
  1. In the four call sites, classify failures with `classify_failure_retryability`.
  2. On `RETRYABILITY_VERDICT_CREDENTIAL_UNCONFIRMED`, instantiate `CredentialRetry` using `BACKGROUND_CREDENTIAL_RETRY_BUDGET` (or `LAUNCH_CREDENTIAL_RETRY_BUDGET` for launch paths).
  3. Ensure no admission permits or locks are held while sleeping.
  4. Add tests using the SSH shim in `tests/sdd_store/test_sidecar_clone_retry_credentials.py` and reset `_EXHAUSTED_HOSTS` in teardown.

---

### Rank 3: [`sase-zo`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sdd/beads/events/issues/sase-zo.jsonl) — `sase repo open` Rejects Configured Sidecars Under Project Display Names
* **Type / Size / Status:** `bug` / `small` / `ready` (**10 independent +1 confirmations**)
* **Justification:** **Severe Workflow Blocker**. SASE core memory mandates that agents use `sase repo open` for all cross-repo operations. However, in `src/sase/main/repo_handler_common.py:match_repo_record`, candidate records are filtered comparing `RepoRecord.project` against `ProjectContext.project_name`. Because inventory records carry `project="sase"` and `project_key="gh_sase-org__sase"`, all configured candidates are erroneously pruned. Running `sase repo open research` fails with exit code 2: `Unknown repo`. Ten separate agent runs have been blocked by this defect.
* **Recommended Solution:**
  1. In `src/sase/main/repo_handler_common.py:match_repo_record` and `src/sase/main/repo_open_external.py:_unknown_repo_error`, normalize project comparison to match against both canonical `project_key` and display `project_name`.
  2. Add regression tests in `tests/main/test_repo_open.py` asserting that `sase repo open research` and `sase repo open sase--research` resolve cleanly.

---

### Rank 4: [`sase-v6`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sdd/beads/events/issues/sase-v6.jsonl) — `rust-lsp-install` Silently Fails and Exits 0 on Custom Cargo Target Dirs
* **Type / Size / Status:** `bug` / `small` / `ready` (**5 independent +1 confirmations**)
* **Justification:** **Silent Tooling Corruption**. `Justfile` recipe `rust-lsp-install` hardcodes source path `src="{{ sase_core_dir }}/target/release/sase-xprompt-lsp"`. On developer and server hosts where Cargo is configured with a global `target-dir` (such as `~/.cargo/config.toml` configuring `target-dir = "/mnt/poseidon/cargo-target"`), the binary is built elsewhere. The install recipe executes:
  `cp "$src" "$tmp"; chmod +x "$tmp"; mv -f "$tmp" "$dest"; printf "[rust-lsp-install] installed %s\n" "$dest"`
  Without `set -e`, failed `cp`/`mv` commands are ignored and `printf` exits 0. Developers and agents silently run stale LSP binaries indefinitely.
* **Recommended Solution:**
  1. Add `set -euo pipefail` to the `rust-lsp-install` recipe in `Justfile`.
  2. Dynamically determine the Cargo target path via `cargo metadata --format-version 1 --no-deps` or `CARGO_TARGET_DIR`.
  3. Validate that `test -x "$dest"` succeeds and that `.venv/bin/sase-xprompt-lsp --version` executes before reporting success.

---

### Rank 5: [`sase-15o`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sdd/beads/events/issues/sase-15o.jsonl) — Antigravity (`agy`) Trajectory Extraction and No-Progress Detection Silently Off
* **Type / Size / Status:** `bug` / `large` / `ready` (**2 independent +1 confirmations**)
* **Justification:** **Core Provider Telemetry Loss**. In `src/sase/llm_provider/_subprocess_agy.py`, `_SUPPORTED_AGY_TRAJECTORY_VERSIONS` is hardcoded to `frozenset({"1.0.10"})`. The environment's Antigravity CLI has updated to version `1.2.7+`. Because version matching is an exact string set, SASE silently disables trajectory tool-call extraction, token accounting, and structural no-progress detection for all `agy` agent runs, causing looping agents to waste runner slots.
* **Recommended Solution:**
  1. In `src/sase/llm_provider/_subprocess_agy.py`, replace the strict frozenset with a semver compatibility range (`>=1.0.10, <2.0.0`) or extend the allowlist to include `1.2.7+`.
  2. Implement dynamic schema checking on `transcript.jsonl` rather than failing closed on patch-level version bumps.
  3. Add regression tests validating trajectory parsing against current `agy` 1.2.7 output.

---

### Rank 6: [`sase-1q3`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sdd/beads/events/issues/sase-1q3.jsonl) — Pytest Inherits `SASE_MODEL_OVERRIDE` and Fails Model/Provenance Assertions
* **Type / Size / Status:** `ci` / `small` / `ready`
* **Justification:** **Test Isolation Contamination**. When `SASE_MODEL_OVERRIDE` is exported in the ambient environment (common during development or agent subshell runs), pytest fails **7 assertions** across `test_workflow_executor.py`, `test_init_skills_deploy.py`, `test_sync_checkpoint.py`, and `test_commit_workflow_publication_outcomes.py`. `tests/_conftest_environment.py::_clear_agent_env_vars` scrubs `SASE_AGENT*` and `SASE_MODEL_ALIAS_OVERRIDES`, but omits `SASE_MODEL_OVERRIDE`.
* **Recommended Solution:**
  1. In `tests/_conftest_environment.py::_clear_agent_env_vars`, add `"SASE_MODEL_OVERRIDE"` to the cleared environment variables list.
  2. Preserve explicit per-test overrides via `monkeypatch.setenv`.
  3. Add a regression test verifying that setting `SASE_MODEL_OVERRIDE` prior to running pytest does not bleed into test fixtures.

---

### Rank 7: [`sase-1r4`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sdd/beads/events/issues/sase-1r4.jsonl) — Signature-Skew `TypeErrors` Escape Update-Skew Classification (Zombie Monitors)
* **Type / Size / Status:** `bug` / `large` / `ready` (Filed 2026-11-03)
* **Justification:** **Process Zombie Leak**. When SASE updates live while background monitors are running, function signature changes raise `TypeError`. The update-skew classifier only checks for `ImportError` and `AttributeError`, ignoring `TypeError`. Consequently, staged monitors crash unhandled and become orphaned zombie processes that never settle, report completion, or release workspace resources.
* **Recommended Solution:**
  1. In `src/sase/monitor/` and the update-skew classifier, detect `TypeError` exceptions originating from post-update caller frames.
  2. Route identified signature-skew errors to `sase-1jf`'s resume-in-place recovery path.
  3. Add a unit test simulating a live function signature shift across reload boundaries.

---

### Rank 8: [`sase-1qv`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sdd/beads/events/issues/sase-1qv.jsonl) — Slot-Refusal Policy Still Lives in Python Despite Claimed Rust Core Binding
* **Type / Size / Status:** `bug` / `medium` / `ready` (+1 confirmation)
* **Justification:** **Core Architectural Invariant Breach**. Core Memory Section 1.3 (*Rust Core Backend Boundary*) and Decision Record 29 (*The Rust Core Is Required*) mandate that shared domain and admission behavior belongs in `sase_core` in Rust. Epic `sase-1pn` closed claiming quarantine and slot-refusal logic had moved to Rust, but the code was never merged and remains in Python.
* **Recommended Solution:**
  1. Open linked repo `sase-core` with `sase repo open sase-core`.
  2. Implement runner slot-refusal and admission evaluation in `crates/sase_core/src/runner/admission.rs`.
  3. Expose the API via PyO3 bindings in `sase_core_rs`.
  4. Replace the legacy Python implementation in `src/sase/agent/` with the Rust binding call.
  5. Bump `sase-core-revision.txt` to pin the new core commit.

---

### Rank 9: [`sase-1i6`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sdd/beads/events/issues/sase-1i6.jsonl) — Federation IPC Tests Fail Due to `AF_UNIX` Socket Path Exceeding 108 Chars
* **Type / Size / Status:** `ci` / `small` / `ready`
* **Justification:** **Deterministic Test Failure in Workspace Clones**. Linux Unix domain sockets have a hard 108-character sockaddr limit. In `tests/test_dispatch_federation.py:632`, temporary sockets are created under the pytest `tmp_path`. When tests run inside deep workspace clones (such as `~/.local/state/sase/workspaces/sase-org/sase/sase_<N>/...`), socket path lengths exceed 108 characters, causing `server.bind()` to throw `OSError: AF_UNIX path too long` and killing the test thread.
* **Recommended Solution:**
  1. In `tests/test_dispatch_federation.py`, update the socket fixture to bind under `/tmp` (e.g. `tempfile.TemporaryDirectory(dir="/tmp")`) using short socket identifiers.
  2. Verify that `test_ipc_client_decodes_success_and_error_frames` passes reliably from any arbitrary directory depth.

---

### Rank 10: [`sase-1qu`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sdd/beads/events/issues/sase-1qu.jsonl) — `test_update_shortcut_dispatch_performs_no_disk_or_subprocess_work` Fails Cold
* **Type / Size / Status:** `ci` / `small` / `ready`
* **Justification:** **Order-Dependent CI Flakiness**. `tests/ace/tui/test_log_panel_keymap.py::test_update_shortcut_dispatch_performs_no_disk_or_subprocess_work` monkeypatches `Path.read_text`. If this test runs first in a fresh pytest-xdist worker (cold cache), the keymap default loader attempts to read config from disk, hits the monkeypatch, and fails. It only passes if another test previously populated the keymap cache.
* **Recommended Solution:**
  1. In `tests/ace/tui/test_log_panel_keymap.py`, explicitly call the keymap cache warmer before applying `Path.read_text` monkeypatches.
  2. Verify that running the test alone in a cold process passes consistently.

---

## 3. Notable Secondary Candidates / Deferred Work
* **`sase-1qm` (Bug / Large)**: *Host completion refuses an unchanged prepared-completion intent with `stale_worktree_fingerprint`*. High-value cross-repo completion bug in `completion_eval.rs`. Positioned just outside the top 10 due to reproducibility complexity.
* **`sase-1el` (Bug / Large)**: *Bead-assigned phase agents cannot hand off (`missing_gate_turn_row`)*. High-impact agent handoff issue; recommended to tackle immediately once epic `sase-1qz` finishes.
* **`sase-j0` (Untyped / Large / +38)**: *`just check-full` test cost budgets exceeded*. Currently `in_progress` and should remain deferred while epic `sase-1r2` lands release v0.19.0 to avoid budget baseline collisions.

---

## 4. Execution Plan & Artifacts

The research report has been written and permanently registered in SASE artifact storage:
- **Report Location:** [`sase/repos/research/202611/top_10_impactful_task_beads__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202611/top_10_impactful_task_beads__gem.md)
- **Artifact Reference:** `research:202611/top_10_impactful_task_beads__gem.md` (`explicit:f68ec3e9c953e00ce62ec1c4`)
- **Finalizer Declaration:** Submitted and accepted (`commit` for `sdd:research`).
