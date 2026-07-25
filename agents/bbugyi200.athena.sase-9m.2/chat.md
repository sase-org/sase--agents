# Chat History - ace-run (sase-9m.2)

- **TIMESTAMP:** 2026-07-25 13:13:25 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-9m.2

## Prompt

#gh:gh_sase-org__sase
%id(2, clan=sase-9m, bead=sase-9m.2)
%model:@medium_phase_worker
%auto
Can you complete the work for bead sase-9m.2? The bead is already reserved for you and assigned to your agent
name: it was set to status=claimed while your agent was waiting, and the runtime promoted it to
status=in_progress before you started reading this. Do not set either status by hand. Read its description and
design file, do the work, and close the bead. Do NOT close the parent epic. Do NOT create new beads.

## Response

I'll start by reading the bead.

Now writing the store module.

Now the recording hook in `prompt_store.py`:

All 19 pass. Now the full check:

Now make the store path private and register the epic symbols.

Now the epic-symbol whitelist entries:

Lint is clean. Now the full check:

Now closing the bead:

Bead sase-9m.2 is done and closed. The parent epic sase-9m is untouched.

## What landed

**`src/sase/history/prompt_placeholders.py`** (new) — the durable store:
- `~/.sase/prompt_placeholders.json`, `version: 1`, entries persisted already in display order (`count` desc, `last_used` desc, `text` asc), so reads are a plain sequential parse.
- Retention is LRU, not count-based, so a brand-new tag can establish itself in a full store.
- Atomic writes (tempfile + `os.replace`) under a dedicated `prompt_placeholders.lock` `fcntl` lock, kept separate from the prompt-history lock so submit-path writes don't contend.
- Public surface as specced: `common_placeholder_limit()`, `record_prompt_placeholders()`, `load_common_placeholders()`, `common_placeholder_source_token()`, `seed_common_placeholders_from_history()`. Every read treats missing/truncated/version-mismatched files as empty; every write failure is logged at debug and swallowed.
- Seed scans at most the 24 newest shards and runs only when the file is absent; it re-checks for the file under the lock so it can never clobber recorded uses.

**`src/sase/history/prompt_store.py`** — recording hooked into both choke points via lazy import: `add_or_update_prompt()` records *before* the `is_recordable_prompt` early return (short prompts contribute tags without entering history), and `record_failed_launch_prompt()` records after the strip guard. Cancelled/abandoned prompts contribute too; that's noted in both docstrings.

**`tests/history/test_prompt_placeholders.py`** — 19 tests covering every case the plan listed (insert/increment, repeat-in-one-prompt, display order, LRU eviction, limit lowering, `0` disable, four corrupt/mismatched payloads, write failure not escaping `add_or_update_prompt`, short prompts, seeding + shard bound + no-op-when-present).

**`Justfile`** — four `--epic-symbol 'sase-9m(...)'` symvision entries for the store APIs that phase `wiring` (sase-9m.3) will consume. They self-clean when that phase lands.

Config plumbing (`common_placeholder_count` in `default_config.yml`, the JSON schema, `PromptCompletionSettings`) is deliberately left to phase `wiring` per the plan; `common_placeholder_limit()` reads the field through the cached merged config and defaults to 100 until then.

## Check status

`just lint` (ruff, mypy, pyscripts, symvision, toobig) and `just fmt` pass clean; the new module and `tests/history/` (284 tests) pass.

Two failures in `just check` are pre-existing on master, not from this work — I verified both against a clean tree:
- `tests/ace/tui/visual/test_ace_png_snapshots_agents_retry_e2e.py::test_real_fakey_running_fallback_png_snapshot` fails at HEAD without my changes (golden drift from commit 899a257f2).
- `tests/ace/tui/widgets/test_agent_list_status_indicators.py` was committed unformatted, blocking the fmt gate before any other stage could run. I applied the one-line `ruff format` fix so `just check` gets past fmt — it's outside this bead's scope, so revert it if you'd rather it land with the sase-9k work.

`test_suite_gate_integration` and `test_diff_cache` also failed once under the parallel run but pass consistently on re-run; they look load-flaky.

Bead is confirmed CLOSED. Committing now.

Committed and pushed.

- **Bead `sase-9m.2`**: verified `CLOSED` before committing (it was already closed; `sase commit` re-ran the idempotent close). Parent epic `sase-9m` untouched.
- **Commit `9f8f04a4a`** — `feat(history): add durable common-placeholder store (sase-9m.2)`, staged with an explicit `-f` per file:
  - `src/sase/history/prompt_placeholders.py` (new store)
  - `src/sase/history/prompt_store.py` (recording hooks at both choke points)
  - `tests/history/test_prompt_placeholders.py` (19 tests)
  - `Justfile` (symvision epic-symbol entries for the four APIs sase-9m.3 consumes)
  - `tests/ace/tui/widgets/test_agent_list_status_indicators.py` (the one-line `ruff format` fix that was blocking the fmt gate — noted in the commit body as out-of-scope so it's easy to spot)
- The `just fix` pre-commit hook passed; working tree is clean and `master` is in sync with `origin/master`.

One non-blocking note from the tool: `⚠️ Primary commit succeeded; agent-hood publication will retry automatically`. The commit and push landed; only the agent-hood publication step deferred to a retry.
