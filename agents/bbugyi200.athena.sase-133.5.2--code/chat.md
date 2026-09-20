# Chat History - ace-run (sase-133.5.2--code)

- **TIMESTAMP:** 2026-09-20 08:22:11 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-133.5.2--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202609/gh_sase_org__sase-ace_run-sase_133_5_2__plan-260920_063337.md`
- **2. --code** — `~/.sase/chats/202609/gh_sase_org__sase-ace_run-sase_133_5_2__code-260920_063337.md`

## Prompt

%model:@medium
#gh:gh_sase-org__sase
@plan:202609/owner_presentation_facts.md

The above plan has been reviewed and approved. Implement it now.


## Response

Reading the catalog code and the Python enrichment I need to mirror.

Still reading the wire types I need for the new Rust module.

Now add the `use`, helper methods on the facts type, and fix the other literals.

Add a contract test, then run `just check` in sase-core.

sase-core passes `just check`. Now the Python adapters.

Fine — I'll compare the effective role (suffix-derived), which is what the status pass reads.

Use `agent_status_bucket` for both sides, pin UTC, resolve parents by name, and apply status overrides on the owner side.

Those two were load-induced timeouts (they pass alone). Re-running the full core check, then the Python check.

Core is green. Now the primary repo's `just check`.

Implementation is done; I'm submitting the final declaration now.

The gateway fleet catalog now carries the owner's per-record presentation facts, and the shared viewer renderer reproduces the owner's rows for the production fixture (asserted per identity, both projection paths).

Not everything is green:
- **sase-core:** `just check` passes. It failed twice first on timing-sensitive gateway tests (`routes::tests::fleet_*` timeouts, and a `sudo_runner` timeout test); the `routes` ones also pass on their own, and the third full run was clean.
- **Primary repo, `just check`:** it does not pass. It fails at the mypy step (`ace_tmux*.py`), before it reaches the test stage. I confirmed the mypy errors also occur without my changes.
- **Symvision:** it fails on private-import errors in `memory/selector_models.py` and `main/ace_tmux_support.py`; I didn't check whether master fails the same way.
- **`just test-scoped`:** it failed on four tests per run, and the two runs disagreed. The failures were `test_capacity_gate_to_admission.py` (2, fails on the stashed tree too), `test_fleet_contract_sase_core_rs.py` (schema-version pin, fixed), and the timing-sensitive `test_app_import_budget.py`, `test_contract_manifest.py` and `test_lazy_tier2_reconcile_apply.py` (the last two passed on a re-run). After the pin fix, the re-run of the fleet contract tests passed.

**What changed:**
- **New core module:** `fleet_owner_facts.rs` mirrors the owner's per-record enrichment. It produces the rich base status and the shell, plan, question, retry and lifecycle facts. It replaces `display_status_for_record()`.
- **Filesystem lookups:** the two owner-side lookups (persisted question response, plan tier from the plan file) sit behind an observer trait with a hermetic injected form.
- **Wire and revisions:** facts ship as a `presentation` object on the owner facts and the summary, with no paths. The contract is now v5, and row revisions fold in the resolved facts.
- **Viewer:** `_fleet_agents_rows.py` reads the facts, keeps the old fallbacks for legacy payloads, and derives the status bucket from the rich status. Gate members show their gate status. `question_answered` is accepted by the answered-question policies.
- **Fixture:** it now has the tale (`0n`), epic (`0k`), active, waiting, pending-review and answered-question families.
- **Oracle:** `test_owner_facts_oracle.py` checks each fact dimension per identity on both the current and compact paths, plus the `TALE DONE` / `EPIC CREATED` regressions, injection, and a legacy payload.

**Deviations from the plan:**
- **Fixture shape:** the plan says the persisted shape is a nested `family_shell`. It is flat `gate_*` / `monitor_*` keys that the scanner folds into `family_shell`, so I kept the flat keys and added the missing real fields.
- **Nested facts:** I nested the facts under `presentation` instead of adding flat keys to the summary. The viewer accepts either spelling.
- **Start times:** `start_time` is compared for roots only, because the catalog deliberately gives family members their root's start time (an existing gateway test asserts this).
- **Optional dimensions:** `run_start_time` is compared only where the owner recorded one. Proc ids are excluded from the shell-id comparison because the owner's are registry-backed.

I filed two follow-up notes on `sase-133.5.2`. One is that Rust reads artifact-directory timestamps as UTC rather than the configured timezone. The other is the baseline failures above. Both repos were submitted for commit with `bead_action: keep`.
