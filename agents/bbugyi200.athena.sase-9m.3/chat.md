# Chat History - ace-run (sase-9m.3)

- **TIMESTAMP:** 2026-07-25 13:52:40 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-9m.3

## Prompt

#gh:gh_sase-org__sase
%id(3, clan=sase-9m, bead=sase-9m.3)
%model:@medium_phase_worker
%auto
%w:sase-9m.1,sase-9m.2
%w(bead=sase-9m.1)
%w(bead=sase-9m.2)
Can you complete the work for bead sase-9m.3? The bead is already reserved for you and assigned to your agent
name: it was set to status=claimed while your agent was waiting, and the runtime promoted it to
status=in_progress before you started reading this. Do not set either status by hand. Read its description and
design file, do the work, and close the bead. Do NOT close the parent epic. Do NOT create new beads.

## Response

I'll start by reading the bead details.

Now let me start making the edits. Config plumbing first:

Now the Python facade:

Now the TUI result builder:

Now the warm cache mixin:

Now `_file_completion_base.py`:

Now add the trigger-derived flag helper and the warm hook in `_file_completion_base.py`:

Now the open/tab/refresh/accept call sites:

Now refresh and accept:

Now wire the warm calls at the same sites as history words, plus after prompt submission:

Now let's check callers of `placeholder_completion`/candidates elsewhere and run a quick check:

Now let's look at the existing TUI placeholder-completion test file:

Now let me update the test helper app and write the tests:

Now append the new tests:

Now the warm-cache loader tests and a config-parse test:

Now a config-parsing test. Let me find the existing prompt-completion settings tests:

Now let's run the placeholder tests:

All passing. Now let me run `just check`:

I'll wait for the check to finish.

No keep-sorted block there. Making the facade candidate private and whitelisting the metadata dataclass for the polish phase:

Pre-existing failure at HEAD, unrelated to this work. Let me do a final review of the diff:

All checks pass. Now let me close the bead:

Bead **sase-9m.3** (phase `wiring`) is complete and closed.

## What landed

**Config plumbing**
- `ace.prompt_completion.common_placeholder_count` (int, min 0, default 100) added to `PromptCompletionSettings`/`parse_prompt_completion_settings`, `src/sase/default_config.yml`, and `src/sase/config/sase.schema.json`.

**Python facade** (`src/sase/xprompt/placeholder_completion.py`)
- `placeholder_completion(text, line, character, common=())` passes the saved list through to the binding; candidates rehydrate into a source-carrying dataclass, with an unrecognized `source` degrading to `"prompt"` rather than raising.

**TUI result builder** (`src/sase/ace/tui/widgets/placeholder_completion.py`)
- New `PlaceholderCompletionMetadata` attached as each row's `metadata`; `build_placeholder_completion_result(..., common, *, include_common_when_prefix_empty=False)` filters the already-merged list rather than re-implementing matching (D4). Returns `None` when nothing survives, so a bare `<` in prose still opens nothing.

**Warm cache** — new `src/sase/ace/tui/actions/_startup_common_placeholders.py`
- Off-thread staleness check against `common_placeholder_source_token()`, one-time `seed_common_placeholders_from_history()` on the first warm, a generation counter for the memo key, and `_refresh_visible_common_placeholder_surfaces()`. `count: 0` publishes `[]` without touching disk. Registered in `startup.py`, initialised in `_state_init_late.py`, warmed at both prompt-bar mount sites plus `_on_launch_task_complete` so a tag written in one prompt is offered in the next.

**Menu plumbing** — auto passes `False` and records `trigger="auto"`; `Ctrl+T` passes `True` and records `"manual"`; refresh/accept derive the flag from the stored trigger; `_structured_completion_claims_cursor()` passes `True`; the trigger clears in `_clear_file_completion`.

**Tests** — 13 new cases across the facade, the builder, the menu (auto vs. manual, backspace round-trip, accept with/without closing bracket, highlight preservation, cold-cache warm-in, `0` disable), and the cache loader.

## Notes
- The memo in `_placeholder_highlight.py` is now two slots keyed by the empty-prefix rule instead of one slot with the rule in the key — the auto-open path and the precedence check ask for different rules on the same keystroke and would otherwise evict each other every time.
- `just check` is clean except `tests/ace/tui/widgets/file_panel/test_diff_cache.py::test_get_agent_diff_invalidates_when_index_changes`, which I confirmed fails identically at HEAD with my changes stashed.
- Symvision: dropped the three now-satisfied `sase-9m` epic-symbol entries; `common_placeholder_limit` stays whitelisted (it has no consumer outside its own module) and `PlaceholderCompletionMetadata` is newly whitelisted for phase `polish`, which renders from it.
- Phase `core` never raised the `sase-core-rs` floor in `pyproject.toml`. I left it alone: the new binding API is unreleased (sase-core master carries it under an already-published `0.9.2`), and `validate_sase_core_rs_version` requires the declared minimum to exist on PyPI. Dev installs build from the local checkout, so this is only a concern for a released `sase` wheel — it needs a sase-core release before the floor can move.

The bead is closed. The Justfile change is mine (symvision epic-symbol whitelist), so it goes in the commit too.

Committed and pushed. Working tree is clean and `master` is level with `origin/master`.

- **Commit:** `e3e0bd8bb feat(ace): offer saved common placeholder tags in prompt completion (sase-9m.3)` — 24 files, 2 of them new (`_startup_common_placeholders.py`, `test_common_placeholders_cache.py`).
- **Bead:** `sase-9m.3` was already CLOSED; `sase commit` re-ran the close idempotently. Parent epic `sase-9m` untouched, and `sase-9m.4` remains open.
- The `just fix` pre-commit hook ran clean.

One note from the commit output: agent-hood publication didn't complete and will retry on its own. The primary commit and push both succeeded, so nothing is pending on my side.
