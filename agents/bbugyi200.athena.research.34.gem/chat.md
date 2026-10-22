# Chat History - ace-run (research.34.gem)

- **TIMESTAMP:** 2026-10-01 10:43:05 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.34.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261001_102713.md`

## Prompt

%id(gem, clan=research.34)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.34.cdx`, `research.34.cld`, `research.34.grk`, `research.34.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Why is master failing in CI for
this project? What can I do to fix this an prevent this from happening again in the
future? Can you do some research with the goal of answering these questions? Make sure
your report is excellent, concise, and beautiful. End your analysis with a recommended
solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__gem` suffix, i.e. `<stem>__gem.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

# Research Report Summary: Master Branch CI Failures and Prevention Plan

**Researcher Identity:** `research.34.gem`  
**Report Location:** [`sase/repos/research/202610/ci_master_failure_root_cause_and_prevention__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202610/ci_master_failure_root_cause_and_prevention__gem.md)  
**Registered Artifact Reference:** `research:202610/ci_master_failure_root_cause_and_prevention__gem.md` (`file:explicit:b834937818ade70c3c9cc7a4`)

---

## 1. Executive Summary

Since **September 18, 2026** (spanning over **1,100 commits** up to current HEAD [`781063e38e`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20)), the `master` branch in GitHub Actions CI under the [`Master Gate`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.github/workflows/master-gate.yml) workflow has been failing on every push. The last successful run on `master` was run `#35299164480` at commit [`f90c6b549f`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20); the initial failure began on commit [`5cb968c8cb`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20).

The problem consists of two coupled layers:
1. **The Structural Breakdown:** Why commits keep landing on `master` despite CI being persistently red.
2. **The Active Failures on HEAD:** 12 specific lint and test failures across 7 test shards and the lint job.

---

## 2. Why Master Is Failing in CI

### A. The Structural Breakdown (Why Broken Commits Kept Landing)

1. **Direct Trunk Pushes Without GitHub Branch Protection:**  
   Querying the repository branch protection via `gh api repos/:owner/:repo/branches/master/protection` returns `HTTP 404: Branch not protected`. Autonomous SASE agent turns finish by having host finalizers execute `git push origin master` directly. With no branch protection rules requiring passing status checks before pushing, GitHub accepts every push unconditionally.

2. **Scoped Local Verification vs. Exhaustive CI Matrix:**  
   Agents locally run `just check` (or `sase tool run just check`), which intentionally executes only `just test-scoped` (tests covering files modified in the active turn). In contrast, the GitHub Actions [`Master Gate`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.github/workflows/master-gate.yml) workflow runs `just test` across 8 deterministic shards (the entire non-visual test suite). Changes breaking unselected downstream modules were never run by agents prior to landing.

3. **Triage Receipts (`no_new_failures`) vs. Bare CI Execution:**  
   Under [`sase/sase.yml`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/sase.yml), the `check` tool accepts receipts with `[pass, no_new_failures]`. Failures classified as `KNOWN` (e.g. Symvision unused symbols) permit landing because the local tool verdict is `no_new_failures`. However, GitHub Actions runs bare `just lint` and `just test` commands directly. GitHub Actions does not evaluate SASE triage receipts or forgive "known" failures; an exit code `1` immediately fails the workflow.

4. **Python Runtime Skew (Python 3.12 in CI vs. Python 3.14 Locally):**  
   Local development environments run Python 3.14.7 (chosen by `uv` satisfying `>=3.12`), whereas [`.github/workflows/master-gate.yml`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/.github/workflows/master-gate.yml) pins `python-version: '3.12'`. Python 3.14 changed `argparse` choices formatting (omitting duplicate metavars on short options). Certain tests authored and verified on Python 3.14 fail deterministically on Python 3.12 in CI.

---

### B. Concrete Active Failures on HEAD ([`781063e38e`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20))

| Job / Shard | Target / Test | Immediate Root Cause |
| :--- | :--- | :--- |
| **Lint** | `_lint-symvision` | Unused public symbols: [`HandoffSubmitResult`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/tool/handoff_launch.py), [`StarterResolution`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/tool/starter.py), and [`owner_ref`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/tool/owner.py). |
| **Test (Shard 2)** | [`test_agent_header_panel.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/widgets/test_agent_header_panel.py) | `ImportError: cannot import name 'test_hint_document_forces_expansion'` caused by commit `c6b802a647` renaming the test in the implementation module without updating the re-export facade. |
| **Test (Shard 4)** | [`test_contract_manifest.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_contract_manifest.py) | Fails collection (`pytest -m contract --collect-only` exit 2) due to Shard 2's `ImportError` crashing global test collection. |
| **Test (Shard 3)** | [`test_config_schema_repositories.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_config_schema_repositories.py) | Assertion mismatch after commit `e300173faf` generalized the schema description to `<role>`. |
| **Test (Shard 7)** | [`test_memory_log.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/main/test_memory_log.py) | Output dictionary contains new tracking fields (`blob_oid`, `included_blob_oids`) added in `297faf1d38`. |
| **Test (Shard 7)** | [`test_parser_command_help.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/main/test_parser_command_help.py) | Synopsis string expects `{agent-docs,init,list,log,read,show,web}`, missing `history` added in `sase-1dr.5`. |
| **Test (Shard 7)** | [`test_agent_artifact_directory_operation_audit.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_agent_artifact_directory_operation_audit.py) | `quarantine_local_object` added to attachments lifecycle without registering in `_REVIEWED_DIR_OPERATION_CONTEXTS`. |
| **Test (Shard 6)** | [`test_kind_coverage.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/completion/test_kind_coverage.py) | `memory/history:at` slot lacks a completion `ValueKind` or value hint in [`kinds.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/completion/kinds.py). |
| **Test (Shard 5)** | [`test_partial_launch_cleanup.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_partial_launch_cleanup.py) | `fail_launch` mock rejects `history_text` parameter added to [`launch_agents_from_cwd`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/main/query_handler/_launch.py). |
| **Test (Shard 5)** | [`test_axe_run_agent_runner_started_at.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_axe_run_agent_runner_started_at.py) | Setup index update call count increased from 3 to 4. |
| **Test (Shard 8)** | [`test_force_reuse_launch_seam_rejection.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_force_reuse_launch_seam_rejection.py) | Mock expectation failed due to `launch_agents_from_cwd(..., history_text=None)`. |
| **Test (Shard 8)** | [`test_show_images.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_bead/test_show_images.py) | Expects `-i, --images`, which Python 3.12 renders as `-i {choices}, --images {choices}`. |

---

## 3. What to Do to Fix This and Prevent Recurrence

### Immediate Remediation (Restoring Green Master)
1. **Fix Symvision Lint Symbols:** Make `_HandoffSubmitResult` and `_StarterResolution` private in their respective modules; drop the unused `owner_ref` export from [`src/sase/tool/owner.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/tool/owner.py).
2. **Fix Re-Export Facade:** Update [`tests/ace/tui/widgets/test_agent_header_panel.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/ace/tui/widgets/test_agent_header_panel.py) to import `test_hint_document_leaves_header_collapsed` instead of `test_hint_document_forces_expansion`.
3. **Synchronize Schema & Audit Lists:**
   - Update [`tests/test_config_schema_repositories.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_config_schema_repositories.py) to assert `~/.sase/projects/<project_key>/repos/<role>`.
   - Add `src/sase/bead/attachments/lifecycle.py:quarantine_local_object` to `_REVIEWED_DIR_OPERATION_CONTEXTS` in [`tests/test_agent_artifact_directory_operation_audit.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_agent_artifact_directory_operation_audit.py).
4. **Update Assertions for Stale Tests:**
   - Add `"blob_oid": None` and `"included_blob_oids": []` to [`tests/main/test_memory_log.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/main/test_memory_log.py).
   - Add `history` to the synopsis in [`tests/main/test_parser_command_help.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/main/test_parser_command_help.py).
   - Register `memory/history:at` in [`src/sase/completion/kinds.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/src/sase/completion/kinds.py).
   - Update `fail_launch` in [`tests/test_partial_launch_cleanup.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_partial_launch_cleanup.py) to accept `**kwargs`.
   - Update `history_text=None` in [`tests/test_force_reuse_launch_seam_rejection.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_force_reuse_launch_seam_rejection.py).
   - Update setup call count to 4 in [`tests/test_axe_run_agent_runner_started_at.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_axe_run_agent_runner_started_at.py).
   - Check `"--images"` and `"-i"` separately in [`tests/test_bead/test_show_images.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/tests/test_bead/test_show_images.py) to tolerate both Python 3.12 and 3.14 formatting.

### Systemic Prevention (Stopping Future Regressions)
1. **Enable GitHub Branch Protection on `master`:** Require the `Master Gate` status checks (`lint` and all 8 `test` shards) to pass before integration, or route host finalizer pushes to a `staging` branch that auto-fast-forwards `master` only upon a green run.
2. **Eliminate the Landing Bypass for Unclean Checks:** Tighten host completion finalizer rules so that `no_new_failures` does not permit pushing to `master` when whole-repo linters (`just _lint-symvision`) exit with non-zero status codes.
3. **Pin Python Version Across Local Dev and CI:** Check in a repository-level `.python-version` pinned to `3.12` so that local virtualenvs created by `uv` exactly match the GitHub Actions runner runtime.

---

## 4. Snapshot Registration Verification

The report was written and snapshotted:
```bash
sase artifact create \
  -p "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202610/ci_master_failure_root_cause_and_prevention__gem.md" \
  -l "research:202610/ci_master_failure_root_cause_and_prevention__gem.md"
```
- **Artifact ID:** `explicit:b834937818ade70c3c9cc7a4`
- **Audit Ref:** `file:explicit:b834937818ade70c3c9cc7a4`
- **Finalizer Declaration:** Submitted and accepted for repo `repo-85708adcb2ac` (`sdd:research`).
