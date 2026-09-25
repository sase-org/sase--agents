# Chat History - ace-run (08i--code)

- **TIMESTAMP:** 2026-08-20 08:13:48 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** 08i--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-08i__plan-260820_073638.md`
- **2. --code** — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-08i__code-260820_073638.md`

## Prompt

%model:@small
#gh:gh_sase-org__sase @sase/repos/plans/202608/alias_history_increment.md

The above plan has been reviewed and approved. Implement it now.


## Response

I'll implement the approved alias-history increment plan: first I'll read the current modal/state code, tests, and docs so the 10-run step is isolated from the global ACE page size.

Next I’ll locate the docs and every caller of the alias-history limit helper so the 10-run step stays local and doesn’t leak into other ACE paging.

I’ll check existing naming and tests so the 10-run constant and last-row unload coverage match the rest of the codebase.

I have the current coupling. Next I’ll pin a named 10-run step in state, drop the global page-size dependency from the modal, and update tests and docs.

I’ll add last-row fallback coverage on unload, then tidy the docs table alignment.

Install finished. I’ll run the alias-history tests first, then the page-size regression suite.

Focused tests passed. Next I’ll run `just check` for the whole-repo lint gates and the scoped test lane.

The scoped suite escalated and one unrelated test failed. I’ll inspect that failure and confirm it isn’t from the alias-history change.

The failing test is date-sensitive and unrelated to alias history. I’ll file it as a CI task after checking for duplicates, then wrap the implementation.

Launch Control alias history now steps by 10 runs, independently of the global ACE page size.

**Behavior**
- `Ctrl+J` adds exactly 10 to the per-alias history window; `Ctrl+K` subtracts 10.
- Unload still floors at `llm_provider.model_alias_history_limit` (no-op at that initial window, including non-default values such as 25).
- Reloads stay cached and off the UI thread; load-more keeps the highlight, unload falls back to the last remaining row.
- `ace.page_size` stays 100 and still drives Artifacts, prompt history, revive history, and the other paged ACE surfaces.

**Code**
- Named invariant `ALIAS_HISTORY_LIMIT_STEP = 10` in `alias_history_state.py`; `adjusted_alias_history_limit()` no longer takes a page size.
- `AliasHistoryModal` no longer reads `get_ace_page_size()`.

**Tests and docs**
- State and mounted-modal tests cover `10 → 20 → 10`, `25 → 35 → 25`, cached reloads, the unload floor, selection retention, last-row fallback, and usage-strip recomputation.
- `docs/ace.md` and `docs/configuration.md` describe the 10-run exception without changing the global setting.

**Verification**
Focused alias-history, page-size, prompt-history, and revive-history tests passed (59). `just check` lint gates passed; the scoped lane then escalated to the full suite (`core-identity-changed` after a fresh `just install`) and ran 34,963 passing tests.

The one failure is unrelated: `tests/test_llm_provider_usage_limit_disable.py::TestHandlePossibleUsageLimit::test_codex_reset_at_date_failure_writes_until_disable_at_parsed_instant`. It hardcodes a Codex reset of `Aug 20th, 2026 6:38 AM`; the Python time freeze does not reach the Rust `expires_at must be in the future` check, so after that calendar instant the disable is rejected. Isolated rerun failed on the same tree. Recorded as a `DISCOVERED ISSUE` on in-progress epic `sase-n4.5` rather than as a new task.

The implementation is already on disk. I'll read the commit skill and land those uncommitted alias-history changes now.

I'll record the commit skill, then inspect the uncommitted alias-history diff so the message matches the actual change.

The diff matches the approved plan. I'll write the commit message and land it with the stitch workflow.

The commit is still running; I'll wait on it in this turn rather than ending early.

Committed `007cec13c` on `master`: **fix(ace): step alias history by 10 runs, not ace.page_size**. Working tree is clean and in sync with `origin/master`.

Launch Control alias history now steps by 10 runs, independently of the global ACE page size.

**Behavior**
- `Ctrl+J` adds 10 to the per-alias history window; `Ctrl+K` subtracts 10.
- Unload still floors at `llm_provider.model_alias_history_limit` (including non-default values such as 25).
- Reloads stay cached and off the UI thread; load-more keeps the highlight; unload falls back to the last remaining row.
- `ace.page_size` stays 100 and still drives Artifacts, prompt history, revive history, and the other paged ACE surfaces.

**Code**
- Named invariant `ALIAS_HISTORY_LIMIT_STEP = 10` in `alias_history_state.py`.
- `adjusted_alias_history_limit()` no longer takes a page size.
- `AliasHistoryModal` no longer reads `get_ace_page_size()`.

**Docs**
- `docs/ace.md` and `docs/configuration.md` describe the 10-run exception without changing the global setting.
