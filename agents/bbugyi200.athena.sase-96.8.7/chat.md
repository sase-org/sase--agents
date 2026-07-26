# Chat History - ace-run (sase-96.8.7)

- **TIMESTAMP:** 2026-07-25 16:38:34 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-96.8.7

## Prompt

#gh:gh_sase-org__sase
%id(7, clan=sase-96.8, bead=sase-96.8.7)
%model:@medium_phase_worker
%auto
%w:sase-96.8.2,sase-96.8.3
%w(bead=sase-96.8.2)
%w(bead=sase-96.8.3)
Can you complete the work for bead sase-96.8.7? The bead is already reserved for you and assigned to your agent
name: it was set to status=claimed while your agent was waiting, and the runtime promoted it to
status=in_progress before you started reading this. Do not set either status by hand. Read its description and
design file, do the work, and close the bead. Do NOT close the parent epic. Do NOT create new beads.

## Response

I'll start by reading the bead.

Now let me write the reaper module.

Now the reaper module:

Now the tests:

Now update the chop registry test and add the contract test:

Now add a `managed_tmpdir_root` test to the sandbox suite:

I'll wait for the full check to finish.

Still running. Waiting for it to complete.

I'm waiting on the full `just check` run (currently at 4 xdist workers due to token-pool contention). I'll report as soon as it lands.

The check is still running. I'll stop polling and wait for the monitor to fire.

Now add the audit review entry:

Now update the reaper tests for the new field and add index coverage:

Done. Bead **sase-96.8.7** is closed.

## What I built

**`src/sase/core/managed_tmp_reaper.py`** — a bounded reaper for the root `get_sase_managed_tmpdir()` returns, modeled on `tools/run_pytest:_reap_stale_pytest_runs()` (mtime-only staleness, never follows symlinks, swallows `OSError` so a lost race is harmless).

Per-subdirectory horizons, not global:

| Bucket | Horizon | Why |
|---|---|---|
| `editors/` `wrappers/` `viewers/` `commit-messages/` `ace-profiles/` `artifact-pages/` `embedded-artifacts/` `workflow-loader/` `xprompts_catalog/` | 12h | scratch dies with its command |
| `handoff/` `gh-diffs/` | 3d | a launched process may re-read them mid-run |
| `launch-prompts/` `workflow-artifacts/` | 14d | read back by the ACE Agents tab |
| unknown subdirs + stray top-level entries | 3d | nothing writes to the bare root any more |

Managed subdirectories themselves are never removed (they're mount points every `get_sase_managed_tmpdir(...)` caller races to create). Removals are capped at 2,000 per invocation so a first pass over the measured 94k-entry root converges over several runs instead of stalling one.

**`managed_tmp_reap` chop** on the hourly `housekeeping` lumberjack — off every interactive path. It reports `scanned/removed/deindexed/capped` in the chop summary plus a `reclaimed N entries under <root>: editors=…, launch-prompts=…` log line.

One thing the audit surfaced that the design didn't anticipate: reaping a `workflow-artifacts/` directory can orphan an agent-artifact-index row (a workflow launched without an explicit `artifacts_dir` gets one there). The reaper now batches reaped directories into `delete_agent_artifact_index_artifacts`, declared as `BatchedCoverage` in `test_agent_artifact_directory_operation_audit.py`.

## Verification

`just check` is green on fmt, lint (ruff/mypy/keep-sorted/pyscripts), and 22,210 tests except three failures I confirmed are **not** mine:

- `test_diff_cache.py::test_get_agent_diff_invalidates_when_index_changes` — the intra-file pollution bug the plan's Non-goals already documents.
- `test_ace_png_snapshots_tools.py::…agents_tools_panel_full…` — 95/1.5M-pixel renderer drift; reproduces identically with my changes stashed.
- `just _lint-symvision` — `--epic-symbol 'sase-9m(common_placeholder_limit)'` in the `Justfile` went stale mid-run when a sibling agent closed sase-9m. Also reproduces with my changes stashed. Dropping the entry surfaces `common_placeholder_limit` as genuinely unused, so the cleanup (delete the symbol + its tests + the Justfile entry) belongs to sase-9m's lander, not this phase — I left it alone rather than race them.

`test_suite_gate_integration.py::test_scaled_suite_runs_share_capacity_and_release_after_sigkill` failed once under worker-token contention and passes in isolation.

I did **not** run the reaper against the real `$SASE_TMPDIR` — that one-time reclamation is sase-96.8.8's job behind a confirmation gate.

Bead is closed. Now committing.

Committed and pushed.

**Commit:** `15a5a0e67 feat(axe): reap the managed SASE temp root (sase-96.8.7)` — working tree clean, `master` in sync with `origin/master`.

**Bead:** `sase-96.8.7` verified `[CLOSED]` before the commit (parent epic `sase-96.8` untouched).

The 12 files landed as one commit: the `managed_tmp_reaper` module and its `managed_tmp_reap` chop script, the `managed_tmpdir_root()` helper in `paths.py`, the chop registration in `pyproject.toml`/`default_config.yml`, docs for `axe.md`/`configuration.md`, and four test files.

Two notes from the commit run:

- The `before commit` hook ran `just fix` clean.
- Post-commit agent-hood publication for an unrelated hood (`sase-99`) warned that `sase-99.land.f2` is absent from the project inventory. The primary commit succeeded and that step retries on its own; it's not tied to these changes.

One thing resolved itself while I was finalizing: the symvision lint failure I flagged (the stale `sase-9m(common_placeholder_limit)` epic-symbol entry) was fixed upstream by that lane's own lander — `9aee6792b refactor(ace): make the common-placeholder limit helper private (sase-9m)` is now the commit directly beneath mine. Leaving it alone was the right call.
