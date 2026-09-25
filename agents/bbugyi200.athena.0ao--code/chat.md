# Chat History - ace-run (0ao--code)

- **TIMESTAMP:** 2026-09-08 17:30:01 EDT
- **MODEL:** claude/sonnet
- **AGENT:** 0ao--code

## Prompt

%model:@medium
#gh:gh_sase-org__sase @plan:202609/artifact_links_require_real_changes.md

The above plan has been reviewed and approved. Implement it now.


## Response

I'll start by opening the plans sidecar repo using the required `/sase_repo` skill.

"plans" is a sidecar repo. Opening it now.

This is a substantial cross-repo implementation task. Let me start by reading the required reference memory and exploring the current code structure in both repos.

Now let me open the sase-core repo and survey the relevant code in both repos in parallel.

Given the scope (~4,400 Python lines + ~5,150 Rust lines across two repos), I'll parallelize reconnaissance with research agents before writing any code.

Good, found the primary repo root. Let me navigate there and locate the target files.

All files exist. Let me read them all now.

Now let's read the remaining files: commit.py, _artifact_link_commit.py, artifact_link_outbox.py, and the ArtifactLinkStore.

Three research agents are now surveying the Python finalization path, Python publication path, and the Rust sase-core modules in parallel. I'll wait for their reports before starting implementation.

Now let's read submission.rs and wire.rs for the finalizer module.

Now let's read the artifact_link module files.

Before pausing this turn to wait on the background research agents, I need to submit the SASE final declaration per project policy.

No changes have been made yet, so no final declaration is needed right now. I'll wait for the three research agents to finish before starting the implementation.

Now let's find the exact commit `0a1aef7d8` and check its diff, plus look at Rust binding adapter usage examples (`sase.core.rust`).

Now let's read the relevant lib.rs sections in detail: helpers around line 5180-5400 (finalizer), and 5698-6040 (artifact_link), plus module init and header comment blocks near lines 1-50, 300-480.

This is the exact commit that introduced the auto-commit-on-read behavior. Let's see the full diff.

Now let's look at the artifact_link pyo3 bindings section (5698-6040) and the module registration section (14580-14620) plus the doc-comment block near 450-480 and imports around 690-720.

I made an erroneous placeholder tool call just now — disregard it, it did no work. The three real research agents (Python finalization path, Python publication path, Rust sase-core modules) are still running in the background. I'll begin implementation as soon as their reports come in.

No pyi stub — types flow purely dynamically. Now let's look at the sase repo Python adapter pattern.

This is a rich, relevant module. Let's read `src/sase/core/finalizer_facade.py` and `src/sase/core/artifact_row_resolution_facade.py` (thin adapters) as concrete examples.

I now have a complete picture. Here is the full research report.

Found it. The actual working directory should be `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13` (the parent), which contains `src/`. Let's check there.

All four target files exist under the repo root. Let's read them in full, plus locate all other callers and related test files.

These are the append/inspect call sites (writer + doctor), not the drain function itself, but relevant context. Let's read those in context, plus search for "published" checks across the relevant dirs, and locate run_id/checkpoint/run_scoped patterns.

Good — this confirms the writer (`_record_read_link` in `read.py`, on every `sase artifact read`) appends to the outbox, and `link_health.py` (doctor) only inspects (read-only stats). Now let's search for "published" checks relating to agents/families across sdd/, agents_sync/, finalizers/.

I now have everything needed. Here is the complete research report.

---

# Research Report: Artifact-Link Read-vs-Real-Change Commit Obligation

## 1. `src/sase/artifact_cli/read.py` — `handle_read` / `_record_read_link`

**Purpose:** Implements `sase artifact read <ref> <reason>`, prints an artifact body, and records an audited read.

**`handle_read(args: argparse.Namespace) -> int`** (lines 87–146): resolves the reference, calls `_prepare_body`, `_record_audit_and_consumption`, then conditionally `_record_read_link`, then prints.

Trigger chain for `_record_read_link`:
```python
def _should_record_link() -> bool:
    return bool(_in_agent_run() and discover_agent_identity())

def _in_agent_run() -> bool:
    return bool(os.environ.get("SASE_AGENT"))
```
`recorded_link` is computed once per body-preparation path (`_prepare_body`, lines 149–173) and then, in `handle_read`:
```python
if recorded_link:
    try:
        _record_read_link(result, reason=str(args.reason))
    except Exception as exc:
        print(f"Error: could not record read link: {exc}", file=sys.stderr)
else:
    print(_READ_NOT_RECORDED, file=sys.stderr)
```
So **every read inside an agent run with a discoverable identity** (`SASE_AGENT` env set + `discover_agent_identity()` non-`None`) triggers `_record_read_link` — this is unconditional on whether the run has made any other file changes.

**`_record_read_link(result: ResolvedArtifactReference, *, reason: str) -> None`** (lines 263–288) — the load-bearing function:
```python
def _record_read_link(result: ResolvedArtifactReference, *, reason: str) -> None:
    identity = discover_agent_identity()
    if identity is None:
        return
    store = resolve_artifact_link_store()
    target = canonicalize_artifact_link_ref(
        render_artifact_ref(replace(result.parsed, fragment=None))
    )
    source = f"agent:{identity.name}"
    row = {
        "schema_version": ARTIFACT_LINK_ROW_SCHEMA_VERSION,
        "source_ref": source,
        "relation": "read",
        "target_ref": target,
        "description": reason,
        "origin": "read",
        "created_by": identity.name,
        "created_at": datetime.now(tz=UTC).strftime("%Y-%m-%dT%H:%M:%SZ"),
        "uses": 1,
    }
    outcome = store.upsert_row(row)
    append_artifact_link_outbox_entry(
        project_key=store.project_key,
        agent_name=identity.name,
        row=dict(outcome.get("row") or row),
    )
```
This **immediately writes to disk twice**: `store.upsert_row(row)` writes versioned sidecar JSON (`links/**/*.json`) via `ArtifactLinkStore` (see §"ArtifactLinkStore" below), then `append_artifact_link_outbox_entry(...)` *also* appends the row to a durable per-project JSONL outbox at `~/.sase/projects/<project_key>/artifact-link-outbox.jsonl` — this second call was added later (see §"Commit 0a1aef7d8" / outbox history below) and was clearly *meant* to replace the immediate write, but the immediate `upsert_row` call was left in place, so both paths run redundantly today.

**Identity available at read time:** `AgentIdentity` (from `sase/agent/identity.py`):
```python
@dataclass(frozen=True)
class AgentIdentity:
    name: str
    source: AgentIdentitySource  # "SASE_AGENT_NAME" | "agent_meta" | "interactive"
    artifacts_dir: str | None = None
```
`discover_agent_identity(env=None)` resolves from `SASE_AGENT_NAME` env var, falling back to `agent_meta.json` under `SASE_ARTIFACTS_DIR`. No run-id/turn-nonce is captured here — only `identity.name` (used as `created_by`/`source_ref`) and `store.project_key`.

Row shape (v2 schema, `ARTIFACT_LINK_ROW_SCHEMA_VERSION = 2` from `src/sase/sdd/_artifact_link_store_support.py`): `schema_version, source_ref, relation, target_ref, description, origin, created_by, created_at, uses`. No run-id field exists on the row itself — only `agent_name` on the *outbox entry* wrapper (see §7).

---

## 2. `src/sase/llm_provider/commit_finalizer_state/__init__.py` — `collect_dirty_state`

**Purpose:** Aggregate every "dirty" repository (uncommitted changes) visible to the finalizer.

```python
def collect_dirty_state(
    project_dir: str,
    *,
    artifact_root: Path | None = None,
) -> DirtyState:
```
Flow: builds a `main` `DirtyRepo` from `build_commit_details(project_dir)` (main checkout), then gathers `sibling`, `external` (opened linked/external repos, via `sase.linked_repos.opened_linked_repo_names`/`opened_external_repo_records`), and `sdd` repos (`_dirty_sdd_store_repos` + `_dirty_agents_prompt_archive_repo`, from `_dirty_repos.py`). **`_dirty_sdd_store_repos`/`dirty_sdd_store_repos(project_dir)`** (in `_dirty_repos.py`) is exactly the place where artifact-link sidecar dirt (`links/**/*.json` under the SDD store/sidecar repo) surfaces: it runs `git_changed_files(str(repo_root))` on every SDD sidecar/store repo and returns a `DirtyRepo(kind="sdd", ...)` whenever any file (including a link-index JSON written by `_record_read_link`) is dirty there. This is **the mechanism by which a bare read becomes "dirty state."**

All repos are deduped (`_dedupe_dirty_repos_by_path`, kind-priority `main > sdd > external > sibling`), then:
```python
repos, pre_existing_repos = _exclude_pre_existing_baseline(
    repos, load_dirty_baseline(artifact_root)
)
```
**"Unchanged baseline fingerprints" subtraction** (`_exclude_pre_existing_baseline`, lines 149–189): for each repo, `split_pre_existing_changed_files(repo.path, changed_files, baseline_fingerprints)` splits changed paths into `still` (kept) vs `pre_existing` (excluded) using **content-hash + git-status-code fingerprints** captured at run start (`finalizer_baseline.json`, written by `capture_dirty_baseline`/`capture_opened_repo_dirty_baseline` in `commit_finalizer_baseline.py`). A path is only excluded as "pre-existing" if *both* its status code and blob hash still match the baseline snapshot — i.e. dirt this run didn't touch at all. **Link-index dirt created by a read this run is NOT part of the baseline**, so it is never excluded by this mechanism; it always counts as "this run's dirt."

Returns:
```python
@dataclass(frozen=True)
class DirtyState:
    project_dir: str
    repos: tuple[DirtyRepo, ...]
    details: str
    @property
    def is_clean(self) -> bool: return not self.repos

@dataclass(frozen=True)
class DirtyRepo:
    name: str
    path: str
    changed_files: tuple[str, ...]
    kind: Literal["main", "sibling", "external", "sdd"]
```
`DIRTY_REPO_KIND_PRIORITY = {"main": 0, "sdd": 1, "external": 2, "sibling": 3}` (in `commit_finalizer_types.py`).

Connects to: `declaration.py::_build_live_context` (consumes `DirtyState` to build obligations), `reconciliation.py::prepare_commit_dirty_state` (calls `collect_dirty_state` repeatedly before/after each machine auto-commit pass, including the artifact-link auto-commit).

---

## 3. `src/sase/finalizers/declaration.py` — `_build_live_context`

```python
def _build_live_context(
    root: Path,
    *,
    command: str,
    plan: FinalizerPlanWire | None = None,
) -> _LiveFinalizerContext:
    plan = plan or load_finalizer_plan(root)
    run_id, agent_id, turn_nonce = _run_identity(root, command)
    dirty_state = _collect_dirty_state(root)   # -> collect_dirty_state(project_dir, artifact_root=root)
    requirements, obligations = _build_context_requirements(plan, dirty_state)
    host_records = _host_repository_records(dirty_state)
    context = FinalizerContextWire(..., requirements=requirements, obligations=obligations)
    context_digest = validate_finalizer_context(plan, context)   # Rust core call
    ...
```
`_build_context_requirements` is imported from `sase.finalizers.declaration_store` as `build_context_requirements` (see §declaration_store.py detail below): for every plan entry whose `provider_ref == "builtin@commit"`, it builds one `FinalizerObligationWire(kind="repository", ...)` **per `DirtyRepo` in `dirty_state.repos`**, unconditionally:
```python
def build_context_requirements(plan, dirty_state):
    ...
    for entry in plan.entries:
        if entry.provider_ref == "builtin@commit":
            repository_obligations = [_repository_obligation(repo) for repo in dirty_state.repos]
            obligations.extend(repository_obligations)
            trigger = "dirty_repository" if repository_obligations else "not_triggered"
            requirements.append(FinalizerPayloadRequirementWire(
                instance_id=entry.instance_id,
                trigger=trigger,
                submission_required=bool(repository_obligations),
                ...
            ))
```
and:
```python
def repository_obligation_id(repo: DirtyRepo) -> str:  # sha256 of {kind,name,path}
def _repository_obligation(repo: DirtyRepo) -> FinalizerObligationWire:
    ...
    return FinalizerObligationWire(obligation_id=repo_id, kind="repository",
                                    display_name=..., paths=paths, digest=state_digest)
```
This is **exactly** how "dirty state → repository obligation" happens: *any* nonempty `DirtyState.repos` (including a `kind="sdd"` repo whose only dirt is a link-index JSON from a bare read) forces `submission_required=True` for the `builtin@commit` finalizer instance, which is what makes `sase final submit` demand a commit declaration even for read-only runs. `publish_final_context`/`submit_final_manifest` (same file) build/validate/accept this context through `validate_finalizer_context`/`validate_finalizer_submission` (Rust core calls, `sase.core.finalizer_facade`).

---

## 4. `src/sase/finalizers/reconciliation.py` — `prepare_commit_dirty_state`, `_auto_commit_artifact_link_indexes_if_possible`, `reject_unproven_reconciliation_transition`

```python
@dataclass(frozen=True)
class PreparedCommitDirtyState:
    dirty_state: DirtyState
    done_plan_auto_committed: bool = False
    sdd_prompt_qa_auto_committed: bool = False
    sdd_bead_projection_auto_committed: bool = False
    sdd_store_auto_committed: bool = False
    artifact_links_auto_committed: bool = False
    bead_publication_error: str | None = None
    artifact_link_publication_error: str | None = None
    dirty_state_before: DirtyState | None = None
    fingerprints_before: Mapping[str, Mapping[str, tuple[str, str | None]]] | None = None

def prepare_commit_dirty_state(project_dir: str, artifacts: Path | None) -> PreparedCommitDirtyState:
```
Sequence inside `prepare_commit_dirty_state`: snapshot `dirty_before = collect_dirty_state(...)` and its fingerprints → auto-commit bead reprojection → auto-commit separate SDD store → rescan → auto-commit external SDD prompt Q&A → auto-commit "done" plan status → **`_auto_commit_artifact_link_indexes_if_possible`** (last step) → return.

```python
def _auto_commit_artifact_link_indexes_if_possible(
    project_dir: str,
    dirty_state: DirtyState,
    artifact_root: Path | None,
) -> tuple[DirtyState, bool, str | None]:
    indexes, lock_only_roots = _artifact_link_dirty_candidates(dirty_state)
    if not indexes and not lock_only_roots:
        return dirty_state, False, None
    ...
    result = commit_artifact_link_indexes(
        indexes, store=store,
        repo_roots=tuple(Path(repo.path) for repo in dirty_state.repos),
        artifacts_dir=artifact_root,
        extra_paths_by_root=extra or None,
        verify_publication=True,
    )
    ...
    if not result.committed and not result.publication_error:
        return dirty_state, False, None
    refreshed = collect_dirty_state(project_dir, artifact_root=artifact_root)
    return refreshed, result.committed, result.publication_error
```
`_artifact_link_dirty_candidates` (lines 433–459) scans every `DirtyRepo.changed_files`, classifying each path via `classify_artifact_link_repo_file` (from `sase.sdd._artifact_link_files`) into `INDEX` (a `links/**/*.json` sidecar file — collected for commit) or `LOCK` (a `.lock` sentinel — never staged, but its presence with no index dirt still forces a "lock_only_roots" pass, which just installs `.gitignore`). **This is the gate that currently decides "should we auto-commit artifact-link dirt": it is purely file-classification based (is *any* dirty file in the repo an artifact-link index/lock), with NO check for whether the run has any *other, non-link* real change.**

`reject_unproven_reconciliation_transition(before, after, *, fingerprints_before, artifacts, ledger_before, instance_id, attempt, ledger, invoke_result) -> None`: fails closed ("dirty work vanished without an attributable commit" / "stale_commit_declaration") if a repo's dirty paths changed (added/removed/fingerprint-mismatched) between the pre-reconciliation snapshot and the post-reconciliation snapshot without a matching new commit marker. This is the safety net ensuring the auto-commit passes (including artifact-links) either fully explain a transition or the finalizer fails rather than silently discarding dirt.

`clean_result_reason(...)` classifies a "clean" finalizer outcome, including `"artifact_links"` in the auto-committed reason list — i.e. a run whose *only* dirt was link-index JSON currently reports success as `auto_committed_artifact_links`, proving today's system treats a pure-read run as having made an "auto-commit."

---

## 5. `src/sase/finalizers/commit.py` — sequencing

`execute_commit_finalizer(...)` is the entry point invoked for the `builtin@commit` finalizer instance. Order:
1. `ledger_before_reconciliation = _load_commit_results(artifacts)`.
2. `state = prepare_commit_dirty_state(project_dir, artifacts)` — **this runs all machine-owned auto-commits, including the artifact-link auto-commit, BEFORE the accepted declaration is even loaded.**
3. `dirty_before_decisions = state.dirty_state`; `dirty_before_reconciliation = pre_reconciliation_dirty_state(state)` (== `state.dirty_state_before`, i.e. the pre-auto-commit snapshot).
4. Load the accepted commit declaration (`_load_accepted_commit_declaration`). If missing **and** `state.dirty_state.is_clean` (post-auto-commit), it short-circuits: calls `_raise_if_unpublished_machine_state` then returns a success result with no attempts — i.e. a purely link-index-dirty run that got auto-committed by step 2 can succeed the `builtin@commit` finalizer with *zero* declared obligations from the model, but it still created a real git commit (`chore(artifact-links): persist link indexes`) as a side effect of `prepare_commit_dirty_state`.
5. Otherwise: obligations from `accepted_context.obligations` are matched against `dirty_before_reconciliation.repos` (`_reject_stale_repository_obligation` per repo), `reject_unproven_reconciliation_transition(dirty_before_reconciliation, state.dirty_state, ...)` is called to prove the auto-commit passes accounted for everything, then dispatch proceeds to `sase stitch create` for remaining declared repos.

So reconciliation (and hence the artifact-link auto-commit) runs **before** any check of whether the model declared/accepted anything — it is unconditional machine housekeeping that runs on every finalizer invocation, gated only by `_artifact_link_dirty_candidates` finding index/lock dirt.

---

## 6. `src/sase/sdd/_artifact_link_commit.py` — `commit_artifact_link_indexes`

```python
ARTIFACT_LINK_COMMIT_MESSAGE = "chore(artifact-links): persist link indexes"
ARTIFACT_LINK_COMMIT_TYPE = "sdd"
ARTIFACT_LINK_FILE_HOOK_CAUSE = "artifact_links"

def commit_artifact_link_indexes(
    index_paths: Iterable[Path],
    *,
    store: SddStore | None = None,
    repo_roots: Sequence[Path] = (),
    artifacts_dir: str | Path | None = None,
    already_locked: bool = False,
    mutation_origin: str = "user",
    push_after_commit: bool | Literal["async"] | None = None,
    verify_publication: bool = False,
    extra_paths_by_root: dict[Path, list[Path]] | None = None,
    message: str = ARTIFACT_LINK_COMMIT_MESSAGE,
) -> _ArtifactLinkCommitResult:
```
Behavior: groups valid index paths by owning sidecar root (`_group_valid_indexes`, validated via `is_canonical_artifact_link_index[_location]`), and **for each owning root**:
```python
gitignore = ensure_artifact_link_lock_gitignore(root)  # touches .gitignore
unique_indexes = list(dict.fromkeys(indexes))
if gitignore is not None:
    unique_indexes.append(gitignore)
```
So **yes, it does touch `.gitignore`** — `ensure_artifact_link_lock_gitignore` (in `_artifact_link_ignore.py`) appends the rooted pattern `/links/**/*.lock` to each sidecar's `.gitignore` (creating the file if absent) and stages it in the same commit whenever it was created/amended. It then calls `_commit_paths(...)` → `commit_sdd_store_files`/`commit_sdd_files` (from `sase.sdd.files`) with `auto_commit_type="sdd"`, `cause="artifact_links"`, and — critically — `verify_publication=True` from the reconciliation caller triggers `_publication_error_for_roots` → `_unpushed_sidecar_error`, which actually **pushes** (`push_bead_work_launch`) the sidecar repo if it has a tracking upstream and the new HEAD isn't published yet. So a bare read can, through this path, cause both a local commit *and* a remote push of the sidecar/document repo.

`_ArtifactLinkCommitResult(committed: bool, repo_roots: tuple[Path,...], publication_error: str|None)` — `__bool__` returns `committed`.

`persist_artifact_link_graph_mutation(link_store, *, changed_indexes, beads_changed, artifacts_dir=None, mutation_origin="user")` is the explicit-mutation (`sase artifact link`/`sase artifact rm`, not read) counterpart — raises `ArtifactLinkPersistError` on publication failure rather than swallowing it, unlike the finalizer's best-effort auto-commit path.

---

## 7. `src/sase/sdd/artifact_link_outbox.py` — `drain_artifact_link_outbox`

**Purpose:** A machine-local, durable JSONL replay queue for read-link rows, intended (per its module docstring "Machine-local replay log for artifact-link read rows") to decouple *recording* a read from *publishing* it.

Storage: `~/.sase/projects/<project_key>/artifact-link-outbox.jsonl` (`_artifact_link_outbox_path`), plus a sibling `artifact-link-outbox-dropped.jsonl` audit trail for stale/dropped entries. Entries are appended under an `fcntl.LOCK_EX` file lock (`append_artifact_link_outbox_entry`) and read under `LOCK_SH`.

```python
@dataclass(frozen=True, slots=True)
class _ArtifactLinkOutboxEntry:
    schema_version: int
    id: str
    created_at: float
    project_key: str
    agent_name: str
    row: dict[str, Any]
    @property
    def logical_key(self) -> tuple[str, str, str]:  # (source_ref, relation, target_ref)
```
Run/agent identity fields on an outbox entry: only `agent_name` (no run_id/turn_nonce) plus `project_key`.

```python
def drain_artifact_link_outbox(
    *,
    store: ArtifactLinkStore | None = None,
    agent_name: str | None = None,
    drop_stale_terminal: bool = True,
    push_after_commit: bool | str | None = "async",
) -> _ArtifactLinkOutboxDrainReport:
```
Pipeline: read all entries → `_partition_selected` (only `agent_name`'s entries, if given) → `_partition_stale_terminal` (drop entries whose agent finished terminally >`retention_days` ago and never got published — moved to the dropped-audit file) → **`_partition_publishable`**:
```python
def _partition_publishable(entries):
    for entry in entries:
        if _agent_is_published(entry.agent_name):
            publishable.append(entry)
        else:
            retained.append(entry)
    ...

_PUBLISHED_AGENT_STATUSES = frozenset({"exact", "drifted", "vcs_backed"})

def _agent_is_published(agent_name: str) -> bool:
    result = resolve_cli_reference(f"agent:{agent_name}")
    return result.resolution.status in _PUBLISHED_AGENT_STATUSES
```
**This confirms the plan's suspicion exactly: "publishable" today means only "the agent's own hood/summary document resolves to a committed VCS location" — it has nothing to do with whether *this run* made any real file change.** An agent whose hood got published for any reason (even one triggered by something else entirely) makes all its queued read rows "publishable."

→ `_partition_machine_writable_entries` (authorization probe per sidecar root) → `_upsert_publishable_entries` (calls `store.upsert_row` for the *delta* uses only, converging duplicate replays) → `_commit_outbox_indexes` → `commit_artifact_link_indexes(changed_indexes, store=..., repo_roots=..., push_after_commit=..., mutation_origin="machine")` (same function as §6) → on success, `_rewrite_without_ids` atomically rewrites the outbox JSONL to drop drained/dropped ids.

**Caller (only production caller):** `src/sase/workflows/commit/workflow_publication.py::run_agent_publication_step` → `_drain_artifact_link_outbox_for_agent`, called **only when `method in ("create_commit", "create_pull_request")` and `cp.publication_agent` is set**, i.e. only in the `sase stitch create` commit workflow, after a **real primary commit** has succeeded and the "publish_agent_hood" step is running/complete:
```python
_ARTIFACT_LINK_OUTBOX_STEP = "drain_artifact_link_outbox"
...
def _drain_artifact_link_outbox_for_agent(cp, *, checkpoint_save):
    if not cp.publication_agent or _ARTIFACT_LINK_OUTBOX_STEP in cp.completed_steps:
        return
    drain_artifact_link_outbox(agent_name=cp.publication_agent, drop_stale_terminal=False, push_after_commit="async")
```
This is the **one place today where "promote pending reads because a real commit happened" is already wired up** — it is checkpointed (`CommitCheckpoint.completed_steps`) so it only runs once per real commit. The other caller is the maintenance script `sase_chop_artifact_link_backfill.py` (drains with no `agent_name` filter, i.e. drains everything publishable, for backfill/repair purposes).

**Redundancy with the finalizer path:** Because `_record_read_link` still calls `store.upsert_row(row)` directly (§1), the sidecar JSON is *already* dirty before `drain_artifact_link_outbox` ever gets a chance to write it via the delta-upsert in `_upsert_publishable_entries`; the finalizer's `_auto_commit_artifact_link_indexes_if_possible` (§4) races to commit that dirt regardless of whether a real commit will ever happen. In other words: **today there are two independent, redundant persistence paths — the immediate write in `read.py` (which the finalizer auto-commits unconditionally) and the outbox+drain path (which is correctly gated on real-commit/agent-publication, but starts from a delta of zero because the immediate write already did the work).**

---

## `ArtifactLinkStore` — definition, `upsert_row`, row fields

**Definition:** `src/sase/sdd/_artifact_link_store_impl.py`:
```python
@dataclass(frozen=True)
class ArtifactLinkStore(
    ArtifactLinkStoreCoreMixin,
    ArtifactLinkStoreRowsMixin,
    ArtifactLinkStoreSidecarMixin,
    ArtifactLinkStoreAggregateMixin,
    ArtifactLinkStoreProjectedMixin,
    ArtifactLinkStoreBeadRowsMixin,
    ArtifactLinkStoreReconcileMixin,
):
    project_key: str
    sidecar_roots: Mapping[str, Path]
    beads_dir: Path | None = None
    sdd_store: SddStore | None = None

    @classmethod
    def from_sdd_store(cls, store: SddStore, project_key: str) -> ArtifactLinkStore: ...
```
Public facade re-exported from `src/sase/sdd/artifact_link_store.py` (also exports `resolve_artifact_link_store()`, `resolve_machine_artifact_link_store()`, `ARTIFACT_LINK_ROW_SCHEMA_VERSION = 2`, `canonicalize_artifact_link_ref`).

**`upsert_row`** (in `_artifact_link_store_rows.py::ArtifactLinkStoreRowsMixin`, the load-bearing write path):
```python
def upsert_row(self, row: Mapping[str, Any]) -> dict[str, Any]:
    """Write one validated row to sidecar JSON (when owned) and the aggregate."""
    validated = validate_artifact_link_row(row)   # Rust core validation/canonicalization
    outcome = None
    changed_indexes: list[Path] = []
    for ref in (validated["source_ref"], validated["target_ref"]):
        written = self._upsert_sidecar(ref, validated)   # writes links/**/*.json under sase.sdd sidecar
        if written is not None:
            outcome = written
            changed_indexes.extend(written.get("changed_indexes") or ())
    beads_changed = False
    bead_written = self._upsert_bead(validated)
    if bead_written is not None:
        outcome = bead_written
        beads_changed = str(bead_written.get("kind") or "") != "unchanged"
    elif self._is_aggregate_only(validated):
        outcome = self._upsert_aggregate_row(validated)
    rebuilt = self.rebuild_aggregate()
    result = dict(outcome or {"kind": "unchanged", "row": validated, "rows": list(rebuilt.get("rows", []))})
    result["changed_indexes"] = tuple(dict.fromkeys(changed_indexes))
    result["beads_changed"] = beads_changed
    return result
```
This is the **synchronous disk write** — `_upsert_sidecar` (in `ArtifactLinkStoreSidecarMixin`) writes/updates the versioned per-artifact sidecar JSON index file under the artifact's owning sidecar root (`links/**/*.json`), acquiring a `.lock` sentinel file during the write (hence `_artifact_link_dirty_candidates`'s `LOCK`/`INDEX` classification in reconciliation.py). It is called both by `_record_read_link` directly (today, redundantly) and by `_upsert_publishable_entries` in the outbox drain (§7, delta-only).

**Row fields** (validated/canonicalized by Rust core via `validate_artifact_link_row` → `require_rust_binding("artifact_link_validate_row")`): `schema_version` (int, currently 2), `source_ref` (str, e.g. `"agent:<name>"`), `relation` (str slug, e.g. `"read"`), `target_ref` (str, canonical artifact ref), `description` (str, the read "reason"), `origin` (str, e.g. `"read"`), `created_by` (str, agent name), `created_at` (ISO-8601 UTC string), `uses` (int count — read-outbox convergence treats `origin="read"` rows as *cumulative* additive uses across independent reads, while commit-scoped origins converge to a max via `_converge_prompt_ref_uses` in `artifact_link_store.py::upsert_artifact_link_rows`). **No run-id field exists on the row** — only `created_by`/`source_ref` name the agent, not a specific run/turn.

`remove_rows(source_ref, target_ref, *, relation=None) -> ArtifactLinkRemoval` is the deletion counterpart:
```python
@dataclass(frozen=True)
class ArtifactLinkRemoval:
    rows: tuple[dict[str, Any], ...]
    changed_indexes: tuple[Path, ...] = ()
    beads_changed: bool = False
```

---

## Rust/PyO3 binding adapter pattern (`sase.core.rust` + example)

`src/sase/core/rust.py` defines the **only** supported import path into the `sase_core_rs` PyO3 extension:
```python
RUST_EXTENSION_MODULE_NAME = "sase_core_rs"

def require_rust_extension() -> Any:
    return importlib.import_module(RUST_EXTENSION_MODULE_NAME)  # raises ImportError w/ install hint on failure

def require_rust_binding(name: str) -> Any:
    """Return sase_core_rs.<name> or raise with operation-specific text."""
```
Callers never `import sase_core_rs` directly; they call `require_rust_binding("<fn_name>")(...)`. Concrete adapter example — **`src/sase/core/finalizer_facade.py`** wraps the finalizer policy bindings this whole feature depends on:
```python
def validate_finalizer_context(plan, context) -> str:
    binding = require_rust_binding("validate_finalizer_context")
    return str(binding(finalizer_wire_to_json_dict(plan), finalizer_wire_to_json_dict(context)))

def validate_finalizer_submission(plan, context, submission) -> FinalizerSubmissionValidationWire:
    binding = require_rust_binding("validate_finalizer_submission")
    payload = binding(finalizer_wire_to_json_dict(plan), finalizer_wire_to_json_dict(context), finalizer_wire_to_json_dict(submission))
    return finalizer_submission_validation_from_dict(dict(payload))
```
i.e. the pattern is: (1) convert dataclass "wire" types to plain JSON dicts (`finalizer_wire_to_json_dict`), (2) call the named Rust binding with those dicts, (3) convert the JSON result back into a typed dataclass (`finalizer_*_from_dict`). The finalizer obligation/requirement/context digesting (`finalizer_json_digest`, `finalizer_context_digest`, `validate_finalizer_plan`, `aggregate_finalizer_outcomes`) all follow this same shape — these are the Rust-side policy authorities that `declaration.py`/`declaration_store.py` call to decide whether a context is valid and whether a submission satisfies it. **A cross-cutting change to "what counts as an obligation" (e.g. distinguishing pending-vs-promoted artifact-link dirt) would need to either (a) stay entirely on the Python side by keeping such dirt out of `DirtyState`/`collect_dirty_state` before it ever reaches `build_context_requirements`, or (b) extend the Rust `FinalizerObligationWire`/validation contract** — (a) is far less invasive given everything upstream of `_build_context_requirements` is pure Python.

Also relevant: `validate_artifact_link_row`/`upsert_artifact_link_rows` in `_artifact_link_store_support.py`/`artifact_link_store.py` call `require_rust_binding("artifact_link_validate_row")` / `require_rust_binding("artifact_link_upsert_row")` — the row canonicalization/merge logic itself lives in Rust, not Python.

---

## Commit `0a1aef7d8` — origin of the auto-commit-on-read behavior

`0a1aef7d80cd755b3f55ea62ee8aa4e69759daca` — **"feat(artifact-links): persist sidecar indexes on mutate and finalize"** (Aug 21 2026, `bbugyi200.athena.09s`).

This is the commit that introduced `auto_commit_artifact_link_indexes_if_possible` (now `_auto_commit_artifact_link_indexes_if_possible`) into `reconciliation.py`, added `_artifact_link_dirty_candidates`/`_porcelain_path`/`_resolve_finalizer_sdd_store`, wired it into `prepare_commit_dirty_state`, renamed `_raise_if_unpublished_bead_state` → `_raise_if_unpublished_machine_state` in `commit.py` to also fail on `artifact_link_publication_error`, and created `src/sase/sdd/_artifact_link_commit.py` (`commit_artifact_link_indexes`, `persist_artifact_link_graph_mutation`, `.gitignore` handling) wholesale (384 new lines). It also extended `ArtifactLinkStore.upsert_row`/`remove_rows` to return `changed_indexes`/`beads_changed` so the commit helper knows which files to stage. **This commit made every dirty `links/**/*.json` file — however it got dirty — an unconditional auto-commit candidate for the `builtin@commit` finalizer.** A later commit, `5d36fef26` ("feat(artifacts): add durable read-link outbox", Aug 25 2026, bead `sase-tw.2`), added the outbox (`artifact_link_outbox.py`, `drain_artifact_link_outbox`, the `workflow_publication.py` wiring) specifically to decouple recording from publishing, but its diff to `read.py` only **appended** `append_artifact_link_outbox_entry(...)` after the pre-existing `store.upsert_row(row)` call rather than replacing it — leaving the immediate-write-on-read path (and thus the `0a1aef7d8` auto-commit trigger) fully intact. This is the precise seam the new plan needs to close.

---

## Summary of the implementation seam

The minimal, well-supported point of intervention is **`_record_read_link` in `read.py`**: stop calling `store.upsert_row(row)` synchronously for a bare read; only call `append_artifact_link_outbox_entry(...)`. Everything downstream (`_dirty_sdd_store_repos` → `collect_dirty_state` → `build_context_requirements` → repository obligations → `_auto_commit_artifact_link_indexes_if_possible`) already stays inert for a repo with no dirty files, so a read-only run would naturally produce zero `DirtyState.repos` and zero obligations without touching any of files 2–6. The remaining gap to close per the stated policy ("promoted... published/committed... only when the run DOES have real changes") is in **`drain_artifact_link_outbox`'s `_partition_publishable`/`_agent_is_published`** (§7): "publishable" needs to become "this run has real attributable changes" (main/sibling/external/sdd-document dirt unrelated to link-index bookkeeping) rather than "the agent's own hood document happens to be resolvable in git" — and the natural place to invoke a corrected drain is still `workflow_publication.py::run_agent_publication_step`, which already only fires after a genuine `create_commit`/`create_pull_request` succeeded, i.e. already encodes "this run had real changes it just committed." The finalizer-side auto-commit in `reconciliation.py`/`commit.py` (`_auto_commit_artifact_link_indexes_if_possible`) is the piece that currently *forces* an obligation purely from read dirt and would become unreachable for pure-read runs once `read.py` stops writing synchronously — but it should be double-checked/kept as a defensive backstop only for cases where `dirty_state.repos` already contains a non-link real change (so link-index dirt sitting alongside genuine edits still gets swept into the same commit as before).

Good progress — the first research agent (Python finalization path) reported back with a detailed analysis. I'm still waiting on the other two (publication path and Rust core). Let me check final-declaration status since nothing has changed yet.

Now the second test file:

First research report is in — confirms the exact seam: `_record_read_link` in `read.py` synchronously writes sidecar JSON on every read, which `collect_dirty_state` picks up unconditionally, forcing a repository obligation and an unconditional auto-commit in `reconciliation.py`. Still waiting on the publication-path and Rust-core reports before I start implementing.

# Research Report: sase-core Eligibility Contract Implementation Reference

Repo root: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/sase/repos/linked/sase-core`
Consumer repo root: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13`

## 1. `crates/sase_core/src/finalizer/`

Module doc (mod.rs, line 1-6):
> "Shared finalizer protocol wires and deterministic domain rules. The host owns filesystem inspection, subprocess execution, and recovery turns. This module owns the frontend-neutral contract: versioned wire shapes, selector replay, dependency ordering, digest binding, submission coverage, and aggregate outcome classification."

This is architecturally the closest existing analog to the eligibility contract you're adding: a pure, host-agnostic decision/validation layer that the host feeds facts into and gets a verdict back.

### `finalizer/wire.rs` — the versioned data contract

Purpose: every wire struct/enum for the finalizer protocol, plus size/length constants. This is the file to mirror for a new eligibility wire module.

```rust
pub const FINALIZER_WIRE_SCHEMA_VERSION: u64 = 2;

pub const FINALIZER_INSTANCE_ID_MAX_LEN: usize = 64;
pub const FINALIZER_PROVIDER_REF_MAX_LEN: usize = 160;
pub const FINALIZER_PROVENANCE_MAX_LEN: usize = 160;
pub const FINALIZER_TEXT_MAX_CHARS: usize = 4_096;
pub const FINALIZER_LIST_MAX_LEN: usize = 128;
pub const FINALIZER_PAYLOAD_MAX_BYTES: usize = 256 * 1024;
pub const FINALIZER_ATTEMPT_MAX_LEN: usize = 32;
pub const FINALIZER_DIAGNOSTIC_MAX_LEN: usize = 64;
```

Run identity lives directly on the context and submission envelope:

```rust
#[derive(Debug, Clone, PartialEq, Eq, Serialize, Deserialize)]
#[serde(deny_unknown_fields)]
pub struct FinalizerContextWire {
    pub schema_version: u64,
    pub run_id: String,
    pub agent_id: String,
    pub turn_nonce: String,
    pub plan_digest: String,
    #[serde(default)]
    pub requirements: Vec<FinalizerPayloadRequirementWire>,
    #[serde(default)]
    pub obligations: Vec<FinalizerObligationWire>,
    #[serde(default, skip_serializing_if = "Option::is_none")]
    pub context_digest: Option<String>,
}

#[derive(Debug, Clone, PartialEq, Serialize, Deserialize)]
#[serde(deny_unknown_fields)]
pub struct FinalizerSubmissionEnvelopeWire {
    pub schema_version: u64,
    pub run_id: String,
    pub agent_id: String,
    pub turn_nonce: String,
    pub plan_digest: String,
    pub context_digest: String,
    #[serde(default)]
    pub payloads: Vec<FinalizerSubmissionPayloadWire>,
}
```

`(run_id, agent_id, turn_nonce)` is the identity triple the crate already uses to bind a submission to one specific run — `submission.rs` rejects a submission whose triple doesn't match the context exactly ("stale" errors). This is the closest precedent for "attributable to that specific run's stable identity."

Obligations model dirty-state accounting per repository (directly analogous to what you'd need for "real, host-verified file changes ... in the primary repo, an opened linked/external repo, or an artifact document repo"):

```rust
#[derive(Debug, Clone, PartialEq, Eq, Serialize, Deserialize)]
#[serde(deny_unknown_fields)]
pub struct FinalizerObligationWire {
    pub obligation_id: String,
    pub kind: String,
    #[serde(default, skip_serializing_if = "Option::is_none")]
    pub display_name: Option<String>,
    #[serde(default, skip_serializing_if = "Vec::is_empty")]
    pub paths: Vec<String>,
    #[serde(default, skip_serializing_if = "Option::is_none")]
    pub digest: Option<String>,
}
```

The test fixture in `submission.rs` shows `obligation_id: "repo:primary"`, `kind: "repository"`, `paths: ["."]` — i.e. host-supplied evidence that a given repo has dirty/attributable state, which is exactly the "primary repo / opened linked repo / artifact doc repo" shape you'd need, just generalized. And `FinalizerTriggerKindWire::DirtyRepository` is an existing named trigger:

```rust
#[derive(Debug, Clone, Copy, PartialEq, Eq, Serialize, Deserialize)]
#[serde(rename_all = "snake_case")]
pub enum FinalizerTriggerKindWire {
    NotTriggered,
    Always,
    DirtyRepository,
    ProviderRequested,
}
```

Deferral reasons are a closed enum (note the doc comment on the exhaustiveness contract):

```rust
/// Closed set of reasons a repository obligation may be deferred instead of
/// committed. Every member describes the tree; none expresses "not asked".
#[derive(Debug, Clone, Copy, PartialEq, Eq, Serialize, Deserialize)]
#[serde(rename_all = "snake_case")]
pub enum FinalizerDeferralReasonWire {
    ProtectedPaths,
    ForeignWork,
    UnsafeContent,
    BelongsToAnotherTurn,
}
```

`BelongsToAnotherTurn` is precisely "some agent in the family got published but not this run" — i.e. the failure mode your eligibility contract needs to distinguish. Outcome/status enums and per-instance result shape:

```rust
#[derive(Debug, Clone, Copy, PartialEq, Eq, Serialize, Deserialize)]
#[serde(rename_all = "snake_case")]
pub enum FinalizerInstanceStatusWire {
    Pending, Skipped, Success, Refused, Deferred, Failed,
}

#[derive(Debug, Clone, Copy, PartialEq, Eq, Serialize, Deserialize)]
#[serde(rename_all = "snake_case")]
pub enum FinalizerAggregateStatusWire {
    Pending, Success, Refused, Deferred, Failed,
}

#[derive(Debug, Clone, PartialEq, Eq, Serialize, Deserialize)]
#[serde(deny_unknown_fields)]
pub struct FinalizerInstanceResultWire {
    pub instance_id: String,
    pub status: FinalizerInstanceStatusWire,
    #[serde(default)]
    pub attempts: Vec<FinalizerAttemptWire>,
    #[serde(default, skip_serializing_if = "Option::is_none")]
    pub refusal_reason: Option<String>,
    #[serde(default, skip_serializing_if = "Option::is_none")]
    pub deferral: Option<FinalizerDeferralWire>,
    #[serde(default, skip_serializing_if = "Vec::is_empty")]
    pub evidence: Vec<FinalizerOutcomeEvidenceWire>,
    #[serde(default, skip_serializing_if = "Vec::is_empty")]
    pub diagnostics: Vec<FinalizerDiagnosticWire>,
}
```

"Commit evidence" is modeled generically as `FinalizerOutcomeEvidenceWire { kind: String, value: String }` — a free-form kind/value pair attached to a result, not a typed commit-sha/repo struct. If your eligibility contract needs typed evidence (e.g. repo path + commit sha + change counts), that's new territory, not reused from here.

**Versioning convention** (answers "how does schema versioning work"): every top-level wire struct carries `schema_version: u64` as its first field. A single crate-wide constant (`FINALIZER_WIRE_SCHEMA_VERSION`) is bumped on breaking change, and `validate_schema()` (in `selection.rs`) does an exact-match check — there is no multi-version compatibility shim:

```rust
pub(crate) fn validate_schema(actual: u64, what: &str) -> Result<(), FinalizerError> {
    if actual == FINALIZER_WIRE_SCHEMA_VERSION {
        Ok(())
    } else {
        Err(FinalizerError::validation(format!(
            "unsupported finalizer {what} schema_version {actual}; expected {FINALIZER_WIRE_SCHEMA_VERSION}"
        )))
    }
}
```

Additive, backward-compatible fields within the *same* schema version instead use `#[serde(default = "fn")]`, e.g.:

```rust
#[serde(deny_unknown_fields)]
pub struct FinalizerInstancePolicyWire {
    #[serde(default = "default_max_attempts")]
    pub max_attempts: u32,
    #[serde(default = "default_refusal_policy")]
    pub refusal: FinalizerRefusalPolicyWire,
}
```

Every struct also has `#[serde(deny_unknown_fields)]` (strict rejection of unrecognized keys) and enums are `#[serde(rename_all = "snake_case")]` closed sets (unknown variants are rejected by serde itself — see the `serde_rejects_unknown_statuses` test). This is the pattern a new eligibility wire module should follow exactly: one crate-local `..._WIRE_SCHEMA_VERSION` constant, `schema_version` as the first field of every top-level struct, `deny_unknown_fields`, closed snake_case enums, and `validate_schema()`-style hard-cutover checks (no migration code — a schema bump is a breaking wire change, and callers on both sides bump together).

### `finalizer/mod.rs`

Purpose: module wiring, error type, re-exports. Key error type:

```rust
#[derive(Debug, Error, Clone, PartialEq, Eq)]
pub enum FinalizerError {
    #[error("{0}")]
    Validation(String),
}
impl FinalizerError {
    pub(crate) fn validation(message: impl Into<String>) -> Self {
        Self::Validation(message.into())
    }
}
```

Every fallible finalizer function returns `Result<T, FinalizerError>`. A new eligibility module should define its own analogous error enum (mirroring `ArtifactLinkError`'s `kind`+`message` shape or `FinalizerError`'s single-variant shape — see comparison below) rather than reusing `FinalizerError` cross-module.

### `finalizer/selection.rs` — plan resolution / validation / digesting

Purpose: turns a `FinalizerPlanInputWire` (instances + defaults + required + selector ops) into a deterministic, dependency-ordered `FinalizerPlanWire`, and validates/digests/authenticates it. Key public functions:

```rust
pub fn validate_finalizer_provider_spec(spec: &FinalizerProviderSpecWire) -> Result<(), FinalizerError>
pub fn finalizer_provider_spec_digest(spec: &FinalizerProviderSpecWire) -> Result<String, FinalizerError>
pub fn validate_finalizer_instance_spec(spec: &FinalizerInstanceSpecWire) -> Result<(), FinalizerError>
pub fn finalizer_instance_spec_digest(spec: &FinalizerInstanceSpecWire) -> Result<String, FinalizerError>
pub fn resolve_finalizer_plan(input: &FinalizerPlanInputWire) -> Result<FinalizerPlanWire, FinalizerError>
pub fn finalizer_plan_digest(plan: &FinalizerPlanWire) -> Result<String, FinalizerError>
pub fn validate_finalizer_plan(plan: &FinalizerPlanWire) -> Result<String, FinalizerError>
pub fn authenticate_finalizer_plan(plan: &FinalizerPlanWire, expected_digest: &str) -> Result<String, FinalizerError>
```

Also exposes shared low-level validators reused by `outcome.rs` and `submission.rs`: `validate_instance_id`, `validate_provider_ref`, `validate_digest`, `validate_optional_digest`, `validate_list_len`, `validate_required_text`, `validate_optional_bounded_text` (all `pub(crate)`). A new eligibility module could either duplicate small validators like these locally or, if truly shared, promote them — the current crate keeps such helpers module-private and duplicates trivially rather than building a shared validation utility crate, so follow that convention (keep new eligibility validators `pub(crate)` inside the new module).

`authenticate_finalizer_plan` is the "bind an untrusted client-echoed value back to its authoritative digest" pattern — directly reusable as a template for authenticating an eligibility decision that gets echoed back by a caller.

### `finalizer/digest.rs` — canonical digesting

Purpose: canonical (recursively key-sorted) JSON serialization + sha256, used everywhere a digest needs to be reproducible regardless of field order.

```rust
pub fn canonical_json_bytes(value: &Value) -> Result<Vec<u8>, FinalizerError>
pub fn canonical_json_sha256(value: &Value) -> Result<String, FinalizerError>
pub fn finalizer_digest_json_value(value: &Value) -> Result<String, FinalizerError>
pub fn finalizer_digest_serializable<T: Serialize>(value: &T) -> Result<String, FinalizerError>
```

If a new eligibility module needs a digest (e.g. to bind an eligibility verdict to the exact evidence it was computed from), this is the function to call, not a hand-rolled hasher — but note it's scoped inside `finalizer` and returns `FinalizerError`. A new module would either write its own tiny copy (a ~10-line function, consistent with the "small modules don't share utility crates" pattern already observed) or take a `serde_json::Value` in/out and do its own error wrapping.

### `finalizer/outcome.rs` — aggregate outcome / attempt-ledger policy

Purpose: validates a `Vec<FinalizerInstanceResultWire>` and aggregates it into one terminal `FinalizerAggregateResultWire`, with strict invariants (unique/increasing 1-based attempt numbers, terminal attempt status must match instance status, refused requires `refusal_reason`, deferred requires `deferral`).

```rust
pub fn validate_finalizer_instance_results(results: &[FinalizerInstanceResultWire]) -> Result<(), FinalizerError>
pub fn aggregate_finalizer_outcomes(results: Vec<FinalizerInstanceResultWire>) -> Result<FinalizerAggregateResultWire, FinalizerError>
```

Aggregate precedence is fixed and tested: `Failed > Refused > Pending > Deferred > Success` (see `aggregate_failure_precedence_is_stable`, `deferred_ranks_below_pending_and_refused_but_above_success`). This precedence-ladder pattern (worst status wins, with `Deferred` demoted to a "warning" diagnostic rather than a hard failure) is a strong template for an eligibility verdict enum if you need to combine per-repo eligibility into one run-level verdict.

### `finalizer/submission.rs` — run-identity binding and context/submission validation

Purpose: validates a `FinalizerContextWire` against a resolved plan (coverage: every plan entry must have exactly one requirement), computes/verifies `context_digest`, and validates a `FinalizerSubmissionEnvelopeWire` against both — this is the file that actually enforces run-identity staleness:

```rust
pub fn validate_finalizer_context(plan: &FinalizerPlanWire, context: &FinalizerContextWire) -> Result<String, FinalizerError>
pub fn finalizer_context_digest(context: &FinalizerContextWire) -> Result<String, FinalizerError>
pub fn validate_finalizer_submission(plan: &FinalizerPlanWire, context: &FinalizerContextWire, submission: &FinalizerSubmissionEnvelopeWire) -> Result<FinalizerSubmissionValidationWire, FinalizerError>
pub fn validate_finalizer_deferral(deferral: &FinalizerDeferralWire) -> Result<(), FinalizerError>
```

The stale-identity check is exactly the "attributable to that specific run's stable identity" pattern you need:

```rust
if submission.run_id != context.run_id {
    return Err(FinalizerError::validation("submission run_id is stale"));
}
if submission.agent_id != context.agent_id {
    return Err(FinalizerError::validation("submission agent_id is stale"));
}
if submission.turn_nonce != context.turn_nonce {
    return Err(FinalizerError::validation("submission turn_nonce is stale"));
}
```

This triple (`run_id`, `agent_id`, `turn_nonce`) plus digest chaining (`plan_digest` → `context_digest` → `submission_digest`) is the crate's existing mechanism for "this artifact belongs to this specific run, not just this agent family" — a new eligibility contract that must check "attributable to that specific run's stable identity (not just some agent in the family got published)" should adopt the same triple (or whatever subset your host already threads through — likely `run_id`/`agent_id` at minimum) as first-class required fields on its request wire, and reject on mismatch the same way, with the same wording style ("`<field>` is stale").

## 2. `crates/sase_core/src/artifact_link/`

Module doc (mod.rs, line 1-2):
> "First-class artifact link graph: row schema, relation registry, managed tables, companion paths, and frontmatter inlet."

**Important scope note**: this module is about the *artifact-link graph* (typed relations like `cites`, `implements`, `produced-by`, `launched` between artifacts — plans, beads, agents, stitches), not directly about run-eligibility bookkeeping. It is the *target* of automatic link-row writes (e.g. `produced-by`/`launched` rows with `origin: Derived`/`Projected`), but it does not itself contain any eligibility, run-identity, or dirty-state logic. If the new eligibility contract's job is "decide whether to let an automatic link-row write happen," it is a **new, separate concern** that would sit upstream of (and be consumed by) this module — most likely as a new sibling module (see recommendation at the end), not as an addition to `artifact_link`'s row/relation types themselves.

### `artifact_link/wire.rs` — link-row schema, canonicalization, upsert/dedup

Purpose: the row type stored in the link graph, its schema version, canonicalization/validation, and upsert-with-dedup semantics.

```rust
pub const ARTIFACT_LINK_ROW_SCHEMA_VERSION: u64 = 2;
const MAX_DESCRIPTION_CHARS: usize = 240;

#[derive(Debug, Clone, PartialEq, Eq, Error)]
#[error("{kind}: {message}")]
pub struct ArtifactLinkError {
    pub kind: String,
    pub message: String,
}
```

Note this error shape differs from `FinalizerError`: it carries a machine-readable `kind` string (`"validation"`, `"reserved"`, `"none"`) in addition to `message`, letting Python callers branch on `err.kind` without string-matching. This is a second precedent for a new module's error type — pick `FinalizerError`'s single-variant-enum style or `ArtifactLinkError`'s `kind`+`message` style depending on whether callers need to branch programmatically on failure category (eligibility refusal reasons plausibly want branching, so `ArtifactLinkError`'s shape, or a closed enum reason like `FinalizerDeferralReasonWire`, is probably the better fit).

The link-row type ("agent id" here is `created_by`, a free-text attribution string, not a structured run identity; there is a `uses` counter but no per-run publish-status field):

```rust
#[derive(Debug, Clone, Copy, PartialEq, Eq, Serialize, Deserialize)]
#[serde(rename_all = "snake_case")]
pub enum ArtifactLinkOriginWire {
    Manual, Migrated, PromptRef, Read, Derived, Projected,
}
impl ArtifactLinkOriginWire {
    pub fn increments_uses(self) -> bool { matches!(self, Self::PromptRef | Self::Read) }
}

#[derive(Debug, Clone, PartialEq, Eq, Serialize, Deserialize)]
pub struct ArtifactLinkRowWire {
    pub schema_version: u64,
    pub source_ref: String,
    pub relation: String,
    pub target_ref: String,
    pub description: String,
    pub origin: ArtifactLinkOriginWire,
    pub created_by: String,
    pub created_at: String,
    #[serde(default = "default_uses")]
    pub uses: u64,
}
```

Note: `ArtifactLinkRowWire` does *not* have `deny_unknown_fields` (unlike every finalizer struct) — worth flagging if you add fields to it, but irrelevant if your eligibility contract is a new, separate wire type.

Dedup key (directed vs. undirected identity for one stored edge):

```rust
#[derive(Debug, Clone, PartialEq, Eq, PartialOrd, Ord, Serialize, Deserialize)]
#[serde(tag = "kind", rename_all = "snake_case")]
pub enum ArtifactLinkDedupKeyWire {
    Directed { source_ref: String, relation: String, target_ref: String },
    Undirected { relation: String, left_ref: String, right_ref: String },
}

#[derive(Debug, Clone, Copy, PartialEq, Eq, Serialize, Deserialize)]
#[serde(rename_all = "snake_case")]
pub enum ArtifactLinkUpsertKindWire { Added, Updated, Unchanged }
```

Key functions:

```rust
pub fn canonicalize_artifact_link_ref(value: &str) -> Result<String, ArtifactLinkError>
pub fn validate_artifact_link_description(description: &str) -> Result<String, ArtifactLinkError>
pub fn validate_artifact_link_row(row: &ArtifactLinkRowWire) -> Result<ArtifactLinkRowWire, ArtifactLinkError>
pub fn artifact_link_dedup_key(row: &ArtifactLinkRowWire) -> Result<ArtifactLinkDedupKeyWire, ArtifactLinkError>
pub fn upsert_artifact_link_row(rows: &mut Vec<ArtifactLinkRowWire>, incoming: ArtifactLinkRowWire) -> Result<ArtifactLinkUpsertWire, ArtifactLinkError>
```

`upsert_artifact_link_row` is the function that would actually *write* an automatic link row once your new eligibility check says "yes, publish this." It has no run-identity or dirty-state gate today — that gate is exactly the gap the new eligibility contract needs to fill, upstream of this call.

### `artifact_link/relation.rs` — closed relation registry

Purpose: the closed v1 relation vocabulary (8 builtins), reserved slugs, inverse-label lookup.

```rust
pub const ARTIFACT_RELATION_WIRE_SCHEMA_VERSION: u64 = 2;
pub const RESERVED_ARTIFACT_RELATION_SLUGS: &[&str] = &["blocks", "depends-on"];

#[derive(Debug, Clone, PartialEq, Eq, Serialize, Deserialize)]
pub struct ArtifactRelationWire {
    pub schema_version: u64,
    pub slug: String,
    pub inverse: String,
    pub directed: bool,
    pub written_by: String,
    pub direction_note: String,
    pub positive_example: String,
    pub negative_example: String,
    pub recommended_source_kinds: Vec<String>,
    pub recommended_target_kinds: Vec<String>,
}
```

`produced-by` (stitch → agent) and `launched` (chop → agent) are `written_by: "projection"` relations — i.e. relations only the system itself writes automatically, never a human/prompt. This is the relation-level analog of "automatic" rows; `written_by` is a free-text hint though, not machine-enforced anywhere in this file — enforcement of "who/what may write this row automatically" is exactly the kind of policy your eligibility contract should own.

```rust
pub fn lookup_artifact_relation(slug: &str) -> Result<ArtifactRelationWire, ArtifactLinkError>
pub fn relation_label_from_perspective(slug: &str, this_is_source: bool) -> Result<String, ArtifactLinkError>
pub fn builtin_artifact_relations() -> Vec<ArtifactRelationWire>
```

### `artifact_link/path.rs` — markdown path resolution

Purpose: resolves the on-disk markdown path for an artifact ref (bead/agent/patch/file/document/chat), including "unpublished" vs. "published" file handling and companion-file collision disambiguation. Key types:

```rust
pub const ARTIFACT_MD_PATH_WIRE_SCHEMA_VERSION: u64 = 1;

#[derive(Debug, Clone, Copy, PartialEq, Eq, Serialize, Deserialize)]
#[serde(rename_all = "snake_case")]
pub enum ArtifactMdPathKindWire { Document, Generated, Companion, Unpublished, None }

pub struct ArtifactMdPathRequestWire {
    pub schema_version: u64,
    pub reference: String,
    pub resolved_path: Option<String>,
    pub published: Option<bool>,   // overrides inference of unpublished file: digest objects
    pub context: ArtifactRefContextWire,
}
```

`published: Option<bool>` here is about whether one *file artifact* has been published to the object store, unrelated to run eligibility. Key functions: `artifact_md_path(request) -> Result<ArtifactMdPathWire, ArtifactLinkError>`, `companion_md_path(asset_path) -> Result<ArtifactCompanionPathWire, ArtifactLinkError>`, `bead_lineage_root`, `bead_page_relpath`. Not directly reusable for eligibility, but shows the crate's convention of taking a `*RequestWire` struct with `schema_version` + a `*ContextWire` sub-struct carrying host-injected environment facts (roots, stores) — a good shape for an eligibility "facts" request (host-verified diff/change facts injected as a context struct).

### `artifact_link/row_resolution.rs` — link-ref → frontend row identity

Purpose: pure lookup-key derivation to resolve an artifact-link ref string (`bead:sase-1`, `agent:worker`, etc.) against candidate frontend "rows" (used by the TUI, not by any commit/publish logic).

```rust
pub const ARTIFACT_ROW_RESOLUTION_WIRE_SCHEMA_VERSION: u64 = 1;

pub struct ArtifactRowIdentityWire { pub pane_id: String, pub parts: Vec<String> }
pub struct ArtifactLinkRefPartsWire { pub schema_version: u64, pub kind: String, pub payload: String }
pub struct ArtifactRowRefQueryWire {
    pub schema_version: u64, pub kind: String, pub payload: String,
    pub project_hint: Option<String>, pub agent_name_candidates: Vec<String>,
}

pub fn parse_artifact_link_ref_parts(value: &str) -> Option<ArtifactLinkRefPartsWire>
pub fn artifact_row_index_keys(identity: &ArtifactRowIdentityWire) -> Vec<Vec<String>>
pub fn artifact_row_ref_lookup_keys(query: &ArtifactRowRefQueryWire) -> Vec<Vec<String>>
pub fn resolve_artifact_row_identity(query: &ArtifactRowRefQueryWire, candidates: &[ArtifactRowIdentityWire]) -> Option<ArtifactRowIdentityWire>
```

Not related to eligibility/publish decisions; included for completeness. This is the file whose `artifact_row_resolution_facade.py` counterpart (see §4) is the cleanest thin-adapter example to copy.

### `artifact_link/inlet.rs` — tolerant frontmatter ingest

Purpose: classify a document's `links:` YAML frontmatter as `Absent` / `Entries` / `Unrecognized` without mutating anything unrecognized.

```rust
pub const ARTIFACT_LINK_INLET_WIRE_SCHEMA_VERSION: u64 = 1;
pub enum ArtifactLinkFrontmatterInletKindWire { Absent, Entries, Unrecognized }
pub struct ArtifactLinkInletEntryWire { #[serde(rename = "ref")] pub artifact_ref: String, pub relation: String, pub description: String }
pub fn parse_artifact_link_frontmatter_inlet(document: &str) -> ArtifactLinkFrontmatterInletWire
```

Not related to eligibility.

### `artifact_link/managed_table.rs` — rendered `## Links` / `## Referenced By` blocks

Purpose: marker-bounded Markdown table rendering/parsing (generic `ManagedTableBlock`, specialized into `links_table_block()` and `referenced_by_table_block()`). Key types: `ManagedTableColumnWire`, `ManagedTableRowWire { values: BTreeMap<String,String>, link_targets: BTreeMap<String,String> }`, `ManagedTableTableWire`, `ManagedTableDocumentWire`. Key functions: `render_managed_table_block`, `parse_managed_table_block`, `upsert_managed_table_block`, plus `links_block_*` / `referenced_by_block_*` thin wrappers. Purely a rendering concern, not eligibility.

### `artifact_link/mod.rs` — re-export surface

Confirms the module's public surface (listed in full at top of this report). No eligibility-adjacent types beyond what's covered above.

### Cross-references between `finalizer` and `artifact_link`

There is **no direct Rust-level coupling** between these two modules today (no `use crate::finalizer::...` inside `artifact_link`, and vice versa — confirmed by grep). They're wired together only from the Python side: `sase/finalizers/reconciliation.py::prepare_commit_dirty_state` (host-side dirty-state capture) feeds into `sase/finalizers/commit.py`, which after a successful commit calls into `sase/sdd/artifact_link_store.py` (`ArtifactLinkStore`) to write `produced-by`/`launched` rows — see `tests/llm_provider/test_commit_finalizer_auto_artifact_links.py` for the current Python-only implementation of exactly the "automatic artifact-link row after a real commit" flow you're formalizing in Rust. That test file (and its neighbors `test_commit_finalizer_external_repos.py`, `test_commit_finalizer_dirty_repo_dedupe.py`, `test_commit_finalizer_shared_clone_audit.py`) is worth reading directly if you need to see today's *ad hoc* Python eligibility logic that the new Rust contract should supersede — it already distinguishes primary repo vs. sidecar/linked repos vs. artifact-doc repos via `DirtyRepo` records from `capture_dirty_baseline`.

## 3. `crates/sase_core_py` — PyO3 bindings

Structure:
```
crates/sase_core_py/
  Cargo.toml               # lib name "sase_core_rs", crate-type ["cdylib","rlib"], pyo3 0.22 abi3-py312
  src/lib.rs                # single ~23,900-line file — ALL bindings live here
  python/sase_core_rs/
    __init__.py              # `from .sase_core_rs import *`
    federation_worker.py, gateway.py
```

There is **one flat `lib.rs`**, no submodules — every new Rust wire type gets: (a) a `use sase_core::{...}` import block (renamed `as core_*`), (b) one `#[pyfunction]` wrapper per core function, (c) one `m.add_function(wrap_pyfunction!(py_*, m)?)?;` line in the `#[pymodule]` init function, and (d) a one-line bullet appended to the giant module-doc bullet list at the top of the file (`//! - \`fn_name(args) -> ret\``). No `#[pyclass]`/`#[pymethods]` are used for these wire types — everything crosses the FFI boundary as plain `dict`/`list`/scalar via `serde_json::Value`, converted with two central helpers:

```rust
fn py_to_json_value(value: &Bound<'_, PyAny>) -> PyResult<JsonValue>      // line 9009
fn json_value_to_py<'py>(py: Python<'py>, value: &JsonValue) -> PyResult<PyObject>  // line 9168
```

**Finalizer example** (`crates/sase_core_py/src/lib.rs`, ~5182-5388): a per-module trio of helpers, then one `#[pyfunction]` per core function:

```rust
fn finalizer_error_to_pyerr(error: FinalizerError) -> PyErr {
    PyValueError::new_err(error.to_string())
}

fn finalizer_wire_from_pydict<T>(dict: &Bound<'_, PyDict>, what: &str) -> PyResult<T>
where T: serde::de::DeserializeOwned,
{
    serde_json::from_value(py_to_json_value(dict.as_any())?).map_err(|error| {
        PyValueError::new_err(format!("{what} is not a valid finalizer wire dict: {error}"))
    })
}

fn finalizer_result_to_py<'py, T>(py: Python<'py>, result: Result<T, FinalizerError>, operation: &str) -> PyResult<PyObject>
where T: serde::Serialize,
{ /* serde_json::to_value + json_value_to_py, error text prefixed with `operation` */ }

#[pyfunction]
#[pyo3(name = "validate_finalizer_submission")]
fn py_validate_finalizer_submission<'py>(
    py: Python<'py>,
    plan: &Bound<'_, PyDict>,
    context: &Bound<'_, PyDict>,
    submission: &Bound<'_, PyDict>,
) -> PyResult<PyObject> {
    let plan: FinalizerPlanWire = finalizer_wire_from_pydict(plan, "plan")?;
    let context: FinalizerContextWire = finalizer_wire_from_pydict(context, "context")?;
    let submission: FinalizerSubmissionEnvelopeWire = finalizer_wire_from_pydict(submission, "submission")?;
    finalizer_result_to_py(py, core_validate_finalizer_submission(&plan, &context, &submission), "submission validation")
}
```

**Artifact-link example** (~5698-5897): same trio pattern with `artifact_link_error_to_pyerr`, plus per-call inline `serde_json::from_value` when a shared `*_from_pydict` helper doesn't exist yet:

```rust
fn artifact_link_error_to_pyerr(error: ArtifactLinkError) -> PyErr {
    PyValueError::new_err(error.to_string())
}

#[pyfunction]
#[pyo3(name = "artifact_link_upsert_row")]
fn py_artifact_link_upsert_row(py: Python<'_>, rows: &Bound<'_, PyList>, row: &Bound<'_, PyDict>) -> PyResult<PyObject> {
    let mut parsed: Vec<ArtifactLinkRowWire> = Vec::with_capacity(rows.len());
    for (index, item) in rows.iter().enumerate() {
        let value = py_to_json_value(&item)?;
        parsed.push(serde_json::from_value(value).map_err(|error| {
            PyValueError::new_err(format!("rows[{index}] is not a valid ArtifactLinkRowWire dict: {error}"))
        })?);
    }
    let incoming: ArtifactLinkRowWire = serde_json::from_value(py_to_json_value(row.as_any())?)
        .map_err(|error| PyValueError::new_err(format!("row is not a valid ArtifactLinkRowWire dict: {error}")))?;
    let outcome = core_upsert_artifact_link_row(&mut parsed, incoming).map_err(artifact_link_error_to_pyerr)?;
    let value = serde_json::json!({ "kind": outcome.kind, "row": outcome.row, "rows": parsed });
    json_value_to_py(py, &value)
}
```

**Module registration** (`#[pymodule]` init fn, ~14590-14663): flat, alphabetical-by-feature `m.add_function(wrap_pyfunction!(py_fn, m)?)?;` calls, e.g.:

```rust
m.add_function(wrap_pyfunction!(py_finalizer_wire_schema_version, m)?)?;
m.add_function(wrap_pyfunction!(py_validate_finalizer_submission, m)?)?;
m.add_function(wrap_pyfunction!(py_aggregate_finalizer_outcomes, m)?)?;
...
m.add_function(wrap_pyfunction!(py_artifact_link_row_schema_version, m)?)?;
m.add_function(wrap_pyfunction!(py_artifact_link_upsert_row, m)?)?;
```

For a new eligibility module you would add: a `use sase_core::{...as core_*}` import block; `eligibility_error_to_pyerr` + `eligibility_wire_from_pydict<T>` + `eligibility_result_to_py<T>` helpers; one `#[pyfunction] #[pyo3(name = "...")] fn py_...` per public core function; the matching `m.add_function(...)` lines; and a doc bullet in the file's top comment block. No `.pyi` stub file exists anywhere in this crate — Python types are purely dynamic (`dict`/`list`), matched on the Python side by hand-written `@dataclass` wire records (see §4).

## 4. Python adapter pattern (`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/`)

The Rust extension is imported strictly, never optionally, via `sase/core/rust.py`:

```python
RUST_EXTENSION_MODULE_NAME = "sase_core_rs"

def require_rust_extension() -> Any:
    try:
        return importlib.import_module(RUST_EXTENSION_MODULE_NAME)
    except ImportError as exc:
        raise ImportError(f"{RUST_EXTENSION_MODULE_NAME} is not importable ...") from exc

def require_rust_binding(name: str) -> Any:
    module = require_rust_extension()
    try:
        return getattr(module, name)
    except AttributeError as exc:
        raise AttributeError(f"... does not expose binding {name!r} ...") from exc
```

Every facade module calls `require_rust_binding("<py_function_name>")` per call site (not cached at import time), then invokes it. Two concrete facade examples:

**`src/sase/core/finalizer_facade.py`** — thin pass-through, dict-in/dataclass-out:
```python
def validate_finalizer_context(
    plan: FinalizerPlanWire | dict[str, Any],
    context: FinalizerContextWire | dict[str, Any],
) -> str:
    binding = require_rust_binding("validate_finalizer_context")
    return str(binding(finalizer_wire_to_json_dict(plan), finalizer_wire_to_json_dict(context)))

def validate_finalizer_submission(
    plan: FinalizerPlanWire | dict[str, Any],
    context: FinalizerContextWire | dict[str, Any],
    submission: FinalizerSubmissionEnvelopeWire | dict[str, Any],
) -> FinalizerSubmissionValidationWire:
    binding = require_rust_binding("validate_finalizer_submission")
    payload = binding(
        finalizer_wire_to_json_dict(plan),
        finalizer_wire_to_json_dict(context),
        finalizer_wire_to_json_dict(submission),
    )
    return finalizer_submission_validation_from_dict(dict(payload))
```
Dataclasses live in a sibling `finalizer_wire.py` (`@dataclass(frozen=True)` mirrors of every `*Wire` Rust struct, e.g. `FinalizerContextWire`, `FinalizerInstanceSpecWire`), with `finalizer_wire_to_json_dict` (uses `dataclasses.asdict`) and `finalizer_*_from_dict` reconstruction helpers.

**`src/sase/core/artifact_row_resolution_facade.py`** — even thinner, no dataclass roundtrip layer, module docstring states the intended division of labor explicitly:
```python
"""Typed Python boundary for artifact-link row resolution.

All matching rules live in :mod:`sase_core_rs`; this module only converts
between :class:`ArtifactEntryTarget` and plain Rust binding dictionaries.
"""

def resolve_artifact_row_target(
    kind: str, payload: str, candidates: Sequence[ArtifactEntryTarget], *,
    project_hint: str | None = None, agent_name_candidates: Sequence[str] = (),
) -> ArtifactEntryTarget | None:
    binding = require_rust_binding("artifact_row_resolve")
    resolved = binding(
        _query_to_wire(kind, payload, project_hint=project_hint, agent_name_candidates=agent_name_candidates),
        [_target_to_wire(candidate) for candidate in candidates],
    )
    if resolved is None:
        return None
    return _target_from_wire(resolved)
```

**Recommended pattern for the new eligibility function**: create `sase/core/eligibility_wire.py` (frozen dataclasses mirroring the new Rust wire structs, `..._to_json_dict`/`..._from_dict` helpers) + `sase/core/eligibility_facade.py` (one function per exposed binding, each doing `require_rust_binding("...")` then a direct call, converting dataclass↔dict at the boundary only) — i.e. copy `finalizer_facade.py` verbatim in shape if the eligibility payloads are nested/structured, or copy `artifact_row_resolution_facade.py`'s even-thinner shape if they're simple enough not to need a wire.py.

## 5. Testing conventions

**Rust unit tests**: every file in `finalizer/` and `artifact_link/` ends with an inline `#[cfg(test)] mod tests { use super::*; ... }` block containing table-style unit tests of the pure functions (see the ~15 tests quoted/summarized above in `outcome.rs`, `selection.rs`, `wire.rs`, `submission.rs`). Style notes: helper builder functions (`fn result(...)`, `fn plan()`, `fn context(...)`, `fn row(...)`) at the top of the `tests` module; assertions frequently check `.unwrap_err().to_string().contains("substring")` rather than matching error variants; round-trip serde tests assert both directions (`serde_json::to_value` then `from_value`) and explicitly test that unknown enum variants are rejected (`serde_rejects_unknown_statuses`, `unknown_deferral_reason_is_rejected`).

**Rust integration/parity tests**: `crates/sase_core/tests/` (a real `tests/` dir, separate from `src/`) holds cross-cutting integration tests, notably `python_wire_parity.rs` — this is the pattern used to guarantee the Rust JSON wire shape matches what Python's dataclass-based wire module produces. It embeds a **captured Python-fixture JSON string** (generated once by running the equivalent Python code and pasting the `sort_keys=True` output, with the exact generating command preserved in a doc comment) and asserts:
```rust
#[test]
fn rust_json_equals_python_fixture() {
    let rust_value: Value = serde_json::to_value(rust_patch()).unwrap();
    let python_value: Value = serde_json::from_str(PYTHON_FIXTURE).unwrap();
    assert_eq!(rust_value, python_value);
}
#[test]
fn python_fixture_deserializes_into_rust_type() {
    let cs: ChangeSpecWire = serde_json::from_str(PYTHON_FIXTURE).unwrap();
    assert_eq!(cs, rust_patch());
}
```
There's no existing `python_wire_parity.rs` fixture specifically for `finalizer` or `artifact_link` today, but this file is the established place to add one if the new eligibility wire needs a Rust⇄Python shape-parity test (the crate doc explicitly frames this as staying Python-toolchain-free at test time: "The Python side is captured as a fixture string rather than invoked at test time").

**`sase_core_py` tests**: no `crates/sase_core_py/tests/` directory and no `#[cfg(test)]` blocks were found in `lib.rs` — the bindings crate itself carries no dedicated Rust tests; `scripts/check.sh`'s `cmd_test` runs `cargo test --workspace`, which does exercise `sase_core_py` insofar as it compiles/links (PyO3 requires a linkable libpython even for `cargo test`, hence the `resolve_pyo3_python` dance in check.sh), but actual binding-correctness testing happens on the **Python side** in the sase_13 consumer repo.

**Python-side PyO3 binding round-trip tests** (in `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/tests/`): e.g. `tests/test_core_finalizer_facade.py` exercises the full facade→binding→facade round trip end-to-end (build wire dataclasses → call every facade function → assert on typed results), tagged `pytestmark = pytest.mark.contract`:
```python
def test_finalizer_facade_resolves_plan_and_validates_submission() -> None:
    provider = FinalizerProviderSpecWire(...)
    validate_finalizer_provider_spec(provider)
    assert len(finalizer_provider_spec_digest(provider)) == 64
    plan = resolve_finalizer_plan(FinalizerPlanInputWire(...))
    assert plan.plan_digest == finalizer_plan_digest(plan)
    assert validate_finalizer_plan(plan) == plan.plan_digest
    ...
```
Other `sase_core_rs`-referencing test files worth knowing about as templates: `tests/test_validate_sase_core_rs_contracts_tool.py`, `tests/test_rust_extension_module_helpers.py`, `tests/_rust_extension_module_helpers.py` (shared helpers for asserting a binding exists / raises the right error shape). For domain-context (not a testing-pattern reference, but relevant background on the *current* ad hoc Python implementation of "automatic artifact-link row after a real commit"), see `tests/llm_provider/test_commit_finalizer_auto_artifact_links.py`.

## 6. `just check` / `scripts/check.sh` commands (sase-core repo)

`justfile` (top level, in sase-core repo root):
```
default: check
check:  ./scripts/check.sh all
fmt:    ./scripts/check.sh fmt
clippy: ./scripts/check.sh clippy
test:   ./scripts/check.sh test
```

`scripts/check.sh` subcommands (`usage()` block):
```
fmt-check   cargo fmt --all -- --check
fmt         cargo fmt --all
clippy      cargo clippy --workspace --all-targets -- -D warnings
test        cargo test --workspace
all         fmt-check, then clippy, then test (default)
```

Notable: `clippy` and `test` both call `resolve_pyo3_python` first, which hunts for a Python ≥3.12 interpreter (`python3.14`/`python3.13`/`python3.12`/`python3`) and exports `PYO3_PYTHON`, because `sase_core_py` pins PyO3's `abi3-py312` feature and hard-errors under `cargo build/test/clippy --workspace` without it. The script's own comment warns explicitly against falling back to `cargo test -p sase_core` directly, since that "silently skips the `sase_core_py` binding tests" — i.e. for anything touching `sase_core_py`, always run through `./scripts/check.sh` / `just check`, never bare `cargo test -p sase_core`.

## Summary recommendation for where the new eligibility contract fits

Given `finalizer/` already owns run-identity binding (`run_id`/`agent_id`/`turn_nonce` staleness checks), obligation/dirty-state modeling (`FinalizerObligationWire`, `FinalizerTriggerKindWire::DirtyRepository`), and outcome/deferral classification (`FinalizerDeferralReasonWire::BelongsToAnotherTurn` is almost exactly "not this run's own commit"), while `artifact_link/` owns the link-row schema and relation registry it would write into — a new eligibility contract is a **policy layer that sits between them**, consuming run-identity + host-verified-diff facts (finalizer-shaped) and producing a decision about whether to call `upsert_artifact_link_row` (artifact_link-shaped). The cleanest fit matching this crate's existing module granularity (one directory per bounded concern, `mod.rs` + `wire.rs` + a couple of policy files, `#[cfg(test)]` inline, re-exported from `crates/sase_core/src/lib.rs` via a `pub use <mod>::{ fn_a, fn_b, TypeA, TypeB, ..._SCHEMA_VERSION };` block inserted alphabetically) is a **new sibling module** — e.g. `crates/sase_core/src/artifact_link_eligibility/` or `crates/sase_core/src/run_publish_eligibility/` — rather than folding it into either existing directory, since neither one currently imports the other and each already has a clear, singular purpose that a run-identity/dirty-state eligibility gate does not share with either.

The Rust core report is in too — it recommends a new sibling module (`crates/sase_core/src/artifact_link_eligibility/` or similar) that consumes run-identity facts and produces a publish/commit eligibility verdict, following the `finalizer/` module's wire conventions. Still waiting on the Python publication-path report before I start writing code.

Still nothing to declare — no files changed yet. Waiting on the last research agent.

I now have comprehensive coverage of all requested areas. Let me compile the final report.

That's sufficient confirmation (already established via test evidence that `upsert_row` writes to disk unconditionally). I have everything needed. Here is the full research report.

# Research Report: Automatic Artifact-Link Publication Gating

## Path correction (important)

The path given in the task, `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13`, is a directory whose only subdirectory named `sase/` is a **separate git checkout** (remote `sase-org/sase.git`) containing just this project's own dogfood config (`memory/`, `xprompts/`, `sase.yml`, `task_types.json`) — no Python source at all (81 tracked files, no `src/`).

The actual Python source tree (with `src/sase/...`, `tests/...`) lives in the **parent** git repo, whose toplevel is:

```
/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13
```

All paths below are relative to that root (e.g. `src/sase/agents_sync/referenced_by_planning.py` = `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_13/src/sase/agents_sync/referenced_by_planning.py`).

---

## 1. `src/sase/agents_sync/referenced_by_planning.py`

**Purpose:** Pure computation module — builds durable "Referenced By" (markdown-table) write-back *requests* implied by one agent's rendered prompt archive (explicit `@ref` citations and bare prose path mentions of `plans/`/`research/` documents). It performs **no I/O writes and no outbox/store calls itself**.

Key functions:
- `plan_referenced_by_requests(*, target: ProjectTarget, rendered: RenderedPromptArchive, agent_artifacts_dir: Path, global_agent: str, primary_revision: str, store: SddStore, workspace_root: Path, repository_roots: Mapping[str, Path], agent_url: str | None, now: datetime | None = None) -> tuple[ReferencedByOutboxItem, ...]` — for every artifact record the prompt archive linked, resolves it to a document under a `markdown_table`-policy sidecar role and emits one `cites`/`origin="prompt_ref"` item, deduping by `logical_key` and summing `uses`.
- `prose_referenced_by_requests(*, target, prompt_text: str, global_agent, primary_revision, store, workspace_root, agent_url, now=None) -> tuple[ReferencedByOutboxItem, ...]` — regex-scans raw prompt text for exact `(repos/)?(plans|research)/20YYMM/....md` mentions (`_PROSE_ARTIFACT_PATH_RE`) and emits `origin=PROMPT_PROSE_ORIGIN ("prompt_prose")` items only for a confirmed on-disk file match.

Both are gated internally by `_referenced_by_policies()` (only sidecar roles whose `ref.publication.referenced_by == "markdown_table"` participate) and `_role_roots()`.

**Trigger / call chain:** Called from `src/sase/agents_sync/prompt_archive/preparation.py::_plan_referenced_by_requests()` (line 138 of `prepare_prompt_archive` flow), which is invoked while building a `PreparedPromptArchive` (`.referenced_by_requests` field) during `publish_prompt_archive`. The actual **write-back / enqueue** happens in `src/sase/agents_sync/prompt_archive/publish.py`:
```python
for request in prepared.referenced_by_requests:
    enqueue_referenced_by_request(request)   # publish.py:241-242
```
(`enqueue_referenced_by_request` lives in `src/sase/agents_sync/referenced_by_outbox_operations.py:27`.) This happens only after the prompt archive itself has been committed and (if needed) pushed to the agents sidecar, inside `publish_prompt_archive()`.

Immediately after that commit succeeds, `publish.py` also **drains** the queue in the same call:
```python
referenced_by_error = _drain_referenced_by_after_prompt_publish(target, git_runner=git_runner)  # publish.py:256
```
→ `sase.agents_sync.referenced_by_publication.drain_referenced_by_requests(target, git_runner=...)`.

**Important finding — this is a *separate* outbox from `artifact_link_outbox.py`.** It is its own durable queue (`referenced_by_outbox*.py` family: `referenced_by_outbox_models.py`, `_store.py`, `_operations.py`, `_serialization.py`, `_diagnostics.py`) with its own JSONL-backed store keyed by project. `drain_referenced_by_requests()` (`referenced_by_publication.py:24`) calls `list_referenced_by_requests(project_key, include_quarantined=False)` which filters only on `not item.quarantined and not item.terminal` (`referenced_by_outbox_store.py:36`) — **there is no "is agent published" gate anywhere in this path**, unlike `artifact_link_outbox.py`. It fires unconditionally whenever the prompt archive commit succeeds, i.e. it is triggered per-commit-of-the-prompt-archive, not per "family published" status. It's a second, related-but-distinct mechanism the plan may also need to touch, since it's likewise not gated on "this run had real attributable file changes" — it fires as long as `cp.publication_agent` is set and a commit method (`create_commit`/`create_pull_request`) ran (see §3 below), regardless of whether that commit contained real content or was itself just SDD-chore work.

`ReferencedByOutboxItem` (`referenced_by_outbox_models.py:13`) fields: `project_key, project, global_agent, agent_url, primary_revision, sidecar_role, provider, artifact_id, repo_relpath, identity_value, canonical_ref, destination, uses, published_date, relation="cites", origin="prompt_ref", description, attempts=0, last_error, quarantined=False, quarantined_at, terminal=False, terminal_reason, created_at, updated_at`, with `logical_key = (global_agent, primary_revision, sidecar_role, artifact_id, relation, origin)`.

Also invoked from a background sync path: `src/sase/agents_sync/git_sync.py:89-156` calls `clear_quarantined_referenced_by_requests`, `drop_terminal_referenced_by_requests`, and `drain_referenced_by_requests` as part of the general agents-sync sweep.

---

## 2. `src/sase/scripts/sase_chop_artifact_link_backfill.py`

**Purpose:** An hourly builtin housekeeping chop (`@builtin_chop("artifact_link_backfill")`) that owns 4 bounded jobs per enabled project:
1. Retroactive derivation sweep (`run_artifact_link_backfill_batch`) over pre-existing documents.
2. **The read-outbox drain** for agents that have since published (`drain_artifact_link_outbox`).
3. Cross-workspace `reconcile_and_repair_artifact_links` / `reconcile_aggregate()`.
4. Dangling-ref repair via git rename history.

Key functions:
- `_run(runtime: BuiltinChopRuntime) -> ChopResultBuilder` — top-level chop entry, iterates `_enabled_project_records()`.
- `_run_project(project_key, workspace_dir, *, swept, totals, deadline, chop_deadline, state_path, runtime)` — per-project driver. Sweep is time-budgeted/resumable via a JSON checkpoint (`artifact_link_backfill.json`, `_STATE_SCHEMA_VERSION=1`).
- The outbox drain call site (line 247):
```python
outbox_report = drain_artifact_link_outbox(store=store)   # sase_chop_artifact_link_backfill.py:247
totals.outbox_drained += outbox_report.drained
totals.outbox_dropped += outbox_report.dropped
```
Note: called with **no `agent_name` argument** → operates over *all* queued agents/entries in the project outbox in one pass (unlike the commit-time call in `workflow_publication.py`, which scopes to one agent). `drop_stale_terminal` defaults to `True` here, so terminal-but-never-published entries older than the retention cutoff get dropped (see §"published-agent status check" below).
- `_Totals` dataclass: `projects, failed_projects, sweep_scanned, sweep_persisted, sweep_remaining, outbox_drained, outbox_dropped, reconciled, repaired_renames, deferred_projects, warnings: list[str]`.

**Published-agent status check used today:** none directly in this file — it delegates entirely to `drain_artifact_link_outbox()`'s internal `_agent_is_published()` gate (see §4/§5). This chop is the periodic background sweep that lets a *previously unpublished* agent's queued reads get committed later, purely because `resolve_cli_reference(f"agent:{name}")` now resolves to `"exact"|"drifted"|"vcs_backed"` — i.e. **exactly the mechanism the plan needs to change**, since (per `builtin_entry_agent.py`) agent-name resolution "globalizes" a bare local shell name to its shared **agent-hood** page, so once *any* neighbor in the hood publishes, every neighbor's queued reads become "publishable" here even if that specific run made no real edits.

---

## 3. `src/sase/workflows/commit/workflow_publication.py`

**Purpose:** Post-commit publication steps for the commit workflow (`run_agent_publication_step`), invoked after a primary VCS commit/PR is created. Publishes bead pages, the prompt archive, the agent hood, and drains the artifact-link outbox — all keyed off a `CommitCheckpoint`.

Key functions/signature:
```python
def run_agent_publication_step(
    cp: CommitCheckpoint,
    method: str,
    *,
    checkpoint_save: Callable[[CommitCheckpoint], str | None],
    get_vcs_provider: Callable[[str], object],
) -> bool
```
- Early return `True` (no-op) unless `method in ("create_commit", "create_pull_request")`.
- Publishes bead pages (`publish_committed_bead_pages`) once (`"publish_bead_pages" not in cp.completed_steps`).
- If `not cp.publication_agent`: only refreshes the plan header and returns — **agent/link publication is entirely skipped** for non-agent (interactive/user) commits.
- Resolves `cp.primary_revision` from the VCS provider if missing.
- Publishes the prompt archive (`publish_prompt_archive`) — this is where §1's referenced-by items get enqueued+drained.
- If `"publish_agent_hood" in cp.completed_steps` already (i.e., a resumed/retried checkpoint): calls `_drain_artifact_link_outbox_for_agent(cp, ...)` directly and returns.
- Otherwise, calls `publish_committed_agent_hood(cp.publication_agent, cp.primary_revision, commit_cwd=cp.cwd)` (from `sase.agents_sync.commit_publication`), then **always** calls `_drain_artifact_link_outbox_for_agent(cp, ...)` before marking `"publish_agent_hood"` complete — i.e., the outbox drain runs on *every* commit-with-a-publication-agent, regardless of whether the hood publication itself succeeded/queued/skipped.

The outbox drain helper:
```python
def _drain_artifact_link_outbox_for_agent(
    cp: CommitCheckpoint, *, checkpoint_save: Callable[[CommitCheckpoint], str | None]
) -> None:
    if not cp.publication_agent or _ARTIFACT_LINK_OUTBOX_STEP in cp.completed_steps:
        return
    ...
    drain_artifact_link_outbox(
        agent_name=cp.publication_agent,
        drop_stale_terminal=False,
        push_after_commit="async",
    )
    ...
    cp.completed_steps.append(_ARTIFACT_LINK_OUTBOX_STEP)   # "drain_artifact_link_outbox"
```
This is scoped to `agent_name=cp.publication_agent` (this run's own shell/family identity), `drop_stale_terminal=False` (never drops here — only the chop sweep drops stale entries), `push_after_commit="async"`.

**Where newly-eligible pending links would get promoted as part of a real commit:** exactly here — `_drain_artifact_link_outbox_for_agent` is the natural insertion point for a new "did *this run* have real attributable file changes" check, since `cp` (the `CommitCheckpoint`) already carries `commit_sha`, `commit_tree`, `primary_revision`, `entry_id`, `cwd`, `completed_steps` — i.e., the "commit checkpoint identity" the plan says to reuse (see §"run identity" below). Today this call is unconditional whenever a commit method ran and `cp.publication_agent` is set; it does not check whether the commit that just happened touched real content vs. was itself just an SDD/artifact-link/bead maintenance commit.

`CommitCheckpoint` (`src/sase/workflows/commit/checkpoint.py:19`) fields relevant here: `method, payload, cwd, version, cl_name, project_file, diff_path, base_cl_name, reserved_name, parent_cl_name, dispatch_result, primary_revision, commit_sha, commit_tree, pushed, dispatch_error, publication_agent, no_commit_dispatched, cs_name, entry_id, completed_steps: list[str], created_at`.

---

## 4. All callers of `drain_artifact_link_outbox` (from `src/sase/sdd/artifact_link_outbox.py`)

```
grep -rn "drain_artifact_link_outbox" src/  (excluding definition/`__all__`)
```

| Call site | Context |
|---|---|
| `src/sase/scripts/sase_chop_artifact_link_backfill.py:247` — `drain_artifact_link_outbox(store=store)` | Background hourly chop sweep, unscoped (all agents), `drop_stale_terminal` default `True`, `push_after_commit` default `"async"`. |
| `src/sase/workflows/commit/workflow_publication.py:189` — `drain_artifact_link_outbox(agent_name=cp.publication_agent, drop_stale_terminal=False, push_after_commit="async")` | Inline, at the end of a real commit-workflow publication step (`_drain_artifact_link_outbox_for_agent`), agent-scoped. |

No other production call sites exist. (Tests call it directly: `tests/main/test_artifact_link_outbox.py`.)

Related but distinct `artifact_link_outbox` API surface used elsewhere:
- `src/sase/artifact_cli/read.py:284` — `append_artifact_link_outbox_entry(project_key=..., agent_name=identity.name, row=...)` inside `_record_read_link()` (called on every `sase artifact read`). **This is the writer/enqueue side.** It first calls `store.upsert_row(row)` (line 283) — an unconditional *local, synchronous* write of the read-link row into the sidecar JSON index on disk (creating dirty git state in that sidecar repo immediately, independent of publish status) — then queues the same row into the outbox for later cross-workspace/deferred replay.
- `src/sase/artifact_cli/link_health.py:179` — `inspect_artifact_link_outbox(store.project_key)` inside the `sase artifact link doctor` report — read-only stats (`queued`, `dropped` counts), no gating logic.

---

## `src/sase/sdd/artifact_link_outbox.py` — deep dive

**Purpose:** Machine-local durable JSONL replay log (`~/.sase/projects/<project_key>/artifact-link-outbox.jsonl`) for artifact-link **read** rows recorded by agents, so a read recorded by an agent that isn't (yet) publishable stays queued instead of being written into a shared sidecar index prematurely.

Key dataclasses:
- `_ArtifactLinkOutboxEntry(schema_version, id, created_at, project_key, agent_name, row: dict[str, Any])` — `.logical_key` = `(source_ref, relation, target_ref)`.
- `_ArtifactLinkOutboxStats(queued, dropped)`.
- `_ArtifactLinkOutboxDrainReport(queued, drained=0, retained=0, dropped=0, committed=False, changed_indexes: tuple[Path,...]=(), skip_diagnostics: tuple[str,...]=())`.

Module constants:
```python
_PUBLISHED_AGENT_STATUSES = frozenset({"exact", "drifted", "vcs_backed"})
_TERMINAL_AGENT_STATES = frozenset({"completed", "failed", "stopped", "dismissed"})
_TERMINAL_AGENT_STATUSES = frozenset({"DONE", "FAILED", "STOPPED", "CANCELED"})
_DEFAULT_RETENTION_DAYS = 90
```

Key functions:
```python
def append_artifact_link_outbox_entry(*, project_key, agent_name, row, now=None, entry_id=None) -> _ArtifactLinkOutboxEntry
def inspect_artifact_link_outbox(project_key: str) -> _ArtifactLinkOutboxStats
def drain_artifact_link_outbox(
    *, store: ArtifactLinkStore | None = None, agent_name: str | None = None,
    drop_stale_terminal: bool = True, push_after_commit: bool | str | None = "async",
) -> _ArtifactLinkOutboxDrainReport
```

**`drain_artifact_link_outbox` pipeline** (the exact "is this publishable" logic):
1. `_partition_selected(entries, agent_name=...)` — if `agent_name` given, only that agent's entries proceed; others stay `retained`.
2. `_partition_stale_terminal(...)` — (only when `drop_stale_terminal=True`) drops entries whose agent is terminal (`_TERMINAL_AGENT_STATES`/`_TERMINAL_AGENT_STATUSES`) and finished more than `_terminal_cutoff()` (retention days, default 90) ago **and still not published** (`not _agent_is_published(entry.agent_name)`).
3. **`_partition_publishable(entries)` — the core gate:**
```python
def _partition_publishable(entries):
    publishable, retained = [], []
    for entry in entries:
        if _agent_is_published(entry.agent_name):
            publishable.append(entry)
        else:
            retained.append(entry)
    return publishable, retained
```
4. `_partition_machine_writable_entries(...)` — filters out entries whose sidecar root isn't machine-writable right now (unauthorized entries stay queued).
5. `_upsert_publishable_entries(...)` — converges rows by logical key (keeping max `uses`), upserts only the *delta* uses vs. existing store rows, collects `changed_indexes`.
6. `_commit_outbox_indexes(...)` → `commit_artifact_link_indexes(changed_indexes, store=..., repo_roots=..., push_after_commit=..., mutation_origin="machine")` (imported from `sase.sdd._artifact_link_commit`).
7. On success, `_rewrite_without_ids(...)` removes drained/dropped ids from the outbox file (drained ids only if the commit succeeded — if `commit_artifact_link_indexes` fails, the whole drain reports `retained=len(entries)` and nothing is removed).

**The load-bearing "is this agent published" check:**
```python
def _agent_is_published(agent_name: str) -> bool:
    try:
        from sase.artifact_cli.references import resolve_cli_reference
        result = resolve_cli_reference(f"agent:{agent_name}")
    except Exception:
        return False
    return result.resolution.status in _PUBLISHED_AGENT_STATUSES
```
This resolves `agent:<name>` through `resolve_builtin_entry` → `resolve_agent_entry` (`src/sase/artifact_providers/builtin_entry_agent.py`) which delegates to the Rust resolver locating `agents/<globalized-name>/README.md`. Per that module's own docstring: *"Resolution globalizes a bare local name (e.g. '9w' -> 'alice.athena.9w')"* — i.e. it resolves against the shared **agent-hood** page (`memory/glossary/agent-hood.md`: agents sharing a `<name>.` prefix, e.g. `foo`, `foo.bar`, `foo.baz`, `foo.bar.1`, are all one hood/neighborhood). **This is exactly the bug surface the plan targets**: `_agent_is_published(entry.agent_name)` returns `True` the instant *any* member of the agent's hood/family has a published hood page — it says nothing about whether *this specific run* (this outbox entry's originating shell) made any real file edits, or even ran again after another family member committed.

---

## Other "agent published" gates found across `sdd/`, `agents_sync/`, `finalizers/`

```
grep -rn "is_published|published_agent|agent.*publish" src/sase/sdd/ src/sase/agents_sync/ src/sase/finalizers/
```

There are **three independent copies of essentially the same check**, all keyed off `resolve_cli_reference(f"agent:{name}")` and the same `{"exact","drifted","vcs_backed"}` status set:

1. `src/sase/sdd/artifact_link_outbox.py:527` — `_agent_is_published` (above, gates the read-outbox drain).
2. `src/sase/sdd/artifact_link_derivation.py:262` — `_is_agent_published(agent_name, *, context=None)`, used by `ArtifactLinkDerivationInputs.is_agent_published` (built in `artifact_link_derivation_inputs()`, line 71) which is threaded into `derive_candidate_links(...)` for the retroactive/derived-link candidate rules (e.g. the `implements` rule) — i.e. whether an *agent* endpoint is eligible to be named in a **derived** (not read-outbox) link at all.
3. `src/sase/sdd/_artifact_link_store_reconcile.py:159` — `ArtifactLinkStoreReconcileMixin._agent_ref_is_published(ref, *, context)`, used by `_row_is_publishable()` (line 138) inside `durable_sidecar_rows()` — this is the gate for **cross-workspace aggregate reconciliation**: *"Return sidecar rows whose agent endpoints have published… This filter serves the publication decision only: which rows are safe to hand another machine over the outbox."* Explicitly documents that the *local* read-model aggregate (`project_aggregate_rows`/`preview_reconciled_aggregate`) must **not** apply this filter — only the publication/durability decision does.

All three use the identical `_PUBLISHED_AGENT_STATUSES = frozenset({"exact","drifted","vcs_backed"})` set and the identical `resolve_cli_reference(f"agent:{name}")` call — meaning a fix to the eligibility contract likely needs to touch (or centralize) all three, not just `artifact_link_outbox.py`, since they all suffer the same "any hood-mate publishing anywhere retroactively legitimizes me" property.

**A fourth, structurally different mechanism** — not gated on agent-publish status at all — lives in `src/sase/finalizers/reconciliation.py::_auto_commit_artifact_link_indexes_if_possible()` (called from `prepare_commit_dirty_state`). This scans the *current* dirty git state (`_artifact_link_dirty_candidates`, using `classify_artifact_link_repo_file`/`ArtifactLinkRepoFileKind` from `sase/sdd/_artifact_link_files.py`) for repos whose **only** dirt is link-index (`links/**/*.json`) and/or lock files, and if so, auto-commits them via `commit_artifact_link_indexes(..., verify_publication=True)` **unconditionally** — no check that any *other* repo in this run has real content changes. This is precisely the mechanism `test_two_implicit_plan_reads_commit_once_without_declaration` exercises (see below) and is the other half of the "soon to be wrong" behavior, independent of the outbox/agent-publish gate.

---

## Test files

### `tests/main/test_artifact_link_outbox.py` (200 lines) — exercises `drain_artifact_link_outbox` + `sase artifact read` directly

- `test_drain_published_agent_commits_dirty_index_without_double_counting` — two `handle_read()` calls queue 2 outbox entries for agent `reader` (mocked `resolve_cli_reference("agent:reader")` → status `"exact"`, i.e. "published"); `drain_artifact_link_outbox(store=store, agent_name="reader", drop_stale_terminal=False, push_after_commit=False)` drains both, commits once (`report.drained==2`, `report.committed is True`, `HEAD` gains exactly `links/doc.md.json`), converges `uses=2` in one index row, and empties the outbox.
- `test_drain_unpublished_agent_leaves_entry_queued_and_uncommitted` — same setup but the mocked `agent:reader` resolves to status `"missing"` (unpublished); after `handle_read()` queues 1 entry, `drain_artifact_link_outbox(...)` reports `drained=0, retained=1, committed=False`; the outbox entry (1) and the dirty uncommitted index file remain, confirming the current "not published → stays queued forever" gate.

Both tests directly assert the *current* `_agent_is_published` behavior — they patch `sase.artifact_cli.references.resolve_cli_reference` for the literal string `"agent:reader"`, so a future implementation that changes eligibility to "this run had real file changes" rather than "this agent name resolves as published" will need updated/new fixtures here (e.g. simulating a run with vs. without real edits in the primary/linked/sdd repos), while these two tests likely still hold as regression coverage for the *agent-hood-published* signal specifically (assuming it becomes one necessary-but-no-longer-sufficient condition, or is retired in favor of the new contract — worth flagging to the implementer).

### `tests/llm_provider/test_commit_finalizer_auto_artifact_links.py` (671 lines) — exercises `prepare_commit_dirty_state` (the finalizer's own index-only auto-commit path) + the full `run_finalizers` builtin-commit flow

All tests call `_record_reads(plans, *targets)` → `ArtifactLinkStore(...).upsert_row(_read_row(target))` **directly** (bypassing the outbox and the agent-publish gate entirely — this is the "already-local, already-dirty sidecar index" scenario), then `_prepare(artifacts)` = `prepare_commit_dirty_state(resolve_finalizer_project_dir(), artifacts)`.

- `test_two_implicit_plan_reads_commit_once_without_declaration` — **asserts current, soon-to-be-wrong behavior**: two implicit plan reads (`plan:202608/one.md`, `plan:202608/two.md`) are the *only* dirt anywhere (no other repo/content edits at all this run); `prepare_commit_dirty_state` auto-commits them as `chore(artifact-links): persist link indexes` with `artifact_links_auto_committed is True`, leaves the dirty state clean, and a second `_prepare()` call is a no-op. This is exactly the case the new policy must break: zero real attributable file changes in the entire run, yet the two read-derived link-index writes still get committed automatically. (No agent-publish check is even in play here — the gate that needs to change is "dirty state is *only* link indexes/locks," with no requirement that *anything else this run* was a real edit.)
- `test_mixed_unrelated_dirt_is_left_for_the_declaration` — one implicit read plus an unrelated hand-edited `notes.md`; asserts the link index still auto-commits (`artifact_links_auto_committed is True`) while `notes.md` is left dirty for the normal declaration path — i.e. today "real dirt exists somewhere in the same repo" is *not required* for the link-index auto-commit, it commits regardless.
- `test_pre_existing_dirty_index_is_not_auto_committed` — uses `capture_dirty_baseline(main, artifacts)` (writes `finalizer_baseline.json`) to snapshot a pre-existing dirty `preexisting.md.json` before a new read is recorded; asserts only the *new* read's index file gets auto-committed, the pre-existing dirty index is left alone. This demonstrates the existing baseline-diffing mechanism already distinguishes "this run's own writes" from "dirt that predates this run" — a reusable primitive.
- `test_malformed_candidates_remain_dirty` — a hand-corrupted `broken.md.json` sibling is never staged/committed (fails `is_canonical_artifact_link_index`), stays in `dirty_state.repos[].changed_files`.
- `test_multiple_sidecars_commit_once_each` — two sidecar roles (`plan`, `research`) each get exactly one auto-commit for their own index-only dirt.
- `test_publication_failure_is_recoverable` — a broken git remote makes the local `chore(artifact-links)` commit succeed but push/publish fail; asserts `artifact_link_publication_error` is populated (`"was committed locally but NOT published"` / `"unpublished artifact-link commit(s)"`), and that `_ensure_artifact_link_commit_published(plans)` can later confirm publication once the remote is fixed.
- `test_executor_accepts_artifact_link_auto_commit_against_existing_marker` — full `run_finalizers` flow: a pre-seeded `commit_results.json` entry (sha `"a"*40`) plus a fresh link-index auto-commit; asserts the executor does not treat the artifact-link auto-commit as "unexplained drift" against the declared commit markers (`runner.assert_not_called()`, i.e. `run_stitch_create` is never invoked since the link commit already satisfied the obligation) — this exercises `reject_unproven_reconciliation_transition`'s marker/fingerprint diffing.
- `test_executor_rejects_artifact_link_auto_commit_without_new_marker` — same setup but the `commit_results.json` marker ledger write is suppressed after `prepare_commit_dirty_state`; asserts `BuiltinCommitFinalizerError` with `match="vanished|discarded|attributable"` — i.e. the executor's stale/attributability check already fires when dirty content disappears without a matching commit marker. (Note: `"attributable"` here is about the marker-vs-dirty-diff invariant, not about "real file changes" in the plan's sense — it's a different attributability check than what the plan needs to add.)
- `test_executor_commits_mixed_report_after_artifact_link_auto_commit` — a link-index-only auto-commit plus a genuine `report.md` edit; asserts the link-index commit and the real-content stitch commit land as two separate commits in the same repo, and both get recorded as `commit_results.json` markers with the same `cwd`.

None of these tests currently gate the finalizer auto-commit on "did the run also touch a *primary*, *linked/external*, or a *different* artifact-document repo with real content" — that's the gap the plan needs to close, and `test_two_implicit_plan_reads_commit_once_without_declaration` is the single test that most directly encodes (and will need to be flipped/extended for) the old behavior.

---

## Existing "run identity" / "checkpoint" / "dirty baseline" / "finalizer evidence" primitives available for reuse

The plan's hint ("reuse existing run metadata, dirty baselines, authenticated finalizer evidence, and commit checkpoint identity") maps onto concrete, already-existing pieces:

**Run metadata / run id**
- `SASE_AGENT_TIMESTAMP` env var is treated as the canonical `run_id` in several places:
  - `src/sase/finalizers/declaration.py:345` — `_run_identity(root, command) -> (run_id, agent_id, turn_nonce)`, requires `SASE_AGENT_TIMESTAMP`, `SASE_AGENT_NAME`/`agent_meta.json`, and `SASE_FINAL_TURN_NONCE_ENV`, raising `FinalizerDeclarationError(code="missing_turn_metadata")` if any is absent — this is the strongest existing "this specific run" identity triple.
  - `src/sase/workflows/commit/checkpoint.py:56` — `session_id = os.environ.get("SASE_AGENT_TIMESTAMP") or str(os.getpid())` used to name the on-disk checkpoint file when `SASE_ARTIFACTS_DIR` isn't set.
  - `src/sase/workflows/commit/commit_tracking.py:499,552,626` — every `commit_results.json` marker embeds `run_id = os.environ.get("SASE_AGENT_TIMESTAMP", "")` (falls back to the artifacts-dir basename).
  - `src/sase/agent/identity.py::discover_agent_identity()` — returns `AgentIdentity(name, source, artifacts_dir)` from `SASE_AGENT_NAME` (this run's own shell name, e.g. `alice.athena.09l` — distinct from the family/hood name that `_agent_is_published` resolves against).

**Commit checkpoint identity**
- `CommitCheckpoint` (`src/sase/workflows/commit/checkpoint.py:19`) — `commit_sha`, `commit_tree`, `primary_revision`, `entry_id`, `publication_agent`, `cwd`, `completed_steps`, persisted/loaded via `checkpoint_save`/`checkpoint_load`.

**Authenticated finalizer evidence (real-commit ledger)**
- `commit_results.json` (via `write_result_marker` / `record_sdd_commit_result_marker` in `src/sase/workflows/commit/commit_tracking.py`) — each marker: `{method, run_id, cwd, result, commit_result, commit_sha, commit_tree, message, repo_name, diff_path, entry_id, pushed, dispatch_error, ...}`.
- `src/sase/finalizers/commit_repair.py`:
  - `load_commit_results(artifacts: Path | None) -> list[dict[str, Any]]`
  - `new_commit_markers(before, after) -> list[dict[str, Any]]` (diffs two marker snapshots by `_marker_key = (cwd, result, commit_sha, commit_tree, entry_id)`)
  - `marker_matches_repo(marker, repo: DirtyRepo) -> bool`
  - `marker_evidence(marker) -> list[FinalizerOutcomeEvidenceWire]`
  
  **Caveat found:** SDD/sidecar commit markers (written via `commit_sdd_files` → `_record_sdd_commit_marker` → `record_sdd_commit_result_marker`) do **not** carry `auto_commit_type`/`cause` — an artifact-link-only `chore(artifact-links): persist link indexes` commit and a "real" SDD content commit are both recorded identically except for `message`/`repo_name`. Any new "real attributable file changes" check built on `commit_results.json` alone would need to special-case `ARTIFACT_LINK_COMMIT_MESSAGE` / `BEAD_LINK_COMMIT_MESSAGE` (both defined in `src/sase/sdd/_artifact_link_commit.py:24,27`) to avoid a self-referential "the link commit counts as evidence that links may be published" loop.

**Dirty baselines**
- `src/sase/llm_provider/commit_finalizer_baseline.py` — `capture_dirty_baseline(project_dir, artifacts_dir)` (writes `finalizer_baseline.json`, scope `run_start`), `capture_opened_repo_dirty_baseline(...)` (scope `opened_repo`, for repos first touched mid-run), `load_dirty_baseline(artifact_root) -> DirtyBaseline | None`, `load_finalizer_baseline_records(...) -> tuple[FinalizerBaselineRecord, ...] | None`. `FinalizerBaselineRecord`: `repo_id, path, kind, name, scope, fingerprints: dict[str, tuple[str,str|None]], captured_at`. This is exactly the pre-existing-vs-this-run diffing primitive `test_pre_existing_dirty_index_is_not_auto_committed` relies on, and is reused inside `finalizers/reconciliation.py::PreparedCommitDirtyState.{dirty_state_before, fingerprints_before}` / `reject_unproven_reconciliation_transition`.

**Repo-kind typology matching the plan's "primary / linked-external / artifact-document repo" language**
- `_DirtyRepoKind = Literal["main", "sibling", "external", "sdd"]` (`src/sase/llm_provider/commit_finalizer_types.py:8`), with `DirtyRepo(name, path, changed_files, kind)` / `DirtyState(project_dir, repos, details)`. `"main"` = primary repo, `"sibling"`/`"external"` = linked/external repos, `"sdd"` = artifact/document sidecar repos (plans/research/agents/beads). `collect_dirty_state()` (`src/sase/llm_provider/commit_finalizer_state.py`) is the function that produces this typed snapshot; it's already called from `prepare_commit_dirty_state`.
- `_artifact_link_dirty_candidates(dirty_state) -> (indexes, lock_only_roots)` and `classify_artifact_link_repo_file(path, repo_root) -> ArtifactLinkRepoFileKind {INDEX, LOCK, REJECTED, OTHER}` (`src/sase/sdd/_artifact_link_files.py`) already distinguish "link index/lock only" dirt from real content dirt per repo — the natural building block for "does *any* repo this run touched have non-link-index real changes."

---

## Summary of the cross-cutting surface for the plan

1. **Read-outbox gate** (`src/sase/sdd/artifact_link_outbox.py::_agent_is_published`, duplicated in `artifact_link_derivation.py::_is_agent_published` and `_artifact_link_store_reconcile.py::_agent_ref_is_published`) — all three resolve `agent:<name>` which globalizes to the shared hood/family page, so any family member's publication anywhere retroactively unlocks every neighbor's queued reads. Drained from two call sites: the hourly chop (`sase_chop_artifact_link_backfill.py:247`, unscoped) and commit-time (`workflow_publication.py:189`, scoped to `cp.publication_agent`, i.e. this run's own shell name — the natural place to add a "this run had real changes" precondition).
2. **Finalizer index-only auto-commit gate** (`finalizers/reconciliation.py::_auto_commit_artifact_link_indexes_if_possible`) — currently commits link-index-only dirt with zero requirement that *anything* in the run was a real edit (`test_two_implicit_plan_reads_commit_once_without_declaration`). Direct local writes originate from `ArtifactLinkStore.upsert_row()` inside `artifact_cli/read.py::_record_read_link()` on every `sase artifact read`, independent of the outbox.
3. **Referenced-By outbox** (`agents_sync/referenced_by_planning.py` + `referenced_by_outbox*.py` + `referenced_by_publication.py`) — a separate queue/drain with no publish-status gate at all today, fired whenever the prompt archive itself commits — likely needs the same "real changes this run" precondition applied at its drain trigger point (`workflow_publication.py`'s `publish_prompt_archive` call) if it's in scope.
4. Reusable primitives already exist for "did *this run* make real, attributable file changes": `SASE_AGENT_TIMESTAMP`/`SASE_AGENT_NAME` run identity, `CommitCheckpoint`, `commit_results.json` markers + `new_commit_markers`/`load_commit_results`, `finalizer_baseline.json` dirty baselines, and `DirtyRepo.kind ∈ {main, sibling, external, sdd}` — none of which are currently wired into either publish gate above.

Both reports are in. I now have a full picture of the current architecture. Let me read the exact source of the most load-bearing files directly so I can design precise changes.

Let me examine `finalizers/commit.py` in full to understand exactly how multi-repo dispatch and publication interact, since that determines where to hook in release-evidence recording.

Now I have a clear, bounded design. Let me check the Rust crate's top-level module wiring before adding the new module.

Now I'll create the new Rust module.

Now wire it into `lib.rs`, both the `pub mod` declaration and the `pub use` re-export block, placed alphabetically right after `artifact_link`.

Let me compile-check just the core crate quickly before adding PyO3 bindings.

The shared cargo build cache (`/mnt/poseidon/cargo-target`) is completely full at the host level — this affects all Rust builds on this machine, not just mine. Rather than touch that shared, possibly-in-use cache, I'll point my build at a local target directory with free space.

Now let's add the PyO3 bindings. First, locate the artifact_link binding section and the module registration function in the massive `lib.rs`.

Now I'll insert a new import block for `artifact_link_eligibility`, right after the `artifact_link` block, and then the binding functions + registrations.

Now insert the binding functions after `py_artifact_link_upsert_row`:

Now let's register these functions in the `#[pymodule]` init function, right after `py_artifact_link_upsert_row`'s registration.

Let's add the doc bullet mentioned in the module-level comment convention, then compile-check.

Now let's compile-check the full workspace, including PyO3 bindings, using the local target dir.

Good, `python3.14` resolves directly on PATH. Let's use `scripts/check.sh` (which handles `PYO3_PYTHON` resolution itself) with the local target dir, running it in the background since it will take a while.

Just formatting differences. Let's apply `cargo fmt`.

Good — that's `cargo fmt` reformatting my own new file, as expected. Now let's run `cargo check --workspace` with `PYO3_PYTHON` set.

Compiles clean across the whole workspace. Let me check disk space on the local cache, then run clippy + full test suite in the background.

Now switching to the Python side. Let me review the existing facade/wire style precisely before writing new files.

Now let's write the Python facade and durable evidence store.

The full sase-core `clippy` + `cargo test --workspace` run passed. Let me confirm the log briefly, then continue with the Python-side implementation.

Now let's insert a new round-trip test right after this one, at line 20048.

Let me fix a bug I introduced — a shadowed variable and a fictional helper function. I'll rewrite the test cleanly.

Now let me replace lines 20147-20156 (the broken final block) with a correct version using the already-computed `ineligible_decision` PyObject before it was shadowed. I'll restructure to keep the original PyObject under a distinct name.

Now let's compile and run this specific test.

Passes. Now let's run fmt-check and clippy again for the final state, then move to the Python side.

Just formatting again, and clippy is clean. Let's apply fmt.

The Rust side is solid — clippy clean, fmt clean, all tests pass including the new eligibility module and its PyO3 bindings. Let me kick off one more full-suite confirmation run in the background while I move to the Python side.

Now let's edit `read.py` to stop the synchronous sidecar write.

Now let's update `artifact_link_outbox.py` with the run-scoped eligibility gate.

Now let's update `_partition_stale_terminal`, `_partition_publishable`, `_entry_from_mapping`, and remove `_agent_is_published`.

Now let's replace `_agent_is_published` with `_entry_is_eligible`, and fix `_entry_from_mapping` to parse `run_id`.

Now let's view the full file to confirm consistency and check the `__all__` list / any remaining references.

This file looks correct and complete. Now let's update `workflow_publication.py`.

Now let's add the helper function itself, right before `_drain_artifact_link_outbox_for_agent`.

Now let's update the specific test to add `run_id` and patch the new eligibility function instead of the removed `_agent_is_published`.

Now let's replace `_patch_read_context` and the two tests below it.

Now let's rewrite the two test functions.

Let's view the full updated test file to verify consistency before moving on.

Now let's update the finalizer reconciliation test file — first add a clarifying comment to the helper, then rewrite the flipped test.

Now let's replace the flipped test itself.

No longer used elsewhere, so I'll remove that unused import and add the two now-needed imports.

Now let's rebuild and reinstall the Rust extension into the Python venv so the new bindings are available, then run the affected tests.

Good — the project venv already uses Python 3.14.7, which satisfies the abi3-py312 requirement. Let's run `just install` with `CARGO_TARGET_DIR` overridden to avoid the full shared disk.

Installation succeeded. Let's verify the new binding is actually importable in the venv.

Now let's run the affected Python test files.

Found the bug — the outbox's row convergence needs to *sum* uses for `read`-origin rows (each queued row is one independent read event) rather than taking the max, since the immediate store-side convergence that used to do this no longer runs. Let me fix `_converged_rows`.

All 21 tests pass now. The remaining diagnostics are pre-existing (unrelated to my change) or expected underscore-prefixed lambda params. Now let's add a regression test for retry-safety and pre-existing durable counts.

I need to fix the delta computation too — for `read` origin, the desired total must be `existing + this batch's increment`, not just the batch's own raw count.

Now let's search broadly for anything else referencing the outbox schema version or entry shape that the schema bump might break.

All pass. Now let's write a dedicated Python facade round-trip test and a test for the release-evidence module, then run a broad sweep and finally `just check`.

Now let's write a contract test for the new facade, following this style.

Now let's run this new test file.

Now let's add the test itself, after `test_commit_publishes_every_sidecar_inline_in_order`.

All 12 pass, including the new evidence test. Now let's run a broad sweep across the whole test suite to catch anything else, then finish with `just check`.

Excellent — all 3300 tests pass. Now let's run the mandatory `just check` lint+test gate for the sase repo.

Just a formatting nit in my new facade file — let's run `just fmt` and re-check.

Formatting applied. Now let's run `just check` in full, handing it to a monitor since it may take a while per project policy.

While `just check` runs, let me verify my earlier analysis that the `referenced_by` write-back path is already structurally gated (no code change needed there).

Still running. Let me wait for the notification rather than poll.

This all matches my intended change set. Let me wait for the `just check` background task to finish.

I'll wait for the `just check` background task notification.

The finalizer declaration was submitted successfully — commit decisions recorded for both the main repo and the sase-core sibling repo, covering all files this run wrote for the artifact-links eligibility change.
