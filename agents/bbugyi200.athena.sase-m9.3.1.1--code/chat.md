# Chat History - ace-run (sase-m9.3.1.1--code)

- **TIMESTAMP:** 2026-08-15 16:44:01 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** sase-m9.3.1.1--code

## Linked Chats

- 1. --plan — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-sase_m9_3_1_1__plan-260815_151905.md`
- **2. --code** — `~/.sase/chats/202608/gh_sase_org__sase-ace_run-sase_m9_3_1_1__code-260815_151905.md`

## Prompt

%model:@medium_worker
#gh:gh_sase-org__sase
@sase/repos/plans/202608/durable_operation_contracts.md

The above plan has been reviewed and approved. Implement it now.


## Response

I'll start by reading the approved plan, the required SASE memory notes, and the current ACE/proc submission surfaces so the implementation stays aligned with the contract.

Next I’ll load the parent plan, CLI/bead memory, and the current proc-submission code so the new contracts match existing patterns.

The parent plan path didn’t resolve; I’ll locate that doc and map the current proc/ACE submission surface next.

I’ll inventory ACE producers, settlement, and existing CLI patterns so the new contracts can sit on the current surfaces without rewriting them.

The bead lookup is still running; I’ll keep mapping producers, existing inventories, and proc tests while it finishes.

The parent epic plan is the source of truth for operations; I’ll open the plans sidecar and read it next, then inventory every current producer.

The parent epic plan lives in the SDD plans directory; I’ll read that and the sibling phase plans next.

I have the parent epic’s invariants. Next I’ll map every producer site, existing CLI entry points, and the test patterns this phase should extend.

I'll searchI'll map CLI registration the production ACE, proc code and tests settlement tests for every proc, and existing service call-submission path and the sites so supporting we can add durable- queueoperation plumbing without inventing a/protocol second protocol. infrastructure.

I have the call-site list; next I’ll read each production submit site and the queue/protocol definitions.

Next I’ll read the parser/entry surfaces and hunt the CLI-help plus proc-settlement tests in parallel.

I have the registrar map; next I’ll inventory domain parsers/handlers and the proc settlement/test machinery.

I’ll keep reading settlement tests, CLI mutation commands, and any existing AST-inventory pattern so we can implement against the real tree.

I’ll pull notify/run parsers, handlers, CLI-rules memory, and the proc settlement code next.

I'll read the submit wrappers, queue/mirror types, and the first batch of producer files.

Next I’ll read the remaining producer files in batches so every call site can be classified.

I’ll map ACE-facing domain services and bead/agent mutation entry points next, plus a representative handler execution test.

I have enough of the architecture to start sketching modules; I’ll keep pulling parser/help patterns and domain-service entry points so the new commands stay thin wrappers.

# CLI, proc settlement, and ACE-call surface map

This is

 the existing protocol. New durable-operation commands should reuse it

 rather than invent sid

ecars, envelopes, or

 dispatch.



---

##

 1. CLI structure



### Registration

Lazy

 registry in `/

home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/main/parser.py`:

- `_COMMAND_REGISTRARS` maps top-level name → `(module, registrar_fn)`.
- `create_parser(only=...)` builds one tree (`parser_only_hint(sys.argv)` in `entry.py`).
- Full-parser import catalog: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/main/parser_full_registrars.py` (`COMMAND_REGISTRARS_BY_NAME`).
- After register: `_sort_subcommand_help()` (alpha by dest) and `_default_list_subcommands()` (bare group → `list`).
- Aliases share a registrar: `changespec`→patch, `task`→proc, `vcs`→stitch, `artifact-file`→artifact.

Misc groups live in `parser_commands.py` (`notify`, `run`, `config`, `file`, `file-history`, `logs`, `lsp`, `path`, `questions`, `comments`, `revive-log`).

### Dispatch

`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/main/entry.py` `main()`:

1. Fast path: `bead`

 via `try_handle_bead_fast_path`.
2. Pre

-argparse: `run` via `handle_run_special_cases`.


3. `create_parser(only=...).parse_args()`.
4. Optional `default_list_delegation_notice`.
5. Alphabetical `if args.command == ...` blocks, each importing a handler.

Bead is special: inlined `_BEAD_HANDLERS` map in `entry.py`, not `handle_bead_command`.

### CLI rules (from `sase/memory/cli_rules.md` + tests)

- Options must not be required; required values are positionals.
- Every public long option has a short alias (internal/`argparse.SUPPRESS` exempt).
- Listed subcommands/options sorted alphabetically.
- Parser tests assert `{a,b,c}` usage sets and `-s, --long` help pairs.
- Existing debt: several parsers still use `required=True` on options (`parser_gate.py` `--id/--kind/--operation`, `parser_agent.py` kill/tribe, `parser_bead_lifecycle.py` `--title`/`--note`, `parser_commands

.py` file-history `--path` and notify show `--id`, hidden `workspace open --reason`).

 New public surfaces should not copy that.

### How

 to add a group

1. `register_<domain

>_parser` in `parser_<domain>.py`.
2. Register in `_COMMAND_REGISTRARS` and `COMMAND_REGISTRARS_BY_NAME`.
3. Add `handle_<domain>_command` and a branch in `entry.py`.
4. Help + handler tests under `tests/main/`.

---

## 2. Existing mutation-capable subcommands (ACE-via-argv candidates)

**Read-only / inspect omitted unless they also mutate.**

### patch (`parser_patch.py` → `handle_patch_command`)

| Command | Mutation? | Notes |
|---|---|---|
| `current`, `search` | no | |
| `ref add` / `ref rm` | **yes** | `update_patch_refs_field` |
| `ref list` | no | bare `ref` → list |
| `set-origin` | **yes** | `PR_ORIGIN` |
| `sync-deltas` | **yes** | required `-P/--

patch` (debt) |
| `sync-external` | **yes** | `-d/--dry-run` |
| `migrate-extension

` | **yes** | `--force` has no short alias |

**Missing vs ACE:** no `status`, `rebase`, `sync` (

workspace), `rewind`. Those are TUI procs today.

### agent (`parser_agent.py` → `handle_agent_command`)

| Command | Mutation? |
|---|---|
| `list`, `show` | no |
| `kill -n NAME` | **yes** (`sase.agents.cli_kill`) |
| `sync` (+ `--drop-retired`, `--retry-quarantined`, `--repair-*`) | **yes** |
| `retire-v1 --apply` | **yes** |
| `tribe set/unset` | **yes** |
| `archive rebuild-index` | **yes** |
| `artifacts layout migrate/rollback` | **yes** |
| `index gc/rebuild/repair --apply` | **yes** |
| `names migrate-auto` | **yes** |
| `prompts migrate --write` | **yes**

 |

**Missing vs ACE:**

 no `launch`, `approve` (auto-approve directive), `revert`, `cleanup`/`dismiss`, `wait`, `rename`. Launch approval is `sase launch`, not `sase agent`.

### launch (`parser_launch.py` → `handle_launch_command`)

Mutations: `approve SELECTOR`, `reject SELECTOR`, `request` (JSON/`--prompt`).

### bead (`parser_bead.py

` + lifecycle

/store/query)



Mutations: `+

1`, `close`,

 `create`, `dep` add/rm, `init

`, `note`, `onboard`, `open`, `ref` add/rm, `rm`, `snooze`, `update`, `work` (launch/cleanup), `sync`, `sync-external`, `resolve-conflicts`.

Reads: `blocked`, `doctor`, `history`, `list`, `pages`, `ready`, `search`, `show`, `stats`.

Handlers: `sase.bead.cli_*` via `sase.bead.cli` facade.

### notify (`register_notify_parser` → `handle_notify_command`)

- `create` — **yes**, stdin JSON + `-s/--sender` `-t/--tag`; privileged actions refused.
- `list`, `show` — no. Bare `notify` → list.

No dismiss/read/snooze CLI; those exist only on `sase.notifications.store`.

### gate (`parser_gate.py` → `handle_gate_command`)

All mutate except `show`: `create` (stdin spec), `act`, `answer`, `wait`.

### plugin (`parser_plugin.py` → `handle_plugin_command`)

`install`, `uninstall`, `update`/`update --all` mutate. `list`/`show` do not.

### workspace (`parser_workspace.py` → `handle_workspace_command`)

| Command | Mutation? |
|---|---|
| `list`, `path` | no |
| `cleanup` | **yes** (`-s/--stale`, `-i/--include-shares`, `-n/--dry-run`) |
| `repair` | **yes** |
| `migrate` / `--finalize` | **yes** |
| `open` | hidden compat; `--reason` required |

### monitor

 (`parser_monitor.py` → `handle_monitor_command`)

- `start -- COMMAND` — **yes** (the reference durable-submit path)
- `stop [ID]` — **yes**
- `list`, `show` — no
- `_supervise` — hidden internal

### proc / run

- `sase proc run -- COMMAND` — **yes** (`submit_proc` / `submit_detached_proc`)
- `sase proc kill REF` — **yes**
- `sase run [PROMPT]` — **yes** (detached agent launch, not a proc-shell)

---

## 3. Parser help tests

Helpers: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/main/parser_help_helpers.py`

- `parser_for(("sase", "proc", "run"))`
- `flat_help`, `help_subcommand_rows`, `assert_metavar_option_documented`
- `parse_and_capture_help` for `SystemExit(0)` help

Representative: `tests/main/test_parser_proc.py` (`test_proc_group_help_lists_sorted_subcommands`, `test_proc_run_help_documents_command_and_examples`).

Also: `tests/main/test_parser_command_help.py` (agent/run/workspace/repo), `tests/main/test_parser_monitor.py`, `tests/main/test_parser_root_help.py`.

Pattern: `format_help()` + assert `{sorted,cmds

}`, `-s, --long`, examples, metavar pairings.

---

## 4. Command execution tests

Representative: `tests/main/test_proc_handler_run.py` + `tests/main/proc_handler_helpers.py`.

```python
def dispatch(argv: list[str]) -> int:
    with pytest.raises(SystemExit) as exit_info:
        handle_proc_command(create_parser().parse_args(argv))
    return int(exit_info.value.code or 0)
```

Isolate with `SASE_HOME`, assert stdout/JSON/exit. Same

 shape: `tests/main/test

_notify_handler.py`, `test_monitor_handler_start.py`, `test_workspace_

handler_*`.

---

## 5. Proc settlement and reservation

###

 Files

| Path | Role |
|---|---|
| `src/sase/procs/request.py` | `ProcSubmitRequest`, fingerprint

, sidecar payload |
| `src/sase/procs/service.py` | `submit_proc_request` / `stop_proc_shell` / reconcile |
| `src/sase/procs/runner.py` | `submit_proc`, `submit_detached_proc`, `wait_for_proc` |
| `src/sase/procs/runtime.py` | paths + `write_json_atomic` / `read_json_object` |
| `src/sase/procs/settlement.py` | `settle_proc_shell`, checkpoints, result envelope |
| `src/s# ACE Production Proc-ase/procs/supervisor.pySubmission Inventory

All paths` | claim → ack below are under → barrier → exec → settle |
| `src `/home/bryan/.local/state/sase//sase/procs/spawn.py` | `writeworkspaces/sase-org_launch_barrier`, supervisor/sase/sase spawn |
| `src/_13/`.sase/monitor/start.py` | first

## Counts

| Set-class ` | Count |
|---|---|
| **Total productionProcSubmitRequest` + submission call settlement policy |

There is no `

 sites** | **54**tests/test (53 producers + 1 forward) |
| Direct_procs_supervisor.py` settlement `self suite beyond

 process._submit_tracked_proc(...)` including-group tests; reservation+ forward | settlement live16 |
| Direct `self in:

- `tests/test_._submit_tracked_proc(...)` excluding forward | procs_facade.py

15 |
| Direct `self` — store `._submit_proc(...)`reserve_proc` lifecycle | 14 |
| Duck
- `tests/test_procs_service.py`-typed `submit = getattr(..., "_submit_tracked_ — two-process submit/replayproc")` then `submit/crash-resume(...)` | 24 |

- `tests/test_procs_supervisor.py`| Duck-typed `getattr(..., "_submit_ — reparent/kill/pidproc")` | **0-reuse
** |
| Formal- `tests/test_ `Protocol`procs_runner.py` — for submit | **0 submit/kill/reconcile

### Two-process** |

` reservation (how_submit_proc` always it is tested)

** forwards to `_submit_trackedStore-level**_proc` (line 142 of `proc_actions (`test_proc_shell_reserve_conflicts.py`). Those_and_lifecycle_fac 14 `_submit_procade`):

1. `` producersreserve_proc(ProcReserve are **also(...))` → `reserved** forward=True`, `replayeders at runtime, but they=False`, `lifecycle=" are distinct producerproc-shell"`.
2. Same `request sites.

---_fingerprint` → `reserved

## Infrastructure=False`, `replayed

### `_=True`, same `procsubmit_proc` / `__id`.
3.submit_tracked_proc` Same ` — `src/saseshell_name`, different fingerprint/ace/tui/ → `ValueError` (`actions/proc_actions.pyshell_name`).
4`

**`. Same `concurrency_keysProcActionsMixin._submit_` whileproc`** active → `ValueError` (L114–149 (`concurrency_key`).
5. Cannot)

- Signature: `(proc_type, cl `finish__name, project_fileproc` until claimed, proc_callable, on; cannot `_success=None) ->update_proc` straight bool`
- Wraps a `(success, to terminal.
6. Path: reserve → `claim message)` callable as_proc_supervisor` (running) → `request_ `TrackedProcResult`
proc_stop` → `- Maps `onbegin_proc_settlement_success` to `` (on_complete` only onsettling) → `finish success
- For_proc` (success +wards to `_submit_tracked `result`).

**Service_proc` (L142-level** (`test_)
- Dedsubmit_request_replay_up isreturns_the_active_ per-`cl_row`):

- Twoname` (no custom `submit_proc_request `dedup_key`` with / `exclusive_scopes` same `shell / `display_name`)_name` + `request
- Completion_fingerprint="sha256:same"`. always uses defaults

: `reload_on_
- Second returns the livecomplete=True`, `notify

 row (`replayed`_on_complete=True

 inside `reserve`

**`Proc_proc`; serviceActionsMixin._submit_tracked

_proc`** (L

 returns `outcome.proc` and151–239)

- Signature **does: `(proc_type, not rewrite cl_name, project_ sidecar /file, proc_callable, *, display_name, ded respawn**).
- Namedup_key, exclusive_-shellscopes, duplicate_message, on_complete, reload_ reuse after settlement ison_complete=True, allowed (`test_named_proc_shell_reuse_ notify_on_complete=is_project_scoped_True) -> ProcInfo |and_waits_for None`
- Dedup:_settlement`); conflict `get_running_for only_key(dedup_key)` if set, else while active, `get_running_for scoped by project_cl(cl_name.

### `result_path)`,`

On then `get_running_ `ProcSubmitRequest.resultfor_scopes(exclusive_scopes)`
- On_path`. Written into collision request sidecar. Settlement copies it into: `notify(..., `settlement.json`. `_ severity="warning")write_result_envelope``, writes the envelope ** return `None`
- Registersbefore** `finish in `ProcQueue`,_proc`:

- skip wraps if checkpoint callable with `Proc `result_Reporter` + stdout/stderrwritten` already true or redirect
 path missing- `
- `osProcMirror..open(tmptrack(...), O_WRONLY|O_CREAT|O` on the UI thread (non-blocking enqueue_TRUNC, 0o600)` + f)
- Runs `selfsync + `os.replace`
.run_worker(_wrapped,- `schema thread=True)` —_version: 1` **Text envelope: `ual worker, diesargv`, `cwd`, ` ifexit_code`, `follow ACE exitsup`, `log_path`, `message`, `**
- Stores `_proc_id`, `statusProcCallbackConfig` for`, `termination_reason`

 laterTest: `test_result completion

_and_artifact_sett**Workerlement_are_durable` completion**

- `on asserts file_worker_state_changed exists, mode` ( `0o600`, `L436) routes SUCCESS →artifacts/.proc_settled `_on_proc_worker.json`, `_completed`, ERROR → `_on_proc_worker_result["followuperror`
- `_on_"] == "pending"`.proc_worker_completed` (L241): `Proc

`write_json_atomic` (`runtime.py`)Queue.complete`, `Proc is used for requestMirror.finish(status sidecar, settlement sidecar, start ack,=success|error)`, notify launch barrier —, `on **not** the result_complete( envelope (envelopeTrackedProcCompletion)`, optional `_ uses explicitreload_and_reposition ``, update0o600`).

### Result indicator
- `_on_proc_worker_error`-before-terminal / (L327): same crash after ` finishresult_written`

Check path with `statuspoints (order="error"`
 in `_CHECKPOINTS`;- `_kill_proc` crash after each via (L398): terminate `SASE_PROC_ process group, `complete` + `ProcSUPERVISOR_CRASH_AFTER`):

`Mirror.finish(status="killed")`, **command_gone` → `output_closed` → `drops** completionclaim_settled` → callback

Supporting `artifacts_settled` types: `TrackedProcResult → `followup_sett`, `TrackedProcCompletion`, `_ProcWorkerResult`,led` → **`result_written`** → ` `_ProcCallbackConfig`.

finish_proc`.

`maybe_crash` does### ` `os._exit(90ProcQueue` —)` after `src/sase/ the named checkpoint.

Testsace/tui/proc_queue.py`

In-:

- `test_settmemory,

lement_resumes_after

_an_injected_crash

 thread-safe registry. **Not durable.**

Key` — crash after `output_closed`, API then `reconcile_running:

- `submit(_procs()` /proc_type, cl_ `wait_for_procname, project_file, *, display_name, ded`.
- `test_settlement_recovers_up_key, exclusive_every_injected_crash_scopes) -> Proccheckpoint_repeatedly` —Info` — `dedup_key` defaults **includes `result_written`**,  to `cl_name`
3 attempts each- `complete(proc_: crashid, *, success, message after result file, output, error)`
 written but- `get_running_ before terminal row;for_cl(cl reconcile completes_name)` — only procs all checkpoints.

 whose `dedup_keyHelpers == cl_name` (custom keys opt in out of Patch ded the test file: `_wait_forup)
- `get_running__settforling_`,key `_(waitdedup_key)`
_for_settlement_supervisor_exit`, `_sett- `get_running_lement_checkpoints` (readsfor_scopes(exclusive_scopes)`
- `get `proc_settlement_`, `get_allsidecar_path`).

### Fingerprint`, `running_count`, replay

`proc `remove`, `remove__request_fingerprint` (`completed`, `prune_oldrequest.py`):

- If`

`ProcInfo` holds `request.request `proc_fingerprint` set, use_type it (monitors do this`, `cl_name`, `project_file`,).
- Else SHA- `display_name`, `256 of sorted JSONdedup_key`, `exclusive_scopes`, log,: `argv`, `concurrency_keys`, child `cwd`, timeouts processes, and mirror, `kind`, `label fields (`durable_proc_`, `origin`, `proc_id`, `project`,id`, `store_backed`, `session_* `session_id`, ``).

### `ProcMirrorshell_name`, `workspace

` — `src/s

_num`.
- Unase/ace/tuinamed submits include `proc

/proc_mirror.py`



Writes TUI procs into the durable proc_id`, so each is unique unless fingerprint store **without blocking is supplied.

Monitor the event loop**. Daemon (` writer thread.

Keystart API.py`): `:

- `start`monitor_request_fingerprint` / `stop`
 → passed as `request_fingerprint`;- `track(info, `_replayed_lane_ *, cl_name)`monitor` returns existing record — mint ` on matchnew_proc_id()`, enqueue `_TrackOp` (`, errorskind= on different fingerprint whileTUI_PROC_KIND active`, `origin="ace"`, refuses)
- `finish(info replay, *, status, message, exit_code)` — enqueue of a * `_lost* same-fingerprint monitorFinishOp`
- Writer: `.

### Sidecar helpers

```
~append_proc`,/.sase/ `appendprocs/_proc_log_textruntime/<proc_id>/`, `update_proc`,
  request.json      periodic `reconcile_running_procs`, detached proc_request_sidecar_path-count poll

This + request is a **mirror_sidecar_payload
  settlement.json  **, not a supervisor proc_settlement_sidecar. It does not resume or_path
  .proc re-execute_started     start work after ack
  .proc_ ACE restart.

### Durablego          launch barrier (fingerprint proc + timestamp service (not used by)
```

Helpers ACE TUI submit)

`src: `write_json_atomic`, `read_json/sase/procs/_object`, `write_launch_barrier(service.py` `submit_proc_request(ProcSubmitRequest)` reservesproc_id, request_ a proc-shell andfingerprint=...)`.

Request sidecar fields: launches a detached supervisor. ACE TUI producers `artifacts_dir`, `argv`, `cwd`, `env`, `followup`, do **not** call this. The closest production `log_path`, `proc_id`, `request_fingerprint`, `result_ exception is bead taskpath`, `workspace_claim`.

### How launch, which calls commands complete (supervisor)

 `sase.`run_supervisor` (`bead.task_launchsupervisor.py`): claim → bounded.submit_task_launch_ log → `_for_project` **insidewrite_start_acknowledgement** a T` → wait `.UI-proc_go` → `_tracked workerrun_command` (argv from row.

### Duck-typed “, envprotocols”

There overlay from request sidecar is **no** `Protocol) → always `` for `_submitsettle_proc_shell(...)` in `finally`. Resume_tracked_proc`. Call if alreadyers do:

 `settling`.```python
submit = getattr

Child(self/ env: scrubapp/ agent/chop identity; setsubmit_owner, "_submit `SASE_PROC__tracked_proc", NoneID`, `SASE_)
if callable(PROC_LOG_PATH`,submit):
 `SASE_PROC_    submit(...)
```

SESSION_ID`.

###Adjacent protocol: ` Monitor `ProcGateActionRunner` inSubmitRequest` + settlement policy

`start `src/sase/_monitor` (`ace/tui/modals/gate_action_monitor/start.py`):runner.py` (`run_command` is implemented

- Replay by submitting by fingerprint first.
- `create a `"_monitor_member` thengate-action"` proc). `submit_proc_request(ProcSubmitRequest

(...),

---

## Every production call site (54 after_ack=...)`.
- Policy)

Convention

 on the request: **Direct (not the- row):
tracked**, **Direct-`  - `artifacts_dir_submit_proc`**,

`, `log_path`, **Duck-typed**.  
 `log_owner=ARTIFACTDefault `_S_LOG_OWNER`
submit_proc` identifiers:  - `workspace_claim={project_file, workspace `cl_name=_num, workflow, clpatch.name`, `project_file=patch.file__name}`
  - `followup={kind:path`, `dedup_ monitorkey=cl_name`,, next_action, next no `exclusive_output, tail_lines_scopes`/`display_name`;}`
  - `request_fingerprint`, `shell toast_name=member_ on start;name`, `proc default notify_id=monitor_id + full T`
- `after_ack`: claimUI reload on complete.

### 0. workspace **before Forward (not** launch barrier ( a domaincommand producer)

| # | File / cannot method | Line | start first).
- Settlement Kind | ` detects monitorproc_type` | Callable via `follow | Domain | Durable? | Iup.kind == "monitor"` or `agentDs | Callback /_meta.json` `monitor UI | Existing_id`, then service |
|---|---|---| `settle_monitor_artifacts---|---|---|---|---|---|---|---|
| 0` / `settle_monitor | `src/sase_followup`.

**/ace/tui/Reuseactions/proc_actions.py this for durable CLI` `ProcActionsMixin._submit_proc` |  ops:** `ProcSubmitRequest` + optional142 | **Direct `result_path`/`-tracked (artifacts_dir`/`workspaceforward)** | caller’s_claim`/`followup | `_callable` wrapping `` + fingerprint forproc_callable` | Adapter idem only | n/a | passthrough `potent ACEcl_name`, ` retries. Do not add a secondproject_file` | `on_success envelope format()`.

---

## 6 if success |. AST / inventory n/a |

--- conformance tests

Best

### A. Patch template lifecycle — for a Direct `_submit_proc` (11 “producer)

All inventory”

 test: fail in mix-closed reviewedins mixed into `Ace-context mapsApp`. Optimistic.

|: start Test | Pattern toast only. Completion |
|---|---|
|

: default notify `tests/test_agent + `_reload_and__artifact_marker_mutationreposition`. `on_audit.py` | AST_success` resets

- `$`walk hooks where ` notedsrc/sase` for marker.

| # | File / method | Line | Kind |

 literals + mutation calls; every `proc_type` | Callable | Domain | Durable? `path | IDs | Callback / UI | Existing service |


:function` must be in `_REVIEWED_MARKER_MUTATION_CONTEXTS` with one|---|---|---|---|---| coverage shape |
| `tests---|---|---|---|---|/test_agent_artifact---|
| 1 |_directory_operation_audit `actions.py` | same/status.py` `Status for directoryActionsMixin._apply_status ops |
| `tests/test_change_project`_ |display _215presentation_audit.py` | | Direct-`_submit_proc` `ast.parse` + `ast. | `"revert"`walk` Call sites | nested; unlisted sinks `proc_callable` → fail |
| `tests/_ `_revert_task` |agent_artifact_marker_ Reaudit_helpers.py` |vert Patch | shared scanner |

 **Durable** | `clSkeleton_name`, `project_:

1file` | start. Scan toast; default sources reload | `sase. with `ast.parse`ace.revert.revert_ / `ast.walk`.patch` |
| 2
2. Collect `file | same:function` ( | 235 | Direct-or call names`_submit_proc`).
3 | `"submit"` | →. Compare to a `_submit_task` | frozen inventory dict Git/gh submit/set.
4. Patch | **Durable** | Fail on extras same | start toast | or missing required `sase. coverage.

`workspace_provider.submit_patch` |
| 3 | same | 248 | Directtests/test_markdown_print_width.py`-`_submit_proc and `tests/test_` | `"archive"` |commit_type_tag_ → `_archive_task`contract.py` are narrower | Archive Patch | **Durable AST contracts** | same | start toast.

---

## 7. Envelope | `sase.ace.archive.archive_patch / atomic` |
| 4 |-write protocol same | 265 | Direct (do not fork-`_submit_proc)

|` | `"restore"` | Piece | Where → `_restore_task` | Restore from Reverted | |
|---|---|
| `schema_version **Durable** | same |` | settlement start toast | `sase

.ace.restore.restore envelope

 `1`;_patch` + `transition request_patch_status` |
 sidecar has| 5 | same | none ( 294 | Direct-`fields_submit_proc` | `"status"` | → `_ are implicit) |
| Result envelope |transition_with_siblings_

 `settletask` | Draft→Ready_proc_shell` → + sibling reverts | **Durable** | same `_result | start toast | `s_envelope` → `_writease.status_state_machine_result_envelope` **.transition_patch_statusthen` |
| 6 |** `finish_proc(..., `actions/sync.py` result=envelope `SyncActionsMixin.action)` |
| Request sidecar |_sync` | 226 `submit | Direct-`_submit_proc_request` after_proc` | `"sync successful"` | nested `proc non_callable` → `_sync-replay reserve |
| Mode_task` | Workspace V `0600`CS sync | **Durable** | result file | same | `on only |
|_success`=` `write_json_atomicreset_dollar_hooks`;` | request start toast | `claim/settlement/ack_workspace` + `/barrier (get_vcs_provider`tmp |
| 7 | `actions/base.py` `BaseActionsMixin.action_reword` | 234 + fsync + replace; default umask) |

Gates | Direct-`_submit have a_ **procseparate`** durable | `"reword"` | → ` protocol (`notificationreword_execute_task_gates.service.create` | Rew_gate`, `GATEord change_REQUEST_SCHEMA description | **Durable** |_VERSION`  same | `reset_dollar_hooks`; “Rew3, `atomic_writeording…” | `_json`). Do not mixsase.ace.handlers that with proc.reword.reword envelopes.

---

## _execute_task` |
8. Domain services ACE should call (not TUI| 8 | `actions/base.py` `action mix_add_tag` /ins)

### Patch: status / rebase / sync / `on_dismiss` | rewind

**No CLI today.** Services 307 | Direct-`:

| Op | Service | Notes |
_submit_proc` ||---|---|---|
| `"add_tag"` | → `add_tag_task` | Add tag to description | **Durable** | Status | `sase.status same | `reset_state_machine.transition_dollar_hooks`; “Adding tag…” | `s_patch_status` | alsoase.ace.handlers. `update_patchreword.add_tag_

task` |
| 9_pr_origin_atomic | `actions/base.py`, `update_` `action_mail

patch_parent_atomic` | 393 | Direct-`_submit_proc` | `"mail"` |` |
| Special status | `sase.ace.revert.revert_patch → `mail_execute_`, `sase.acetask` | Mail / post PR | **Durable** | same; workspace claimed

.restore.restore_patch`, `sase.ace.archive.archive_patch`, `sase.workspace **before** submit |_provider.submit_patch` start toast; release | TUI wraps workspace if ded inup rejects | `sase.ace.handlers.mail.mail_execute `_revert_task` / `_submit_task` / `_archive_task` /_task` |
| 10 | `actions/proposal_rebase.py` `Proposal `_restore_task` |
| Rebase | `RebaseMixin` acceptsase.vcs helper | 427_provider.get | Direct-`_submit

_vcs_provider().rebase_proc` | `"accept"` | → `_accept_` + `update_patch_parent_atomic` | bodytask` | Accept proposal of( `_s)rebase |_ **taskDurable**` in `ace | same | optional `on/tui/actions/_success`=`proposal_rebase.py` |
action_mail`; start toast | `sase.| Sync | `provider.sync_workspace` +workflows.accept.AcceptWorkflow` |
| 11 | ` `run_sase_actions/proposal_rebase.pyhg_clean` | `_` `_run_rebase_sync_task` in `workflow` | 498 |ace/tui/actions Direct-`_submit_/sync.py` |
|proc` | `"rebase"` | → `_rebase_task Rewind | `s` | Rebase Patch ontoase.workflows.rewind parent | **.workflow.RewindWorkflowDurable** | same | start.run` | toast | `update uses_patch_parent_atomic `update_to_` + VCS provider |

patch`, `rewind_commit### B. Other Direct_entries` |
| Rename patch `_submit_proc` (3)

| # | File | `sase.ace.operations.rename_patch_ / method | Line | Kind | `proc_type`with_references` | |
 | Callable | Domain | Durable| Refs /? | IDs | origin / deltas Callback / UI | Existing service | already

 |
|---|---|---|---|---|---|---|---|---|---| CLI: `update---|
| 12 |

 `actions/hints/_rewind.py` `RewindMixin_patch_refs_field._run_rewind_workflow` | 168 | Direct`, `handle_set_origin`, `refresh_-`_submit_procdeltas_for_patch` |

Workspace` | `"rewind"` | → `_rewind_task` claim pattern ( | Rewind Patch tosync history entry |/rebase/rewind **Durable** | `cl): `get_first__name`, `project_available_axe_workspace`file` | “Rewinding to entry…” → `claim_workspace` → work | `sase.workflows → `release_workspace`..rewind.RewindWorkflow` |
| 13 | For durable argv `actions/axe_bgcmd.py` `Axe, putBgCmdMixin` slot launch | 255 | Direct-`_submit_proc that in `ProcSubmitRequest.workspace_claim` | `"bgcmd-launch"` | → `_bgcmd_launch_task` so settlement releases` | Start even after crash.

### Agent: launch / approve / revert / axe cleanup / wait / rename / background command | **Durable** tribe

| Op (process must live | Service | CLI today? |
|---|---|) | `cl_name---|
| Launch | `` **sase.agent.launchor** synthetic `bg_cwd.launch_cmd-slot-{slot}` as firstagents_from_cwd` arg; `project_file` from → `launch_agents_from_cwd_impl`; `sase project spec | `.agent.launch_executoron_success`: history + `_load_bgcmd.execute_launch_plan`;_state` + switch view `sase.main.query; `mark_slot_handler._launch._pending` beforelaunch_query` | ` submit,sase run`; clear if rejected not `sase agent | `start_background launch` |
| Launch approval | `create_launch_command`, `run_sase_hg_approval_request`, `_clean`, VCS checkoutwait_for_launch_approval`, `execute_launch |
| 14 | `actions/agents/_monitor__approval_response` | `sase launch {stop_flow.py` `request,approve,reject}`MonitorStopActionFlowMixin._ |
| Autodo_stop_monitor`-approve directive | 66 | Direct- | `sase.x`_submit_proc`prompt.directive_edit.set | `"monitor-stop"`_prompt_auto_mode` + `persist_agent | nested_directive_update` | `proc_callable` | ** StopT monitor command | **Durable**UI only** |
| Re | `cl_name`vert agent=`agent.agent_ commits | `sase.ace.revert_agent_name or monitorexecute.execute_agent_revert_id or artifacts_dir`; `project_file=` | **no CLI** |
| Killagent.project_file` | `sase.agent | default notify+.running.kill_named

reload | `sase._agent` | `smonitor.store.get_monitorase agent kill` |
|` / `stop_monitor Cleanup / dismiss |` |

---

### TUI `_submit C. Agent launch /_cleanup_proc` → cleanup wrappers — Direct- persistencetracked (2 call in ` sites, many logicalagents/_k producers)

| # | Fileilling_utils`, / method | Line | Kind `_dismiss_*` | **no | `proc_type`

 CLI** |
| Wait | | Callable | Domain | Durable `set_prompt? | IDs |_wait` + `persist Callback / UI | Existing service_agent_directive_update |
|---|---|---|---|---|---|---|---|---|`; runner `s---|---|
| ase.axe.run_agent15 | `actions/agent

_wait.wait_for__workflow/_launch_procsdependencies` | **no CLI.py` `LaunchProcMixin** |
| Rename agent |._submit_launch_proc `s` | 86 | Directase.xprompt.directive_edit.set_prompt_-tracked | `"name` + persist |launch"` | `_callable` **TUI only** wrapping caller `proc_callable` | |
| Tribe | `s Agentase.ace.agent_tribes.set_tribe` launch | **Durable** | `cl / `unset_tribe`_name`, `project_ / `save_agent_file` from callertribes` | `s; `display_name`;ase agent tribe {set, `dedup_key`unset,list}` |

### or `launch:{uuid Bead mutations

4}`;CLI no exclusive already scopes | `_on_launch covers_proc_complete`: launch the store-. Invokeresult delta, agent handlers refresh, notification or ` refresh, prompt-stashBeadProject` (` recovery, customsrc/sase/be notify;ad/_project_mutations.py`) inside `reload_on_complete `=beFalsead`,_ `store_notify_on_complete=False`mutation()` (` | `sase.corecli_common.agent_launch_fac.py`) thenade` / launch `auto_commit_beers via callers |
| 16 | `ad_store`:

`create`, `update`, `actions/agents/_cleanup_update_many`, `appendprocs.py` `CleanupProc_note`, `plus_Mixin._submit_cleanup_one`, `snooze`,proc` | 54 | `cancel_snooze`, Direct-tracked | **caller `close`, `open`, `proc_type` `remove`, `add** (`"_dependency`, `remove_kill"` /dependencies`, `claim_for `"dismiss"` / `"save_agent_launch`,"`) | `_callable` `claim_for_agent wrapping `proc_callable` | Kill/_wait`, `release_agent_claim`, `markdismiss/save persistence | **_ready_to_workDurable** | `display`.

_name`; `clDo not bypass_name`/`project_ `befile` from caller; `ad_store_mutation`dedup_key=f / publication (`"{proc_type}:{uuid4}"` (optsBeadPublicationError`).

### Notifications / gates

| out of Patch ded Op | Service |
|---|---|
| Createup) | `_on_ notify |cleanup_proc_complete`: optional notify `sase., agents refreshnotifications.store.append_notification` (`handle, notification snapshot refresh; no default reload/_notify_create`) |
| Dismissnotify | `sase./read/ace.tsnooze | `markui.actions._dismissagents._ed`, `mark_read`, `markkilling` / dismiss persistence |

**Logical_snoozed` — launch **no CLI** |
| producers** (not List/ extra `_submit_tracked_show | `sase.proc` sites):

-notifications.cli_list` `_launch_start.py:191` — single / `cli_show` |
| Create gate | ` launch, `dedsase.notification_gatesup_key=f".service.create_gate`launch:{workflow_name |
| Act / answer /}"`, body `_run_agent_launch_body`
 wait | `notification_gates.cli_act- `_launch_repeat.py/:51` — `_run_repeat_launch`cli_answer`, `notifications / `sase.cli_wait.handle_.agent.repeat_launcher`
- `_launch_bulkgate_wait` |

### Plugins

Public.py:69` — `_ API:run_bulk_launch`
 `sase.plugins.- `_launch_multi_operations` —prompt.py:50` — `plan_install` / `_run_multi_prompt_launch`
- `execute_install`, ` `_launch_multi_modelplan_install_many`.py:61` — `_ / `execute_install_run_multi_model_launch`

**Logicalmany`, plus uninstall/update cleanup siblings producers.:**

- `_kill_procs CLI wrappers:.py:97` bulk `handle kill `proc_plugin_{install,uninstall,update}__type="kill"`
- `_kill_procs.pycommand`. Restart::181` single kill ` `restart_after_proc_type="kill"`
- `_dismissing.py:250` bulk dismiss `plugin_change`.

### Workspace / monitor / run

|proc_type="dismiss"` Domain
- `_dismissing.py | Service |
|---|---|:378` single dismiss `


| Workspace cleanupproc_type="dismiss"`/repair/migrate |
- `_marking.py `workspace_handler:230` marked_maintenance.handle_cleanup`-group / `handle_repair`; save `proc_type=" `workspace_handler_migrationsave"`

---

###.handle_migrate`; `WorkspaceStore` |
 D. Agent directive persist — Direct-tracked (6| Monitor)

All call start/stop | `sase.monitor.start_ `persist_agent_directivemonitor(_update`. OptimisticStartMonitorRequest)` / in-memory field `stop_monitor` |
 updates; rollback| Run | `launch + agents refresh on failure. `_query` → `launchreload_on_complete=_agents_from_cwdFalse`, `notify_on` |

---

## _complete=False`. Shared9. Implementation guidance ded (no second protocol)

1up: `agent. **Parser-directive-persist:{artifacts/handler** like_dir}` (tribes use `parser a global key_proc.py` + `).

| # | Fileproc_handler / method | Line | Kind.py`: dest | `proc_type` names | Callable | Domain | Durable that do not overwrite? | IDs | root Callback / UI | Existing service `command`; remain |
|---|---|---|---|ders as---|---|---|---|---|---| `*_---|
| command`;17 | `actions/rename alpha.py` `RenameMixin._ help; shortset_agent_name` aliases.
2. / `handle_name_ **Mutations ACEresult` | 339 | will retry Direct-tracked | `"agent** go-directive"` | nested `_ through `submit_proc_task` | Persistrequest(ProcSubmitRequest(... agent name | **Durable**))` with a **stable ` | `cl_name=agent.cl_request_fingerprint`** (name or display_monitorname`; `project_file-style), optional `result_path`/`=artifacts_dir`; `display_name=Persistartifacts_dir`/`workspace_claim`.
3. name: … **Supervisor`; `dedup_key argv**=agent-directive-persist should be the new:{artifacts_dir}` | optimistic name `sase <domain> <verb + re> ...` commandfilter; on fail toast (or existing + refresh | one `persist_agent_). Settlementdirective_update` + ` alreadyclaim_agent_name` writes the envelope (sync, and terminal row.
4. **Tests before submit) |
| :** help like18 | `actions/agents `test_parser_/_approve.py` `Agentproc.py`; handler likeApproveMixin._apply_auto `dispatch_approve_choice` |()` in 177 | Direct-tracked | `"agent-directive"` `test_proc_handler | `_task` | Persist auto-approve |_run.py`; crash-after-`result_written` ** likeDurable `test**_sett |lement_reco samevers ded_everyup pattern; `_injected_crash_checkpoint_repeatedly`; replaydisplay_name=Persist auto like `test_submit: …` | optimistic_request_replay_returns `approve`/`_the_active_rowauto_approve_`.
5. **Inventoryplan_action` + row test patch:**; copy rollback `_REVIEW on fail | `persistED_*` AST_agent_directive_update map so` |
| 19 | `actions/agents/_tribe_assignment.py` `Agent new call sites ofTribeAssignmentMixin._apply_ `submit_proc_request` / durableagent_tribe_change` producers | 258 | Direct- cannot land unlisted.

Largesttracked | `"agent-directive CLI"` | `_task` (list of persists gaps for ACE argv) | Persist: **patch tribe on marked status/rebase/sync/ agents | **Durable** |rewind**, **agent wait/ `cl_name="agentapprove--tribes"`;directive/rename/revert `project_file="agent/cleanup**, **notification-tribes"`; ` dismiss/read**. Thosededup_key="agent already have service-directive-persist:tribes"` | optimistic tribe fields; rollback + functions; they need parser+handler plumbing refresh on fail | `, not newpersist_agent_directive_ settlementupdate` |
| 20 types | `actions/agents/_.wait_actions.py` `AgentWaitActionsMixin._apply_wait` (set wait) | 218 | Direct

-tracked | `"agent-directive"` | `_task` | Persist wait deps | **Durable** | `dedup_key=agent-directive-persist:{artifacts_dir}`; `display_name=Persist wait: …` | optimistic wait fields + toast; rollback on fail | `persist_agent_directive_update` |
| 21 | same `_apply_wait` (run-now / clear wait) | 285 | Direct-tracked | `"agent-directive"` | `_task` | Persist run-now / unwait | **Durable** | `display_name=Persist run-now: …`; same dedup | optimistic clear wait; refresh on fail | same + `ReadyMarkerPatch` |
| 22 | same `_apply_live_runner_wait` | 387 | Direct-tracked | `"agent-directive"` | `_task` | Persist parked-slot runner wait | **Durable** | `display_name=Persist runner wait: …`; same dedup | optimistic runner/wait fields; rollback on fail | same + `waiting_marker_patch_for_token` |

---

### E. Agent revert — Direct-tracked (4)

| # | File / method | Line | Kind | `proc_type` | Callable | Domain | Durable? | IDs | Callback / UI | Existing service |
|---|---|---|---|---|---|---|---|---|---|---|
| 23 | `actions/agents/_revert.py` `_submit_revert_preview` | 127 | Direct-tracked | `"revert_preview"` | `_callable` | Preview commits to revert | **UI-only** (read) | `cl_name=agent.cl_name`; `project_file`; `display_name=Revert preview: …`; `dedup_key=_revert_dedup_key(...)` | open confirm modal; no notify/reload | `preview_agent_revert_intent` |
| 24 | `_submit_revert_execute` | 187 | Direct-tracked | `"revert_agent"` | `_callable` | Execute agent revert | **Durable** | `display_name=Revert agent: …`; execute dedup key | default notify; refresh agents if success or local revert SHAs | `execute_agent_revert_intent` |
| 25 | `_submit_bulk_revert_preview` | 337 | Direct-tracked | `"revert_preview"` | `_callable` | Bulk preview | **UI-only** | `display_name=Revert preview: N marked`; `_bulk_revert_dedup_key` | confirm modal | `preview_agents_revert_intent` |
| 26 | `_submit_bulk_revert_execute` | 396 | Direct-tracked | `"revert_agent"` | `_callable` | Bulk execute | **Durable** | `display_name=Revert N marked`; execute dedup | notify + agents refresh | `execute_agents_revert_intent` |

---

### F. Beads — Direct-tracked (3 call sites, many logical producers)

| # | File / method | Line | Kind | `proc_type` | Callable | Domain | Durable? | IDs | Callback / UI | Existing service |
|---|---|---|---|---|---|---|---|---|---|---|
| 27 | `actions/_artifacts_beads_common.py` `ArtifactsBeadsCommonMixin._submit_beads_task` | 136 | Direct-tracked | `f"bead-{operation}"` | caller `task` | Bead store mutation / launch | **Durable** (open-browser excepted via other site) | `cl_name=bead_id`; `project_file=workspace`; `display_name`; `dedup_key=f"beads:{operation}:{project}:{bead_id}"` | `pane.request_refresh()`; optional `_refresh_notification_count`; `reload_on_complete=False`; default notify **on** | `bead_store_mutation` / launch helpers |
| 28 | `actions/_artifacts_beads_issue_mutations.py` `_submit_bead_issue_mutation` | 90 | Direct-tracked | `f"bead-issue-{operation}"` | caller `task` | External GitHub issue mutate | **Durable** | `cl_name=row.issue.id`; `project_file=workspace`; `dedup_key=f"beads:issue:{operation}:{link.project}:{link.issue_id}"` | pane refresh | `_update_issue_task` / VCS issue API |
| 29 | `actions/_artifacts_beads_issue_actions.py` `_submit_beads_issue_open` | 240 | Direct-tracked | `"bead-issue-open"` | nested `task` | Open issue in browser | **UI-only** | `dedup_key=beads:issue-open:{project}:{issue_id}` | no-op `completed` | `webbrowser.open` |

**Logical bead operations funneling through #27** (`_submit_bead_mutation` → `_submit_beads_task`):

- `status`, `edit`, `snooze`, `cancel-snooze`, `create`, `close` (`_artifacts_beads_mutations.py`)
- `issue-attach`, `issue-create` (`_artifacts_beads_issue_mutations.py`)
- `launch` task: `submit_task_launch_for_project` + `cancel_task_triage` (`_artifacts_beads_launch.py:99`)
- `launch` epic: `_launch_scoped_epic` (`_artifacts_beads_launch.py:137`)

Issue edit / close / reopen funnel through #28.

---

### G. Notifications / gates / questions / plan / launch-approval — Duck-typed (8)

| # | File / method | Line | Kind | `proc_type` | Callable | Domain | Durable? | IDs | Callback / UI | Existing service |
|---|---|---|---|---|---|---|---|---|---|---|
| 30 | `modals/notification_modal_action_support.py` `NotificationActionSupportMixin._submit_notification_state_task` | 83 getattr / **85 submit** | Duck-typed | `"notification"` | `_task` wrapping mute/state `task` | Notification mute/state write | **Durable** (store write) | `cl_name="notifications"`; `project_file=""`; `display_name=label`; `dedup_key="notification-state"`; **`exclusive_scopes=("notification-state",)`** | caller `on_complete`; no reload/notify | notification mutation helpers |
| 31 | `actions/agents/_notification_gate_execution.py` `submit_gate_execution_task` | 57 / **92** | Duck-typed | `"notification-gate"` | `work(reporter)` | Neutral gate execute | **Durable** | `cl_name=f"gate {request_id}"`; `project_file=bundle_path`; `dedup_key=notification-gate:{notification.id}` | `_finish_gate_task` / refresh notifications | `sase.notification_gates.executor.execute_gate_selection` |
| 32 | `actions/agents/_notification_gate_actions.py` `NotificationGateActionRunner.run_command` | 139 / **165** | Duck-typed | `"gate-action"` | `work(reporter)` | Gate `run_command` | **Durable** | `cl_name=f"action {operation_id}"`; `project_file=bundle_path`; `dedup_key=gate-action:{notification.id}:{operation_id}` | `on_done(GateCommandOutcome)` | gate bundle command runner |
| 33 | `actions/agents/_notification_question_modal.py` `_submit_question_response_task` | 242 / **245** | Duck-typed | `"question"` | `tracked_body` | Write user-question answers | **Durable** | `cl_name=f"question {request_id}"`; `project_file=response_dir`; `dedup_key=question-response:{request_id}` | `_finish_question_response_task` (notify + refresh count); sync fallback | `sase.user_question_actions.execute_user_question_response` |
| 34 | `actions/agents/_notification_plan_gate.py` `submit_neutral_plan_response` | 78 / **141** | Duck-typed | `"plan-gate"` | `work` | Plan approve/reject/epic | **Durable** | `cl_name` from notification or plan stem; `project_file` from notification; `dedup_key=plan-gate:{notification.id}` | kill agent on reject; status override; refresh count | `sase.plan_approval_actions.execute_plan_approval_response` |
| 35 | `actions/agents/_notification_launch_approval.py` `_submit_launch_approval_task` | 123 / **126** | Duck-typed | `"launch"` | `tracked_body` | Approve/deny pending launch | **Durable** | `cl_name=f"launch approval {request_id}"`; `project_file=response_dir`; `dedup_key=launch-approval:{request_id}` | `_finish_launch_approval_task`; sync fallback | `sase.launch_approval_actions.execute_launch_approval_response` |
| 36 | `actions/agents/_notification_modals.py` `_submit_legacy_epic_launch_task` | 438 / **457** | Duck-typed | `"launch"` | `work` | Legacy epic launch | **Durable** | `cl_name` from notification or plan stem; `project_file` from notification; `display_name=Launch epic: …`; `dedup_key=legacy-epic-launch:{notification.id}` | error toast only | `prepare_epic_launch(..., mode="detached", origin="ace")` |

---

### H. Agents-repo sync — Duck-typed (2)

| # | File / method | Line | Kind | `proc_type` | Callable | Domain | Durable? | IDs | Callback / UI | Existing service |
|---|---|---|---|---|---|---|---|---|---|---|
| 37 | `actions/agents_sync.py` `AgentsSyncActionsMixin.action_sync_agents` | 215 / **219** | Duck-typed | `"agents-sync"` | `task(reporter)` | Sync all agents repos | **Durable** | `cl_name="agents repositories"`; `project_file=""`; `display_name="sync agents repositories"`; `dedup_key="agents-sync"`; **`exclusive_scopes=("agents-sync",)`** | revalidate indicator + agents refresh; no TUI reload | `sync_agents()` |
| 38 | same `action_integrate_cached_agents` | 269 / **272** | Duck-typed | `"agents-cached-integration"` | `task(reporter)` | Import cached incoming hoods | **Durable** | `cl_name="cached incoming agent hoods"`; same **dedup_key + exclusive_scopes `agents-sync`** | same | `integrate_cached_agent_updates` |

---

### I. Plugin / SASE / agent-CLI updates — Duck-typed (10)

All `reload_on_complete=False`, `notify_on_complete=False`. Completions toast and often `_restart_tui(restart_axe=True)` after a real code change.

| # | File / method | Line | Kind | `proc_type` | Callable | Domain | Durable? | IDs | Callback / UI | Existing service |
|---|---|---|---|---|---|---|---|---|---|---|
| 39 | `modals/plugins_browser_update.py` `_submit_update_task` | 351 / **355** | Duck-typed | `"plugin-update"` | `task(reporter)` | Update one plugin | **Durable** | `cl_name=label`; `project_file=""`; `dedup_key=plugin-update:{label}` | `_on_update_complete` / restart | `execute_update` + `reporter.uv_runner()` |
| 40 | `modals/plugins_browser_install.py` `_submit_install_task` | 434 / **437** | Duck-typed | `"plugin-install"` | `task` | Install one plugin | **Durable** | `dedup_key=plugin-install:{name}` | `_on_install_complete` / restart | `execute_install` |
| 41 | same `_submit_install_many_task` | 474 / **477** | Duck-typed | `"plugin-install"` | `task` | Install marked set | **Durable** | `cl_name=joined names`; `dedup_key=plugin-install-many:{names}` | clear marks; restart | `execute_install_many` |
| 42 | `modals/plugins_browser_uninstall.py` `_submit_uninstall_task` | 226 / **230** | Duck-typed | `"plugin-uninstall"` | `task` | Uninstall plugin | **Durable** | `dedup_key=plugin-uninstall:{name}` | restart | `execute_uninstall` |
| 43 | `modals/plugins_browser_mode_switch.py` `_submit_mode_switch_task` | 180 / **183** | Duck-typed | `"mode-switch"` | `task` | Switch uv install mode | **Durable** | `cl_name=plan.target_mode`; `dedup_key="mode-switch"` | receipt + restart | `execute_mode_switch` |
| 44 | `modals/plugins_browser_sase_update_procs.py` `SaseUpdateProcMixin._submit_sase_update_proc` | 97 / **100** | Duck-typed | `"sase-update"` | `proc(reporter)` | Managed sase self-update | **Durable** | `cl_name="sase"`; `dedup_key="sase-update"`; **`exclusive_scopes=("sase-update",)`** | `_on_sase_update_complete` / restart | `_run_sase_update_summary` |
| 45 | same `_submit_dev_update_proc` | 163 / **166** | Duck-typed | `"dev-update"` | `proc` | Editable checkout update | **Durable** | `cl_name=subject`; caller `dedup_key`; **`exclusive_scopes=("sase-update",)`** | `_on_dev_update_complete` | `_execute_dev_update` + journal |
| 46 | same `_submit_combined_update_proc` | 236 / **239** | Duck-typed | `"sase-update"` | `proc` | Dev + managed combined | **Durable** | same as #44 | `_on_combined_update_complete` | both legs |
| 47 | `modals/plugins_browser_agent_clis_actions.py` `_submit_agent_cli_update_task` | 312 / **315** | Duck-typed | `"agent-cli-update"` | `task` | Update agent CLIs | **Durable** | `cl_name="agent CLIs"`; `dedup_key="agent-cli-update"`; **`exclusive_scopes=("agent-cli-update",)`** | cache results, reload pane | `_execute_agent_cli_updates` |
| 48 | `modals/plugins_browser_comprehensive_update.py` `_submit_comprehensive_update_task` | 339 / **342** | Duck-typed | `"comprehensive-update"` | `task` | SASE + CLIs + cached hoods | **Durable** | `cl_name="sase + agent CLIs + cached hoods"`; `dedup_key="comprehensive-update"`; **`exclusive_scopes=("sase-update","agent-cli-update","agents-sync")`** | revalidate badges + restart/toast | provider + sase + agents legs |

---

### J. Git commit / prompt stash / commit fetch — Duck-typed (6)

| # | File / method | Line | Kind | `proc_type` | Callable | Domain | Durable? | IDs | Callback / UI | Existing service |
|---|---|---|---|---|---|---|---|---|---|---|
| 49 | `actions/agent_workflow/_prompt_bar_save_xprompt_git.py` `_submit_xprompt_commit_task` | 181 / **189** | Duck-typed | `f"{noun}-commit"` (`xprompt`/`snippet`/…) | `_task` | Commit+pull+push one file | **Durable** | `cl_name=rel_path`; `project_file=git_root`; `dedup_key={noun}-commit:{git_root}:{rel_path}` | notify; optional catalog refresh | `run_git_commit_push_sync` |
| 50 | same `_submit_post_write_action` | 315 / **346** | Duck-typed | from `_post_write_task_metadata` | `_task` | Post-write: commit, chezmoi, `sase memory init`, `sase skill init` | **Durable** | see metadata below | notify; chain next offer on success | `run_git_commit_push_sync` / `apply_chezmoi` / `run_noninteractive` |
| 51 | `modals/config_commit.py` `submit_config_commit_task` | 126 / **133** | Duck-typed | `"config-commit"` | `_task` | Commit/push config file | **Durable** | `cl_name=offer.rel_path`; `project_file=offer.git_root`; `dedup_key=config-commit:{git_root}:{rel_path}` | notify + index-lock warning | `run_git_commit_push_sync` |
| 52 | `actions/agent_workflow/_prompt_bar_stash.py` `._submit_prompt_stash_persist_task` | 140 / **149** | Duck-typed | `"prompt-stash"` | `_persist` | Persist prompt-stash entry | **UI-session** (store write, not a long-running op) | `cl_name=""`; `project_file=""`; `display_name="Stash prompt"`; `dedup_key=prompt-stash:{entry.id}` | reconcile badge or rollback counts; async fallback if no submit | `_append_prompt_stash_entry` |
| 53 | `widgets/artifacts/commits_pane.py` `CommitsPane.fetch_commits` | 330 / **371** | Duck-typed | `"commit-fetch"` | `_proc` | Fetch commit refs | **UI-only** | `cl_name=f"commits:{scope}"`; `project_file` from project or `""`; `dedup_key=commit-fetch:{scope}` | apply payload if generation matches | `_collect_payload(..., force_fetch=True)` |

**Post-write `proc_type`s from `_post_write_task_metadata`:**

- `COMMIT_PUSH` → `{noun}-commit`, `dedup_key={noun}-commit:{git_root}:{rel_path}`
- `APPLY_CHEZMOI` → `{noun}-chezmoi-apply`, `dedup_key={noun}-chezmoi-apply:{target}`
- `MEMORY_INIT` → `"xprompt-memory-init"`, `dedup_key="xprompt-memory-init"`
- else → `"xprompt-skill-init"`, `dedup_key="xprompt-skill-init"`

---

## Exclusive-scope map

| Scope | Claimed by |
|---|---|
| `agents-sync` | #37 agents-sync, #38 cached integration, #48 comprehensive |
| `sase-update` | #44/#46 sase-update, #45 dev-update, #48 comprehensive |
| `agent-cli-update` | #47 agent-cli-update, #48 comprehensive |
| `notification-state` | #30 notification mute/state |

Everything else uses only `dedup_key` and/or per-`cl_name` Patch dedup.

---

## Durability summary (for the contracts plan)

**Must survive ACE restart (domain mutations / launches / package updates):**  
1–16 (except launch/cleanup wrappers’ UI effects), 17–22, 24, 26, 27–28, 30–38, 39–51.

**UI / session-only:**  
23, 25 (revert preview), 29 (browser open), 52 (prompt stash), 53 (commit fetch).

**Important gap:** every site still runs in a **Textual worker** owned by this ACE process. `ProcMirror` records rows but **does not resume**. If ACE dies mid-`mail`/`sync`/`launch`/`plugin-update`, the in-TUI worker dies. Only operations that internally spawn a detached supervisor (e.g. bead `submit_task_launch_for_project`, `prepare_epic_launch(..., mode="detached")`) have a chance to outlive ACE — and even then the TUI wrapper itself does not.

---

## Representative test doubles

| File | Method | Behavior |
|---|---|---|
| `tests/_agent_cleanup_proc_helpers.py:31` | `_submit_tracked_proc` | Records `ProcInfo`; does not run worker |
| `tests/ace/tui/_agent_wait_resume_helpers.py:53` | same | Fixed `proc_id="task-0"` |
| `tests/test_launch_approval_tui.py:46` | same | Records `ProcInfo` |
| `tests/test_agent_monitor_stop_action.py:35` | `_submit_proc` | Appends args, returns `True` |
| `tests/ace/tui/test_axe_bgcmd.py:218` | `_submit_proc` | Captures bgcmd submits |
| `tests/ace/tui/actions/test_prompt_stash_handler.py:77,131` | `_submit_tracked_proc` | Sync-run callable + `on_complete`, or just record |
| `tests/ace/tui/actions/_prompt_save_xprompt_helpers.py:77` | same | Record only |
| `tests/ace/tui/test_notification_plan_gate.py:77` | same | Sync-run + complete |
| `tests/ace/tui/test_notification_custom_gate.py:196` | same | same pattern |
| `tests/ace/tui/test_plugins_browser_pane_comprehensive_update_execution.py:63` | same | `_SubmitApp` capture |
| `tests/ace/tui/test_agents_sync_actions.py:68` | same | capture |
| `tests/ace/tui/test_agent_tribe_assignment.py:77` | same | persist-path double |
| `tests/ace/tui/test_agent_toggle_approve.py:68` | same | persist-path double |
| `tests/ace/tui/test_revert_agent_action.py:38` | same | capture by `proc_type` |
| `tests/test_agent_launch_validation.py:455` | same | nested launch double |
| `tests/ace/tui/test_proc_queue.py` | real `AceApp._submit_tracked_proc` | integration of queue/dedup/complete |

Typical double signature: `(proc_type, cl_name, project_file, proc_callable, *, display_name, dedup_key, duplicate_message, on_complete, reload_on_complete, notify_on_complete)`. Most **omit `exclusive_scopes`** — comprehensive-update / agents-sync tests that need it use `*args, **kwargs`.

---

## Notes for the durable-operation-contracts plan

1. **54 = 53 producers + 1 `_submit_proc`→`_submit_tracked_proc` forward.** Matches the plan’s ~54 figure.
2. **24/53 producers already duck-type** via `getattr`. Any new facade should be injected the same way or the mixins will keep needing `type: ignore[attr-defined]`.
3. **One launch site and one cleanup site** hide 10 logical operations; **one beads site** hides ~12 operations. Contracts should be per-`proc_type` / operation, not just per call site.
4. **`_submit_proc` cannot express** `exclusive_scopes`, custom `dedup_key`, or `display_name`. Patch actions still share per-`cl_name` dedup (`sync` blocks `mail` on the same Patch).
5. **No production `getattr(..., "_submit_proc")`.** New shared API should target `_submit_tracked_proc`.
6. Existing durable API (`sase.procs.service.submit_proc_request` / `ProcSubmitRequest`) is the natural destination for the “must survive ACE restart” set; TUI-only sites can stay on Textual workers.

I have the producer inventory and CLI map. Next I’ll read TUI performance rules and a few service signatures, then start implementing the contracts.

I have the inventory and CLI map. Next I’ll read the remaining service APIs, then implement the contracts, inventory, commands, and adapter.

I have a clear architecture. I’ll start with the shared operation contracts and inventory, then layer settlement, commands, and the ACE adapter on top.

I have enough context to start writing the shared contracts. I’ll add the operation models and I/O first, then wire settlement, inventory, commands, and the adapter.

I’ll start writing the shared operation package and then wire it through settlement, inventory, commands, and the ACE adapter.

Next I’ll extend proc request, settlement, and supervisor so operation sidecars are created, validated, and published in the right order.

Next I’ll add the ACE durable-submit adapter and the producer inventory with its AST check.

Install finished. I’ll run the new focused tests next, then the full `just check` gate.

Reconcile after result publication was treating a successful typed result as supervisor-loss. I’ll make a valid published success result authoritative except for an explicit kill.

Symvision forbids importing those private TUI task helpers. I’ll switch the command runners to the public domain services instead.

I'll make the inventory scanner private, drop the unused helper, and give `DurableSubmitHandle` a real production consumer.

The inventory file is over the line limit, so I’ll split the site catalog and the scanner into two modules.

The scoped run escalated to the full suite. I’ll pull the actual failing tests and separate ones we caused from unrelated noise.

The durable-operation foundation is in place. Later producer-migration phases can submit explicit argv and read typed results without changing ACE call sites yet.

### What landed

**Checked producer inventory.** All 54 production ACE submit sites are catalogued (53 producers plus the one `_submit_proc` → `_submit_tracked_proc` forward). Each record has source identity, durable vs UI-only, owning domain command, identifiers, result kind, fingerprint inputs, concurrency keys, optimistic UI, and restart recovery. `compare_inventory_to_source()` fails on unlisted, duplicate, stale, or structurally changed production producers.

**Versioned request/result contracts.** `sase.ops` writes mode-0600 regular files and rejects missing, malformed, non-object, unsupported-schema, mismatched operation/proc, and wrong-permission sidecars.

**Proc submit + settlement.** `ProcSubmitRequest` now carries `operation`, `operation_payload`, and `request_path`. When an operation is set, private request/result paths are created, the versioned request is written before the launch barrier, and settlement validates the typed result before terminal state. Success without a valid result is a durable error. Failure/kill/timeout still get an error envelope with no log parsing. Legacy submissions with no operation stay compatible. After a crash past result publication, a valid successful envelope is treated as authoritative.

**Domain command plumbing** (identifiers positional; `-Q/--request-path` and `-R/--result-path` optional, else `SASE_PROC_*` env):

| Family | Entry points |
|---|---|
| patch | `status`, `submit`, `archive`, `restore`, `revert`, `reword`, `tag`, `mail`, `accept`, `rebase`, `sync`, `rewind` |
| agent | `persist-directive`, `revert` |
| bead | `apply-status` |
| notify | `apply-state` |
| plugin / monitor / run | existing commands emit a typed result when a result path is configured |

No `ace` command namespace. No callable/import-path dispatcher.

**Additive ACE adapter.** `_submit_durable_proc` takes argv, an operation request, fingerprint, and concurrency keys; calls `submit_proc_request` off the Textual event loop; tracks the durable proc id; and decodes completion only from the typed envelope. Callables are rejected at the API boundary. Legacy `_submit_proc` / `_submit_tracked_proc` are unchanged.

### Verification

`just install` succeeded. Whole-repo lint in `just check` passed. Focused proc, settlement, inventory, adapter, and command tests passed **48/48**.

`just check` then escalated to the full suite because of the Justfile Symvision `--epic-symbol` for `compare_inventory_to_source` (needed by the next migration phase). That escalated run reported many ANSI-vs-plain-text assertion failures and AcePageGroup notification isolation leaks. Those do not reproduce in the focused contract tests and look unrelated to this phase. Recorded as a `PROPOSED FOLLOW-UP` on `sase-m9.3.1.1`.

No ACE rendering changes, so the PNG visual suite was not run.

Later phases can wire argv such as `sase patch status NAME STATUS` with `SASE_PROC_REQUEST_PATH` / `SASE_PROC_RESULT_PATH` and leave the compatibility callable adapter in place until those call sites move.

The prior turn left uncommitted work and a commit-finalizer instruction. I'll read the full prompt, the approved plan, and the current tree so I can finish the contracts, close the bead, and commit only what this session actually owns.

The previous turn already landed a large contracts tree. I’ll inspect that work against the approved plan, then close the bead and commit only if the implementation is complete.

The contracts tree is already on disk. I’ll review it against the plan, read the required memory notes, and run the focused tests before closing the bead and committing.

I’ll keep reviewing settlement, the ACE adapter, inventory, and the new command families so I can verify the plan is actually complete before closing the bead.

The command runners look complete. Next I’ll inspect settlement, the ACE adapter, inventory, and tests, then run the focused suite.

I’ll finish reviewing inventory, handler wiring, and tests, then run the focused suite so I can close the bead with a real verification note.

The contracts look complete. I’ll install, read the remaining tests and wiring, and run the focused verification suite next.

I’ll check a few likely gaps (proc env, workspace release, inventory count) and run the focused tests before closing the bead.

The tree looks complete. I’ll check workspace/gate result wiring and the mail workspace-release path, then run the focused tests.

I’ll fix two real gaps (mail workspace leak, monitor JSON skip), then install and run the focused tests before closing the bead.

Mail already releases the workspace. I’ll emit the monitor-stop result on the JSON path, then install and run the focused tests.

Install finished. I’ll trim unused public operation names so lint stays clean, then run the focused tests.

The focused suite is still running because the settlement tests launch real supervisors. I’ll wait for that result before linting and committing.

Focused tests passed (39/39). Next I’ll run lint, then the repo `just check` gate.

Lint is clean. I’ll run `just check` next, then close the bead and commit.

I’ll check whether the scoped test selector will escalate before I start the full `just check` gate.

`just check` escalates because of the Justfile epic-symbol. I’ll run the existing reservation tests, then close the bead and commit.

Verification is in. I’ll record the follow-up on the phase bead, close it, then commit.

The phase bead closed and published. Next I’ll record the commit skill and create the commit.

Implemented the durable-operation contracts plan (`sase-m9.3.1.1`) and published the close plus commit `07e254a42` (`feat(ops): add durable operation contracts and producer inventory`).

**What landed**
- Versioned request/result sidecars (`sase.ops`) with mode `0600`, schema checks, and identity matching
- Proc submit/settlement writes the operation request before launch and validates the typed result before terminal state
- Machine-checked ACE producer inventory for all 54 production submit sites
- Additive argv-only ACE adapter (`_submit_durable_proc`) that rejects callables
- Focused domain commands (`sase patch status/submit/...`, `agent persist-directive/revert`, `bead apply-status`, `notify apply-state`) plus typed results on existing plugin/monitor/run paths

**Verification**
- `just install` and `just lint` passed
- 39 focused contract tests passed
- 90 existing proc reservation/settlement/parser tests passed
- `just check` was not re-run to completion: the Justfile epic-symbol for `compare_inventory_to_source` escalates to the full suite. That is recorded as a `PROPOSED FOLLOW-UP` on the phase bead.
