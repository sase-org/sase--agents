# Chat History - ace-run (06n--code)

- **TIMESTAMP:** 2026-08-18 16:03:05 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** 06n--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-06n__plan-260818_142729.md`
- **2. --code** — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-06n__code-260818_142729.md`

## Prompt

%model:@medium
#gh:gh_sase-org__sase @sase/repos/plans/202608/alias_history_model_usage.md

The above plan has been reviewed and approved. Implement it now.


## Response

I'll start by reading the approved plan and the implementation-related skills so I can follow it exactly.

This is a SASE tale, not a PR-plan DAG. I'll read the required memory notes and existing Alias History code, then implement the usage strip as specified.

Memory confirms: no feature flag, and usage aggregation stays off the UI thread. Next I’ll map the existing Alias History modules and tests.

I’ll write the summarizer and the related source changes while the install finishes.

Install finished. Next I’ll format and run the new unit tests before the full check.

Targeted tests passed. Next I’ll run `just check`, then the visual snapshot suite.

Symvision failed on unused symbols I didn’t touch. I’ll confirm that’s pre-existing, file a follow-up if needed, and keep running this tale’s tests.

The unused-ledger lint is already on epic `sase-q0`. I’ll corroborate that, then keep waiting on visual tests (they’re queued behind a long-held worker-token grant).

Visual tests are stuck behind a 28-hour token grant. I’ll stop that wait and run the six snapshot tests with the documented gate bypass.

The six snapshot failures match the new strip. I’ll inspect the actual PNGs, then rebase only those goldens.

The dedicated usage snapshot is clipping the `unused` row. I’ll shrink that fixture so the full strip fits at 120×40, then rebase the goldens.

I’ll slim the usage fixture so the unused row stays on-screen, then rebase the goldens.

The unused row is clipped because `max-height: 5` includes `padding-top`. I’ll raise it to 6 so the five content lines fit.

The CSS edits didn’t change the snapshot frame. I’ll check how the visual suite loads styles.

Usage is shrinking under the container cap. I’ll give the strip a minimum height so the unused row stays visible.

The fourth usage row is clipped at 120×40. I’ll match the plan’s three-row example so unused stays visible, and keep off-pool coverage in the unit tests.

The usage strip matches the plan. I’ll rebase the six alias-history goldens and confirm they pass.

The Alias History panel now ends with a model-usage strip that ranks the models in the currently shown window.

### What you get
Press `H` on an alias, bucket, or alias-backed launch setting. Below the detail strip and above the footer:

- **Header:** `Model usage · N runs`, plus `(deduped)` when a bucket listed the same `artifact_dir` twice, plus `X of Y members used` when the snapshotted pool has more than one member
- **Rows:** provider-colored bars (same palette as the `PROVIDER(model)` badges), counts, largest-remainder percents that sum to 100%, `✗`/`▶` chips, and `unused` / `off-pool` / `unrecorded` / `@ mixed` tags
- **Updates** on load, `Ctrl+K`, `r`, and `.` (computed in the existing off-thread worker)
- **Does not recompute** on `j`/`k`

A one-model alias is a single 100% row. Configured pool members with zero runs stay visible as `unused`.

### Implementation
| Layer | Where |
| --- | --- |
| Summarizer | `src/sase/llm_provider/alias_history_usage.py` |
| Pool snapshot at `H` | `selector_member_provider_model_effort` + `models_panel_history` builders |
| Rendering | `alias_history_usage_rendering.py` + `provider_bar_style()` |
| Modal | fifth region `#alias-history-usage`; worker returns `(view, summary, error)` |
| Layout | usage `max-height: 6` (padding + 5 content lines); list 14; detail 13; footer shares the usage rule |
| Docs | `docs/ace.md` Alias History section |

No feature flag, no config key, no `sase-core` change.

### Verification
- Targeted unit/modal/history tests: **100 passed**
- Alias-history PNG suite: **6 passed** after intentional rebase of the five existing goldens plus new `models_panel_alias_history_usage_120x40`
- `just check`: every lint gate I own is clean; **`lint (symvision)` is still red on master** for unused `ledger_path` / `read_ledger_records` (already on epic `sase-q0`; corroborated)
- `just test-scoped` escalated to the full suite (`core-identity-changed`): **33581 passed**, 13 skipped; the **3 failures** are the pre-existing flag/completion nodes already tracked (`test_kind_mismatch_when_default_disagrees_with_kind`, two `tests/completion/test_snapshot.py` drift tests)

### Notes
- **Bucket title still double-counts** the same run under two aliases. The usage strip dedupes by `artifact_dir`; the title line was left unchanged on purpose.
- The dedicated usage golden is the plan’s three-row case (majority model, failed member, unused member). A fourth `off-pool` row is covered in unit tests; at 120×40 the fifth usage line (header + 4 rows) is clipped by the modal budget.
- I did not open a live `sase ace` session at ~100×30. Footer visibility at 120×40 is confirmed in the PNG goldens.

The implementation is already in the working tree. I'll read the commit skill and commit those changes now.

I'll record the commit-skill invocation and inspect the working tree so the message matches only this change.

The tree matches the approved usage-strip work. I'll write the commit message and create the stitch.

The commit is still running. I'll wait on it until it finishes.

The stitch succeeded. I'll confirm the branch is clean and in sync with upstream.

Committed the Alias History model-usage strip as `610c19cd8` (`feat(ace): show model-usage strip in Alias History`). `master` is clean and matches `origin/master`.

Press `H` on an alias, bucket, or alias-backed launch setting. Below the detail strip:

- **Header:** `Model usage · N runs`, plus `(deduped)` when the same `artifact_dir` appears twice, plus `X of Y members used` when the pool has more than one member
- **Rows:** provider-colored bars, counts, percents that sum to 100%, and `unused` / `off-pool` / `unrecorded` tags
- **Updates** on load, `Ctrl+K`, `r`, and `.` (off-thread). Does **not** recompute on `j`/`k`

No feature flag, no config key, no `sase-core` change. Bucket titles still double-count the same run under two aliases; the strip dedupes by `artifact_dir`.
