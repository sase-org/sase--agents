# Chat History - ace-run (sase-ha.5)

- **TIMESTAMP:** 2026-08-07 22:04:47 EDT
- **MODEL:** claude/opus
- **AGENT:** sase-ha.5

## Prompt

#gh:gh_sase-org__sase
%id(5, clan=sase-ha, bead=sase-ha.5)
%model:@medium_phase_worker
%auto
%w:sase-ha.2
%w(bead=sase-ha.2)
Can you complete the work for bead sase-ha.5? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close the bead with
`sase bead close sase-ha.5 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself: record discovered
follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-ha.5 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead.

My phase is `advisory`. Let me set up and explore the code.

Now let me implement. Starting with the hookspec and registry normalization:

Now the registry aggregation:

Now the accessor:

Now the Muse implementation:

Now the model picker rows:

Now render it in the Textual option label:

Now `%model` completion:

Now the model label:

Now the doctor check:

All three render sites work. Now let me verify the doctor check fires when a user configures the flagged model:

Now let me write the tests:

Now the doctor check tests:

Now fixing the stale pre-existing test expectation:

All green. Now the full check:

Now the label and completion sites:

That exact-dict assertion needs the new keys:

All targeted tests pass. Waiting on the full `just check` run:

`sase doctor -C llm.model_advisory -v` is silent for the shipped defaults, as the plan requires. Waiting on the full check:

Those are the killed/waiter tasks. Let me review the diff while the real run proceeds:

Waiting on `just check`. Meanwhile, a summary of what's implemented:

**The hook** (`src/sase/llm_provider/_hookspec.py`) — `llm_model_advisories`, provider-neutral: model id → `{severity, label, detail}`. Normalized in `_registry_metadata._model_advisories` with malformed entries dropped, not raised, so a third-party provider returning junk can't break registry collection. Exposed through the payload and `registry.model_advisory_map()` / `model_advisory_for()` alongside `model_short_aliases`.

**Muse** flags `muse-spark-1.2-contributor` as `warn` / "trains on your data".

**Three render sites**, all reading the registry:
- `model_picker_rows.py` — `⚠ trains on your data` suffix on the row, full sentence as the row's `description` (which also makes it searchable); `model_option_text` renders it in warning orange, deliberately not provider-colored.
- `xprompt/model_completion.py` — advisory in the completion detail, plus `advisory_label`/`advisory_severity` on the entry and the LSP payload (additive under schema v1).
- `llm_provider/model_label.py` — a `⚠` marker on the resolved label, so an active advisory model stays marked for the run's life.

**The guard** — `sase doctor -C llm.model_advisory` resolves every alias view plus the default provider's tier mappings and WARNs (never fails) on any route landing on a flagged model, naming the route and quoting the detail. Verified silent for shipped defaults.

`just check` is running in the background; I'll report when it lands.

I'll wait for the notification rather than polling further.

`just check` passed (exit 0).

No unpublished-close diagnostic. Now committing.

Working tree clean, master in sync with `origin/master`.

## Summary

Completed bead **sase-ha.5** (`advisory` phase of epic sase-ha).

**What was built:**
- **Hook** (`src/sase/llm_provider/_hookspec.py`) — `llm_model_advisories`, provider-neutral: model id → `{severity, label, detail}`. Normalized in `_registry_metadata`, where malformed entries are dropped rather than raised so a third-party provider can't break registry collection. Exposed via `registry.model_advisory_map()` / `model_advisory_for()`.
- **Muse** flags `muse-spark-1.2-contributor` as `warn` / "trains on your data".
- **Three render sites**, all reading the registry: model picker rows (warning suffix + full sentence as searchable description, warning-colored rather than provider-colored), `%model` completion (advisory in detail, plus `advisory_label`/`advisory_severity` added additively to the entry and LSP payload), and the resolved model label (marker persists for the run).
- **Guard** — `sase doctor -C llm.model_advisory` resolves every alias view plus the default provider's tier mappings and WARNs (never fails) on any route landing on a flagged model, naming the route and quoting the detail.

**Verified:** new tests in `tests/llm_provider/test_model_advisories.py` and `tests/doctor/test_checks_providers_advisory.py`; updated stale expectations in `tests/doctor/test_checks_providers.py` and `tests/test_xprompt_model_completion.py`; the doctor check is silent for shipped defaults; full `just check` green (all lint gates + scoped test lane, exit 0).

Bead closed with a verification note, and the commit landed and pushed. One caveat worth noting: the commit reported that prompt-archive and agent-hood publication were deferred because the agents sync lock was busy — both are queued to retry automatically, and the primary commit itself succeeded.
