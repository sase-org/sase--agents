# Chat History - ace-run (research.0v.cld)

- **TIMESTAMP:** 2026-08-21 19:43:42 UTC
- **MODEL:** grok/grok-4.6
- **AGENT:** research.0v.cld
- **PROMPT:** `~/.sase/multi_prompts/202608/gh_sase_org__sase-multiprompt-260821_193052.md`

## Prompt

%id(cld, clan=research.0v) %m:@research_b  #gh:gh_sase-org__sase I recently implemented pluggable sase finalizers (see the sase-rn and sase-rr epic beads for context). I would like to improve sase's finalizers by fixing any existing bugs and making some improvements to make them more powerful if possible. Can you do some research to help me find any existing bugs and (if possible) make sase's finalizers more powerful? End your analysis with a ranked list of recomended bug fixes / improvements. Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll start by loading the research, artifacts, beads, and finalizer skills, then pull the sase-rn and sase-rr epic context.

Next I’ll load artifact and beads memory, glossary terms, and the research repo, then pull the sase-rn and sase-rr epic beads.

The research sidecar is open. I’ll load glossary terms, the sase-rn and sase-rr beads, and existing research-report conventions next.

I'll inspect existing finalizer research, plans, report format, and related beads so this analysis doesn't duplicate what's already landed.

Existing finalizer research is already in the sidecar. I’ll read those reports, the epic plans, and the current implementation next.

I’ll audit the current finalizer implementation, plans, tests, and sase-rr notes for concrete bugs rather than restating the earlier design research.

sase-rr already closed several known gaps. I’ll inspect the live code, tests, CLI, and config to see what still fails and what’s left to strengthen.

I'll start by mapping the finalizer modules, CLI, schema, and the known issues you listed so we can verify what's still realDocs. still mention the deleted commit-finalizer path. I’ll read the live modules and CLI next to confirm what’s actually wired

.I'll inventory finalizer-related tests and scan for xfails, skips, and untested paths, starting with targeted searches under `tests/`.

## Coverage map

Pluggable-finalizer tests are concentrated in a small set of dedicated files; the older `tests/llm_provider/test_commit_finalizer_*.py` suite still covers pre-protocol commit mechanics (baseline, siblings, auto-SDD, bead publication, shared-clone races).

### Protocol / controller / declaration (well covered)

| Area | Primary tests | Evidence |
|---|---|---|
| Plan + `%final` parsing | `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_23/tests/test_finalizers_foundation.py`, `tests/test_directives_extract.py` | `%final:none` (`foundation.py:47`,

 `121`), unknown/empty fail before persist (`246`), `%final:lint` keeps default commit (`227`),

 required commit vs `%final:none

` (`260`), directive collect (`directives_extract.py:

175`) |
| Controller noops / empty plan | `tests/test_finalizers_protocol_harness.py` | outside agent (`166`), missing artifacts (`189`), handoff skip (`203`), `%final:none` empty success (`228`) |
| Builtin commit execute / refuse | `tests/test_finalizers_commit_reconciliation.py` | declared stitch (`112`), refusal without stitch (`174`) |
| Conflict / resume | protocol harness + live e2e | first-repo blocks later (`protocol_harness.py:307`), successful resume (`356`), exact-cwd sidecar match (`417`), stale checkpoint (`485`); live success path (`live_e2e.py:611`) |
| Stale submit | declaration + protocol + live | stale nonce/plan (`declaration_channel.py:234`), post-submit fingerprint change fail-closed after recovery spent (`protocol_harness.py:514`), one recovery then commit (`live_e2e.py:530`) |
| Later dirt reactivates commit | protocol + live | simulated (`protocol

_harness.py:547`), real git write of `late.py` (`live_e2e.py:

563`) |
| Declaration channel | `tests/test_finalizer_declaration_channel.py` | context obligations (`97`), accept + invalid attempt log (`129`), clean skip recovery (`166`), one recovery turn (`192`), handoff skip (`261`) |
| Wire facade | `tests/test_core_finalizer_facade.py` | plan/context/submit (`45`), aggregate refuse (`117`) |

### Executor / CLI / plugins (partial)

| Area | What exists | Gap |
|---|---|---|
| `sase final` parser | bare `final` → list (`extension_runtime.py:

69`); `context`/`submit` parse (`declaration_channel.py:84`) | No tests for `handle_final_command`, `show`, `doctor`, or actual CLI I/O |
| Command executor | argv-only (`

147`), run+

artifacts (`160`), timeout (`269`), env sanitization (`294`) | No max-attempts retry, cwd kinds, or `submission != none` beyond parse |
| External plugin execute | fake `operation_runner` describe/validate/execute/verify (`215`, `400`); live fixture plugin (`live_e2e.py:449`) | Worker isolation and reject-payload are not asserted in unit tests |
| Missing provider | fail before plan persist (`123`) | — |
| Plugin layer config | plugin config layer rejected (`foundation.py:133`) | — |
|

 Disabled plugin | `

provider

_disabled` (`

371`) | —

 |

### Live e

2e (`

sase-rr

.4` deliverable)

No bead id `sase-rr.4` appears in this workspace. The live suite is `tests/test_finalizers_live_e2e.py` (9 tests, no skip/xfail). Docstring at `1:6` states stitch is a hermetic real

-git runner, **not** full

 `CommitWorkflow`:

- clean completion (`355`)
- dirty commit excludes baseline + push (`390`)
- `%final:none` on dirty tree (`424`)
- command + fixture plugin order (`449`)
- refusal preserves

 dirty work (`502`)
- stale post-submit recovers once (`530`)
- later-finalizer dirt reactivates commit (`563`)
- first-repo conflict blocks second then resumes (`611`)
- plan/monitor/questions handoffs skip controller (`670`)

### Fakey retry pipeline

`tests/fakey/test_retry_pipeline_e2e.py` has **no remaining finalizer failures** (no xfail/skip). The only finalizer assertions are in the first test, which pops `meta["finalizers"]` so exact meta equality still works:

```60:68:tests/fakey/test_retry_pipeline_e2e.py
    finalizers = meta.pop("finalizers")
    ...
    assert finalizers["selected"] == ["commit"]
    assert finalizers["raw_operations"] == []
    assert isinstance(finalizers["plan_digest"], str) and finalizers["plan_digest"]
```

Retry/fallback/spawn/kill tests (`74`, `117`, `140`, `167`, `204`) never re-check `finalizers` or `finalizer_result.json`. The file’s own remaining hole is detached spawn (`1:8`), not finalizers.

---

## Requested paths: tested or not

| Path | Verdict

 |

 Evidence |
|---|---|---|
| External provider payload validation | **Happy path live; reject path stubbed** | Live submit fills `{"note": "live-audit"}` and later asserts `payload_note` (`live_e2e.py:271-272`, `495-498`). Unit test patches `validate_external_declaration_payload` itself (`declaration_channel.py:371-395`), so it never runs `run_provider_operation` / worker JSON

 validation. Fixture reject branch (`tests/fixtures/final

izer_plugin/example_finalizers

.py:20-27`) is unused

. |
| Later

-finalizer dirt

 re

activates commit | **Yes,

 both layers** | Protocol

 (`protocol_harness.py:547-615`, patches `execute_non_commit_finalizer`); live (`live_e2e.py:563-608`, real `late.py` + `cycles >= 2`). |
| Conflict resume | **Yes** | Fail-closed first-repo (`307-353`); success resume (`356-413`); live two-repo (`611-667`). Not the real `sase stitch create --resume` binary (`live_e2e.py:3-5`, `249-258`). |
| Stale submit | **Yes, two budgets** | Nonce/plan digest (`declaration_channel.py:234-258`); recovery-spent fail-closed (`protocol_harness.py:514-544`); one live recovery (`live_e2e.py:530-560`). |
| `%final:none` | **Yes** | Plan (`foundation.py:47`, `121`), controller (`protocol_harness.py:228`), live dirty skip (`live_e2e.py:424`). |
| Required instances | **

Only required `commit` vs `%final:none`** | `foundation.py:260-297`. No required non-commit instance, no `plugins.required` cross-check via `_required_plugin_diagnostics` (`src/sase/finalizers/providers.py:354`). |
| Plugin isolation | **Partial** | Plugin *config* cannot come from plugin layers (`foundation.py:133`). Builtin command env is sanitized (`extension_runtime.py:294-322`). Disabled plugin fails (`371`). Live plugin allowlists `PYTHONPATH` (`live_e2

e.py:153`) so the fixture loads; **no test that plugin subprocesses drop secrets

**. `

worker_entry.py` has zero tests

. |

---

## Remaining holes

1. **`sase final` CLI dispatch** — `src/sase/main/final_handler.py` (`list`/`show`/`doctor`/`context`/`submit`) is untested. Parser only. Pretty/JSON rendering, unknown instance, doctor non-zero exit, stdin submit, declaration error → exit 1: none.
2. **`%final:!commit` never resolved** — extract test keeps `["lint", "commit", "!commit", "none"]` (`directives_extract.py:175-181`). No plan test that `!commit` actually removes commit (or is blocked when required).
3. **External validate is not a real provider call in unit tests** — stubbed at `declaration_channel.py:371`. Malformed JSON / unknown fields / schema mismatch in `_validate_provider_result` (`executor.py:591-629`) are untested. Test named for malformed output does not assert it:

```325:368:tests/test_finalizers_extension_runtime.py
def test_plugin_timeout_and_malformed_output_fail_closed(
    ...
    if operation == "execute":
        raise FinalizerExecutionError("provider operation 'execute' timed out")
    ...
    assert "timed out" in result.diagnostics[0].message
```

4. **Plugin worker isolation untested** — no `run_provider_operation` / `worker_entry` / `sdk.dispatch_provider_request

` tests. Size

-

cap, timeout of a real subprocess, truncated stdout, non

-zero exit: only simulated via `operation_runner`.
5. **Controller limits** — `controller_no_progress` (`protocol_harness.py:643`); `controller

_cycle_limit` (`controller.py:247`) never

 tested. Command `max_attempts` loop (`executor.py:143-162`) never retried.
6. **`commit_repair.py` / real stitch argv** — all stitch tests monkeypatch `run_

stitch_create`/`run_stitch_resume`. Live e2e documents this as intentional (`live_e2e.py:3-5`).
7. **Fakey retry + finalizers** — only the first fakey test checks plan projection; retry/spawn do not assert plan persistence or controller skip on handoff (`test_retry_pipeline_e2e.py:167`).
8. **CLI inspection of unconfigured plugins** is inventory-only (`extension_runtime.py:80`); `diagnose_finalizer_providers` is patched to `()` in several tests (`extension_runtime.py:111`, `declaration_channel.py:354`, `live_e2e.py:346`).

---

## “Bugs” / incomplete tests (no xfails)

There

 are **no** `xfail`/`skip`/`TODO`/`

FIXME` in the dedicated

 finalizer test files. What documents incompleteness:

| File | What it shows |
|---|---|
| `tests/test_finalizers

_live_e2e.py:1-6` | Live suite is not full stitch/CommitWorkflow e2e |
| `tests/test_finalizers_protocol_harness.py:538-541` | Loose `match

="stale\|declaration\|changed"` across

 two exception types — layer ownership of stale submit is not pinned |
| `tests/test_finalizers_extension_runtime.py:325` | Name claims malformed-

output coverage that

 is not asserted |
| `tests/test_finalizer_declaration_

channel.py:371-395` |

 External validate

 is a mock, not the worker |
| `tests/fixtures/finalizer_plugin/example_finalizers.py:20-27` | `reject` / `payload_rejected` path never driven |
| `tests/fakey/test_retry_pipeline_e2e.py:1-8` | Detached spawn still out of sandbox (unrelated to finalizers) |

Unrelated name collision: `tests/ace/tui/test_agent_unread_finalizer.py` is TUI unread-state, not this protocol.

**Bottom line:** controller, `%final:none`, required-commit, conflict resume, stale-submit recovery, and later-dirt reactivation are covered (live + harness). The remaining product holes are real CLI handlers, `!` selectors

, real plugin payload rejection

/isolation, stitch-repair integration, and controller cycle limit.

## Already fixed (verified)

These known items are **not** still true in this tree.

**Non-commit payloads skip provider `validate`** — fixed. Submit now calls `validate_external_declaration_

payload` for every non-builtin provider, and there is a regression test.

```715:731:src/sase/finalizers/declaration.py
        if entry.provider_ref == "builtin@commit":
            _validate_commit_payload(context, payload)
        elif entry.provider_ref != "builtin@command":
            from sase.finalizers.executor import (
                FinalizerExecutionError,
                validate_external_declaration_payload,
            )
            try:
                validate_external_declaration_payload(
                    instance_id, entry.provider_ref, context, payload
                )
```

**`_provider_request` omits payload/obligations** — fixed. Execution now loads accepted payloads and host obligations; `test_external_provider_request_includes_accepted_payload_and_obligations` covers it.

```525:530:src/sase/finalizers/executor.py
    payloads = _load_accepted_payloads(context.artifacts_dir)
    if instance.instance_id in payloads:
        request["payload"] = payloads[instance.instance_id]
    obligations = _load_host_obligations(context.artifacts_dir)
    if obligations:
        request["obligations"] = obligations
```

**Fakey e2e missing `SASE_AGENT_NAME`** — fixed in the current harnesses. Live/protocol/

declaration tests all set `SASE_AGENT_NAME`.

 There is no remaining fakey-specific finalizer suite.

**Private imports in `declaration.py`** — fixed. No `from … import _…` leftovers; format lives in `declaration_format.py`; commit uses

 public declaration helpers.

**`pluggable_finalizers` flag remnants in product code** — fixed. The flag is unregistered; `tests/test_finalizers_retirement.py` asserts it is absent from `src/sase/**/*.py|yml|json`. Mentions remain only in beads/plans/research history.

---

## Findings (highest severity first)

### 1. `max_attempts` is a no-op for `builtin@commit` and plugin providers
**Severity:** bug (config/docs contract broken)

Default config and docs say commit gets two executor attempts:

```1194:1198:src/sase/default_config.yml
    commit:
      use: builtin@commit
      after: []
      max_attempts: 2
      refusal: fail
```

```96:98:docs/commit_workflows.md
The finalizer uses the shared instruction helpers in `sase.commit_instructions`, so the
bead

 and method wording stays consistent between main-workspace and linked-repository
commit guidance. `finalizers.instances.commit.max_attempts` controls how many commit
executor attempts may run before SASE

 fails the invocation
```

`commit.py` never reads `instance.max_attempts`. Plugin execution loops operations, not attempts. Only `builtin@command` uses the field (`executor.py:143-144`). Schema default is `1` while shipped commit config is `2`, which hides the mismatch.

**Why it matters:** Operators think retries are configured. Conflict repair and controller cycles (`MAX_CONTROLLER_CYCLES = 8`) are a different budget. A `max_attempts: 1` commit instance still re-enters across cycles.

**Fix:** Honor `instance.policy.max_attempts` in `execute_commit_finalizer` and `execute_plugin_finalizer`, or stop advertising the field for those providers. Align schema default with shipped commit config.

---

### 2. Plugin workers get `run_id`/`agent_id` of `null` at execute time
**Severity:** bug

Controller builds execution context with only artifacts + plan digest:

```84:87:src/sase/finalizers/controller.py
    context = FinalizerExecutionContext(
        artifacts_dir=artifacts_dir,
        plan_digest=plan_digest,
    )
```

`_provider_request` then sends those null

s:



```510:517:src/sase/finalizers/executor.py
    request: dict[str, Any] = {
        ...
        "run_id": context.run_id,
        "agent_id": context.agent_id,
```

Submit-time `validate_external_declaration_payload` *does* populate them from the context wire (`executor.py:283-288`). Execute/verify do not.

**Why it matters:** Providers that bind evidence or side effects to run/agent identity see a different request at validate vs execute.

**Fix:** Copy `SASE_AGENT_TIMESTAMP` / resolved agent name (or the published context) into `FinalizerExecutionContext` in `run_finalizers`.

---

### 3. Provider request field `selected` is config defaults, not the sealed plan
**Severity:** bug

```519:523:src/sase/finalizers/executor.py
        "selected": [
            item.instance_id
            for item in config.instances.values()
            if item.instance_id in config.defaults
        ],
```

`%final:audit` / `%final

:none` / required-only plans still advertise defaults. Tests always use matching defaults, so this is untested.

**Why it matters:** A plugin that coordinates with siblings (e.g. “commit is selected”) will make the wrong decision.

**Fix:** Pass `plan.entries` instance IDs from the persisted plan (already on disk as `finalizer_plan.json`).

---

### 4. Plugin `execute` status `skipped` fails the whole turn
**Severity:** bug

Wire allows `skipped` (`executor.py:76`, `249-252`), but the controller treats any non-`success` as fatal:

```222:229:src/sase/finalizers/controller.py
                if result.status != "success":
                    _write_aggregate_result(
                        artifacts_dir,
                        list(results_by_id.values()),
                        "failed",
                        cycles=cycles,
                    )
                    raise RuntimeError(_result_failure_message(result))
```

No test covers `skipped`.

**Why it matters:** A provider that correctly reports “nothing to do” aborts completion and looks like a hard failure.

**Fix:** Treat `skipped` as terminal-success for that instance (and do not put it in `ran_non_commit` if you want reactivation — see #8).

---

### 5. Worker crashes drop the real diagnostic
**Severity:** bug

```35:50:src/s

ase/finalizers/worker_entry

.py
        payload = {
            "schema_version": 1,
            "operation": args.operation,
            "provider_ref": args.provider_ref,
            "status": "failed",
            "diagnostics": [
                {
                    "code": "worker_exception",
                    "severity": "error",
                    "message": f"{type(exc).__name__}: {exc}",
                }
            ],
        }
```

Missing `instance_id`. `_validate_provider_result` then rejects:

- describe/validate/verify: `status 'failed'` is not in `{ok, success}`
- execute: `instance_id` is not the

 configured

 id

The worker’s `diagnostics` never surface. Same hole in `sdk.sdk_worker_main`.

**Why it matters:** Host errors become “returned instance None” / “returned status 'failed'”. Exception text can still leak secrets into stdout artifacts (`{exc}`), but the controller message is useless.

**Fix:** Echo `instance_id` from the request; for non-execute, map worker `failed` into a host `FinalizerExecutionError` using `diagnostics[0].message` instead of schema-mismatching first.

---

### 6. One-shot declaration recovery fights commit reactivation
**Severity:** bug / design hole

Docs and controller comments say later mutators can reactivate commit. Recovery is a single file flag:

```412:415:src/sase/finalizers/controller.py
def _declaration_recovery_spent(artifacts_dir: str | None) -> bool:
    if not artifacts_dir:
        return False
    return (Path(artifacts_dir) / FINAL_DECLARATION_RECOVERY_PROMPT_FILENAME).is_file()
```

Reactivation of a dirty tree after a successful first recovery raises `stale_declaration` and stops. Covered as expected failure in `test_stale_post_submit_edit` when the recovery file is pre-seeded (`tests/test_finalizers_protocol_harness.py:533-544`). Happy-path reactivation tests only work because recovery was **not** already spent.

**Why it matters:** Agent forgets `/sase_final` → recovery succeeds → `builtin@command`/plugin writes files → commit cannot get a new declaration. The “fixed point” controller cannot finish.

**Fix:** Separate budgets: declaration-recovery vs post-execute dirty reactivation; or allow one extra submit per controller cycle without consuming the missing-declaration budget.

---

### 7. `FINALIZER_SELECTED` increments on every context republish
**Severity:** bug (telemetry)

```132:135:src/sase/finalizers/declaration.py
    context_digest = validate_finalizer_context(plan,

 context)
    context = replace(context, context_digest=context_digest

)
    payload = _context_payload(plan, context)


    _record_selected_metrics(payload)
```

`publish_final_context` runs

 on every `sase final context`, every controller cycle, and every `_ensure_current_declaration`.

**Why it matters:** Dashboards read “how often is commit selected” as “how often did we republish context.”

**Fix:** Count once when the plan is sealed (`resolve_and_persist_finalizer_plan`), or only when digest/selection changes.

---

### 8. Non-commit instances still run once (no reactivation)
**Severity:** limitation (still present)

```444:445:src/sase/finalizers/controller.py
        if instance_id not in ran_non_commit:
            pending.append(instance_id)
```

**Why it matters:** Lint/format/audit after a reactivated commit never re-verifies. Combined with #6, late dirt is a dead end.

**Fix:** Pending rule should be trigger-based (dirty digest, payload requirement, verify failure), not a one-shot set.

 Cap with `max_attempts` / controller cycles.

---

### 9. Hard 30s plugin timeout vs unbounded `builtin@command` timeout
**Severity:** limitation (still present; asymmetric)

```46:

46:src/sase/finalizers/executor.py
PROVIDER_OPERATION_TIMEOUT_SECONDS = 30.0
```

Command timeout accepts `ms|s|m|h` with **no max** (`providers.py:478-520`). Schema has no plugin timeout field. Docs say trusted config owns timeouts, but plugins cannot set one.

**Why it matters:** RealI have enough validate evidence from/execute work the current tree. (network, full Next I’ll write the-repo research report with lint) dies confirmed at 30s bugs, leftover. gaps A trusted, and a ranked fix list. command can hang the controller for hours.

**Fix:** Per-instance timeout in config for plugins, with a documented cap (e.g. 15m). Apply the same cap to command.

---

### 10. Provider ref matching is not PEP 503–normalized
**Severity:** bug

Inventory/`worker_entry` compare `dist.metadata['Name'] == package` exactly. `normalize_distribution_name` is used only for `plugins.required`. `plugin_qualified_id_matches` is also exact (`package == plugin`).

**Why it matters:** `use: example-finalizers@audit` vs distribution `Example_Finalizers` fails closed at launch or, worse, inventory shows a provider the worker cannot load.

**Fix:** Compare `normalize_distribution_name` on both sides in `worker_entry._find_entry_point` and provider lookup.

---

### 11. “Isolated” workers are env-scrubbed host interpreters
**Severity:** isolation hole

Sanitized env still includes `HOME`, `PATH`, `USER`, `TMPDIR` (`executor.py:48-59, 705-710`). cwd is the project dir. Worker is `sys.executable -m sase.finalizers.worker_entry`, so the plugin imports the full SASE install and can read `~/.ssh`, other repos, `/proc/<ppid>/environ`. `validate` runs in that process **during `sase final submit`**, before the model turn has ended — writes are not prevented.

**Why it matters:** A malicious/buggy `sase_finalizers` entry point is equivalent to arbitrary code as the user, including during declaration. The protocol’s “isolated worker” language overclaims.

**Fix:** Document honestly; optionally drop `HOME`, set `HOME` to a scratch dir, `PYTHONSAFEPATH`, and treat validate as read-only (fs snapshot or landlock if you ever need real isolation).

---

### 12. `sase final list` / `show` / `doctor` ignore the sealed turn plan
**Severity:** limitation / CLI gap

`build_finalizer_inventory` always resolves `config.to_plan_input([])` (defaults only). It never reads `SASE_ARTIFACTS_DIR/finalizer_plan.json`. Pretty `show` also omits `max_attempts` and `refusal`.

**Why it matters:** During a `%final:none` or `%final:lint` turn, `sase final list` still shows default `commit` as selected, while `sase final context` shows the real plan. Agents/operators debug the wrong set. Skill `/sase_final` never mentions doctor/list.

**Fix:** If `SASE_ARTIFACTS_DIR` is set, overlay the persisted plan’s `selected`. Print policy fields in pretty show. Teach the skill `sase final doctor` for repair.

---

### 13. Secret redaction misses common key names
**Severity:** bug (leak)

```595:600:src/sase/finalizers/providers.py
def _looks_sensitive(key: str) -> bool:
    lowered = key.casefold()
    return any(
        fragment in lowered
        for fragment in ("secret", "token", "password", "passwd", "credential")
    )
```

`api_key`, `key`, `auth`, `bearer` print in `sase final show` JSON. Worker exception messages also interpolate `{exc}`.

**Fix:** Expand the fragment list; never put raw `{exc}` in artifacts without redaction.

---

### 14. Handoff commands skip all finalizers, including commit
**Severity:** limitation (still present, documented)

```315:320:src/sase/finalizers/controller.py
def _should_skip_finalizers(artifacts_dir: str | None) -> bool:
    if not artifacts_dir:
        return True
    if not os.environ.get("SASE_AGENT_TIMESTAMP"):
        return True
    return has_pending_handoff(artifacts_dir)
```

Skill and prompt block say this is intentional. Dirty repos after `#plan` / monitor / pipe / questions are left uncommitted.

**Why it matters:** Easy to lose work or leave dirty workspaces. Fine if product intent; surprising if not.

**Fix:** If intentional, keep. If not, run non-mutating finalizers, or snapshot dirty state onto the handoff marker.

---

### 15. No role / xprompt-profile binding
**Severity:** missing feature (still present)

Selection is global `finalizers.defaults` + prompt `%final` only. Nothing in `src/sase/finalizers/` keys off family role, xprompt profile, or `#commit`/`#pr`. Memory `sase/memory/xprompts.md` still describes the old `/sase_git_commit` → `sase commit` path and never mentions `%final` or `/sase_final`. User-facing `docs/xprompt.md` does document `%final`.

**Why it matters:** Land vs explore vs review agents cannot have different default finalizers without every prompt repeating `%final`. Memory instructions agents actually load are stale.

**Fix:** Optional `finalizers.profiles.<role>` or xprompt front-matter `final:`; update xprompt memory (needs explicit user permission + `sase memory init`).

---

### 16. `builtin@command` has no model payload; cwd is only `"primary"`
**Severity:** limitation (still present)

```438:449:src/sase/finalizers/declaration.py
        if entry.provider_ref == "builtin@command":
            requirements.append(
                FinalizerPayloadRequirementWire(
                    instance_id=entry.instance_id,
                    trigger="always",
                    submission_required=False,
```

```720:723:src/sase/finalizers/executor.py
def _resolve_cwd(command_config: CommandFinalizerConfig) -> str:
    if command_config.cwd == "primary":
        return resolve_finalizer_project_dir()
    raise FinalizerExecutionError(f"unsupported cwd policy {command_config.cwd!r}")
```

`resolve_finalizer_project_dir()` is workspace/project dir, not a linked-repo cwd. Docs mention cwd policy as if it were pluggable.

**Fix:** `cwd: repo:<id>` / `linked:<name>` once obligation IDs exist; `submission: payload` when a command needs a model argument.

---

### 17. External plugins always `submission_required: true` with empty `{}` templates
**Severity:** limitation

```454:466:src/sase/finalizers/declaration.py
        requirements.append(
            FinalizerPayloadRequirementWire(
                instance_id=entry.instance_id,
                trigger="provider_requested",
                submission_required=True,
```

Providers cannot opt out of a payload the way command can (`submission: none` only). Agents must submit `{}` even for fire-and-forget plugins.

**Fix:** Honor provider `describe` (`submission_required` / schema) when building context, instead of hard-coding `provider_requested`.

---

### 18. `declaration.py` is still at the size cliff
**Severity:** limitation (partially addressed)

The file is ~999 lines after extracting `declaration_format.py`. Payload validation, I/O, recovery, and metrics still share one module. Bead notes already flagged a toobig violation.

**Fix:** Split `validate_provider_payloads` / commit payload rules and recovery into sibling modules.

---

### 19. Schema / CLI / skill mismatches
**Severity:** limitation

| Surface | Reality |
|---|---|
| Schema `refusal` enum is only `"fail"` | No skip/warn policy exists |
| Schema `max_attempts` default `1` | Shipped commit instance is `2` |
| Skill never mentions `list`/`show`/`doctor` | Those commands exist |
| Skill says handoffs skip `/sase_final` | Matches controller, not commit-of-dirty-work |
| `sase final submit` validates against **last published** context, does not republish | Stale submit is accepted until controller republishes and recovers |

Context vs submit use **different locks** (`final_context.json.lock` vs `final_submission.json.lock`), so a concurrent republish can accept a digest that is already obsolete. Single-threaded host makes this rare; recovery invoke + tools in parallel would hit it.

---

### 20. Tests that do not cover claimed behavior
**Severity:** test gap

- No test that `%final` selection appears in plugin `request["selected"]`.
- No test for plugin `max_attempts`.
- No test for execute `skipped`.
- No test that controller fills `run_id`/`agent_id`.
- Reactivation tests never start from a spent recovery + later mutator.
- `test_plugin_timeout_and_malformed_output_fail_closed` injects `FinalizerExecutionError` in the runner; it does not run `worker_entry` JSON and so misses finding #5.

---

## Ranked summary

| Rank | Finding | Kind |
|---|---|---|
| 1 | `max_attempts` ignored for commit + plugins | bug |
| 2 | Plugin execute `run_id`/`agent_id` always null | bug |
| 3 | `selected` in provider request is defaults, not plan | bug |
| 4 | Plugin `skipped` fails the turn | bug |
| 5 | Worker exceptions lose `instance_id` / real message | bug |
| 6 | One-shot recovery vs commit reactivation | bug |
| 7 | `FINALIZER_SELECTED` over-counts | bug |
| 8 | Non-commit run-once | limitation |
| 9 | 30s plugin cap / unbounded command timeout | limitation |
| 10 | Unnormalized dist names | bug |
| 11 | Worker isolation is cosmetic | isolation |
| 12 | CLI list/show ignore turn plan | missing CLI |
| 13 | Weak secret redaction | leak |
| 14 | Handoffs skip finalizers | limitation |
| 15 | No role/xprompt binding; memory omits `%final` | missing feature |
| 16 | Command: no payload, cwd `primary` only | limitation |
| 17 | Plugins always require a payload | limitation |
| 18 | `declaration.py` still ~1000 lines | limitation |
| 19 | Schema/skill/docs drift | mismatch |
| 20 | Tests miss the above | test gap |

I’ll register typed artifact links for the report, then submit the turn’s finalizer declaration.

The research is in `sase/repos/research/202608/finalizer_bugs_and_capability_upgrades.md` (`research:202608/finalizer_bugs_and_capability_upgrades.md`). It is linked to the `sase-rn` / `sase-rr` / `sase-ro` beads, both epic plans, and the earlier finalizer research.

**Headline:** the protocol is real and the beta split is gone. Built-in `commit` is the mature path. What is not yet powerful is everything around it: plugin requests still lie about selection and run identity, `describe` cannot influence context, and every external instance forces a required empty declaration.

Two findings from this morning’s companion research are already fixed at HEAD `28009002d`: provider `validate` for non-commit payloads, and forwarding accepted payloads plus host obligations into worker requests. Fakey `SASE_AGENT_NAME` is also fixed.

### Ranked recommended bug fixes / improvements

| Rank | Kind | Recommendation |
| --- | --- | --- |
| **1** | Bug | Pass the sealed plan’s `selected` list plus `run_id` / `agent_id` / digests into every worker request. `%final` currently still advertises config defaults, and those IDs are `None`. |
| **2** | Bug | Run `describe` at context-publish time and honor `RequiresSubmission` / payload schema. Stop hardcoding `submission_required=True` for every plugin. |
| **3** | Bug | Honor `max_attempts` for plugins; treat execute `skipped` as not-pending; align JSON schema with the Rust 1–16 cap. |
| **4** | Bug | Replace “non-commit runs once” with explicit triggers so checks can re-run after a mutator. |
| **5** | Bug | Rewrite `docs/commit_workflows.md` (it still teaches `/sase_git_commit` follow-up passes) and retarget docs that cite deleted `commit_finalizer.py`. |
| **6** | Bug | Teach `/sase_final` non-commit payloads; make `obligation_id` / `repo_id` consistent; skip the skill injection when nothing can require a declaration. |
| **7** | Bug | Make `sase final list` distinguish config defaults from *this turn’s* selection. |
| **8** | Bug | Cover payload rejection, `%final:!commit`, real worker isolation, CLI handlers, and plugin retries in tests. |
| **9** | Improvement | Ship `check` as `builtin@command` wrapping `just check`, selected from code/PR xprompts via `%final:check`, not as a global default. |
| **10** | Improvement | Same pattern for `research-doc` and a narrow `sase-hygiene` instance. |
| **11** | Improvement | First-class role/xprompt default lists in trusted config, applied before user `%final`. |
| **12** | Improvement | Configurable plugin timeouts and closed cwd policies beyond `primary`. |
| **13** | Improvement | Typed delivery/review-manifest provider once describe-at-context exists. |
| **14** | Improvement | Land/phase mechanical closeout (epic symbols, follow-up disposition, plan `status: done`). |
| **15** | Improvement | Post-commit bead/Patch/artifact reconciliation and cross-repo compatibility checks. |
| **16** | Later | `failure`/`always` lifecycle, async jobs, preview deploy, cryptographic provenance — wrong seam today. |

If only one follow-up epic is approved: truthful plugin contract (1–4, 8), then docs/skill (5–7), then shipped `check` plus xprompt `%final` (9–11). Those are not `sase-ro` retirement blockers.
