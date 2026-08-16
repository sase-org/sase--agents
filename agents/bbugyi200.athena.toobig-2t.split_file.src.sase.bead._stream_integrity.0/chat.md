# Chat History - ace-run (toobig-2t.split_file.src.sase.bead._stream_integrity.0)

- **TIMESTAMP:** 2026-08-16 02:16:51 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** toobig-2t.split_file.src.sase.bead._stream_integrity.0
- **PROMPT:** `~/.sase/multi_prompts/202608/sase_org_sase-multiprompt-260815_232412.md`

## Prompt

#gh:sase-org/sase
%id(split_file.src.sase.bead._stream_integrity.0, clan=toobig-2t)
%wait:toobig-2t.split_file.src.sase.ace.tui.modals.models_panel_rendering.0
%wait(runners=3)
%auto %wait(priority=20) Can you help me split the `src/sase/bead/_stream_integrity.py` file up into multiple files? Use your best
judgement, but let's aim to keep all files <=500 lines of code.

## Response

I'll start by reading the file to understand its structure.

Now let me write the split modules.

Still compiling the Rust core. Waiting on that before running the gates.

All 17 tests pass. Now the full gate — this takes a while, so I'll run it through a monitor.

Confirmed pre-existing: those same failures reproduce on the clean tree with my changes stashed. Let me file a bead for them per project rules.

Split `_stream_integrity.py` (791 lines) into five modules, all well under 500:

| File | Lines | Responsibility |
|---|---|---|
| `_stream_integrity.py` | 311 | The three public guards + `BeadStreamIntegrityError` |
| `_stream_integrity_git.py` | 205 | Read-only git probes + history-record parsing |
| `_stream_integrity_analysis.py` | 203 | Pure append-only comparison (`analyze_stream_against_ancestor`) |
| `_stream_integrity_files.py` | 92 | Path predicates + JSONL parse/encode/read/write |
| `_stream_integrity_messages.py` | 82 | Operator-facing failure wording |

Design notes:

- **Followed the flat `_prefix` sibling convention** already used in `src/sase/bead/` (`_db_codec.py`, `_sync_git.py`, …) rather than a package directory.
- **Symbols moved across files are public** (`show_text`, `parse_stream_text`, …) because Symvision rejects cross-file imports of `_`-prefixed names. Symbols that stay in one file kept their `_` prefix (`_StreamAnalysis`, `_HistoryRecord`, `_diff_paths`, `_short_sha`).
- **No behavior change.** The only edits to moved code were two local-variable renames in the facade to avoid shadowing the now-imported functions: `worktree_streams` → `local_streams`, `merge_base` → `base`.
- `_STREAM_DIR_PARTS` stayed with both its users by moving `stream_dir_relpath` into the files module — it's pure path logic, so nothing needs a cross-module private constant import.

Test updates: `tests/test_bead/test_stream_integrity.py` imports the four helpers from their new homes, and the `run_sdd_git` monkeypatch target moved to `sase.bead._stream_integrity_git`. All 17 tests pass.

**Verification — `just check`:** all 13 lint gates green (ruff, mypy, symvision, toobig, keep-sorted, formatting, SASE validation). The test lane escalated to the full suite and reported 83 failures / 45 errors — **all pre-existing on master and unrelated**. I confirmed this by stashing my changes and reproducing the same failures on the pristine tree.

Per project rules I filed those failures rather than ignoring them, via `/sase_new_task`:
- `sase-ml` **+1** — the gate/ops/launch-CLI set. My repro adds new evidence: it fails in a *serial* 45-test run, so parallelism isn't a necessary condition, which strengthens that bead's live-host-state theory.
- `sase-mv` **+1** — `test_config_cache.py`, a sibling node to the one it names.
- `sase-m6` **DISCOVERED ISSUE note** — ~25 deterministic ACE TUI failures traced to commit `3c3909c31` (`SASE_BEAD=[sase-m6.6.1.6]`, a phase of that in-progress epic): a `PatchFilterBar` query-before-mount `NoMatches`, and an `f`/`F` fork-keymap disagreement between `default_config.yml` and the footer/help tests. Routed to the epic rather than a new task since its own commit introduced both, and I did not `+1` the retired umbrella `sase-ct` — these are deterministic, not flakes.

These are my changes from this session. Committing them now.

Committed and pushed as `35006a841`; working tree is clean and in sync with `origin/master`.

## What landed

`src/sase/bead/_stream_integrity.py` (791 lines) split into five flat `_stream_integrity_*` siblings, matching the existing convention in `src/sase/bead/`:

| File | Lines | Responsibility |
|---|---|---|
| `_stream_integrity.py` | 311 | The three public guards + `BeadStreamIntegrityError` |
| `_stream_integrity_git.py` | 205 | Read-only git probes + history-record parsing |
| `_stream_integrity_analysis.py` | 203 | Pure append-only comparison (`analyze_stream_against_ancestor`) |
| `_stream_integrity_files.py` | 92 | Path predicates + JSONL parse/encode/read/write |
| `_stream_integrity_messages.py` | 82 | Operator-facing failure wording |

No behavior change — the only edits to moved code were two local-variable renames in the facade to avoid shadowing newly imported functions. Symbols crossing a file boundary dropped their leading underscore (Symvision rejects cross-file private imports); module-local ones kept it.

## Verification

Verification was completed before this commit: all 17 tests in `tests/test_bead/test_stream_integrity.py` pass, and `just check`'s 13 lint gates are green. The `just check` test lane escalated to the full suite and surfaced 83 failures / 45 errors, which I confirmed are pre-existing by reproducing them on a stashed, pristine tree — they were filed per project rules (`sase-ml` +1, `sase-mv` +1, and a discovered-issue note on the in-progress epic `sase-m6`).

## One thing to note

The commit succeeded, but the tool warned that this project has **2 quarantined agent-hood publication requests** predating this work, so the agent link written to this commit may not resolve until you run `sase agent sync --retry-quarantined`. I left that alone since it's project-wide state, not something this change introduced.
