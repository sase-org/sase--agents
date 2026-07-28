# Chat History - ace-run (sase-ac.4)

- **TIMESTAMP:** 2026-07-28 08:59:15 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-ac.4

## Prompt

#gh:gh_sase-org__sase
%id(4, clan=sase-ac, bead=sase-ac.4)
%model:@small_phase_worker
%auto
%w:sase-ac.2
%w(bead=sase-ac.2)
Can you complete the work for bead sase-ac.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=claimed while your agent was waiting, and the runtime promoted it to
status=in_progress before you started reading this. Do not set either status by hand. Read its description and
design file, do the work, and close the bead. Closing an assigned phase bead is unaffected by the parent-close
descendant guard. Do NOT close the parent epic. Do NOT create new beads.

## Response

I'll start by reading the bead.

Now the edit:

Now the `prompt_catalog.py` watch-path normalization:

Now let me look at the regression test files.

Now let me add the shared fixture helper and the app subclass to `_completion_helpers.py`.

Now add the soft-completion regression test:

Now add the directory-key-not-offered assertion to test 1:

Both new normalization tests fail without the fix. Now the full check:

Done. Bead `sase-ac.4` is closed.

## What changed

**`src/sase/ace/tui/widgets/_xprompt_arg_hints.py`** — `_xprompt_arg_assist_project_from_text()` now routes both of its disagreeing sources through `canonical_xprompt_project()`: the VCS tag (user-facing name) and the `_prompt_context` fallback (ProjectSpec directory key). One warm catalog build now serves both entry points, and all four call sites (hints, completion menu, soft completion, preview) inherit the fix since they share this derivation.

**`src/sase/ace/tui/prompt_catalog.py`** — `_project_xprompt_dirs()` canonicalizes before resolving per-project xprompt directories, so the source token and `prompt_source_watch_paths()` watch the right paths even if a caller passes a key or alias. Left `_normalize_prompt_catalog_projects()` alone deliberately: canonicalizing there would let the snapshot's cache keys drift from the keys `_ensure_prompt_catalog_project()` tracks, which would schedule a rebuild on every keystroke.

## Tests

- `tests/ace/tui/widgets/_completion_helpers.py` — `CatalogCompletionTestApp` (warm catalog backed by the real `build_xprompt_assist_entries`) and a `registered_project_xprompts()` fixture registering a project whose directory key (`gh_org__proj`) differs from its `PROJECT_NAME` (`proj`).
- `test_auto_xprompt_completion.py` — the reported case end-to-end: `#git:proj #proj/` opens the menu with `#proj/reads` and `#proj/sync`; the `#gh_org__proj/` spelling offers nothing; the prompt-context (directory-key) path resolves to the same menu.
- `test_prompt_live_completion.py` — `<ctrl+l>` soft completion agrees with the menu.

The tag prefix is `#git:` rather than `#gh:` because the `gh` provider plugin isn't installed in the test environment; the widget code path is identical.

Both new normalization tests fail with the src change reverted.

## Verification

`just install`, then fmt/lint/mypy/symvision/toobig green and `just test` at 22929 passed, 7 skipped. `just check` as a whole still exits non-zero at the SDD plan-link validation stage — 229 pre-existing errors across plan files back to 202602, none in anything this change touches. I did not commit; say the word if you want that.

Bead is confirmed closed. Committing now.

Committed and pushed. Working tree clean, `master` in sync with `origin/master`.

**`b449b8a4b` fix(xprompt): normalize ACE completion project identity (sase-ac.4)**

- `_xprompt_arg_hints.py` — `_xprompt_arg_assist_project_from_text()` routes both the VCS-tag name and the `_prompt_context` directory key through `canonical_xprompt_project()`, so hints, the completion menu, soft completion, and the preview share one namespace.
- `prompt_catalog.py` — `_project_xprompt_dirs()` canonicalizes before resolving per-project dirs, fixing source tokens and `prompt_source_watch_paths()` for key/alias callers. `_normalize_prompt_catalog_projects()` intentionally untouched (would drift snapshot cache keys and force a rebuild per keystroke).
- Tests — shared warm-catalog app + fixture registering a project whose key (`gh_org__proj`) differs from its name (`proj`); menu, directory-key-offers-nothing, prompt-context, and `<ctrl+l>` soft-completion cases. Both normalization tests fail with the src change reverted.

Bead `sase-ac.4` was already closed (verified via `sase bead show` before committing; the commit hook's close is idempotent). Parent epic `sase-ac` left open.

Two things to flag:
- The commit printed a warning: this project has **3 quarantined agent-hood publication requests**, so the agent link written into this commit may stay unavailable until `sase agent sync --retry-quarantined` runs. I did not run it — say the word.
- `just check` as a whole still exits non-zero at SDD plan-link validation (229 pre-existing errors across plan files back to 202602, none in files this change touches). fmt/lint/mypy/symvision/toobig are green and `just test` was 22929 passed, 7 skipped.
