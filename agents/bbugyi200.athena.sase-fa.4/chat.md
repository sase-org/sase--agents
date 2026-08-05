# Chat History - ace-run (sase-fa.4)

- **TIMESTAMP:** 2026-08-05 15:20:42 EDT
- **MODEL:** claude/sonnet
- **AGENT:** sase-fa.4

## Prompt

#gh:gh_sase-org__sase
%id(4, clan=sase-fa, bead=sase-fa.4)
%model:@medium_phase_worker
%auto
Can you complete the work for bead sase-fa.4? The bead is already reserved for you and assigned to your agent
name: it was set to status=in_progress before you started reading this, either by the `sase bead work` launch
checkpoint or by the runtime promoting an ad-hoc wait-time claim. Do not set the status by hand. Read its
description and design file, do the work, and close the bead with
`sase bead close sase-fa.4 --note "<what you verified>"`. Closing an assigned phase bead is unaffected by the
parent-close descendant guard. Do NOT close the parent epic. Do not create beads yourself: record discovered
follow-up work as a `PROPOSED FOLLOW-UP:` entry via
`sase bead note sase-fa.4 'PROPOSED FOLLOW-UP: <one-line summary — detail>'`; the epic's land agent triages
these into task beads.

## Response

I'll start by reading the bead's description and design file.

Now let me read the plan file for full context.

No prior work has been done. This is a large phase. Given its scope and complexity, I'll delegate deep investigation to a subagent first to map out the exact code paths before making changes.

While that investigation runs, let me look at the actual agents sidecar repo to see the corruption firsthand.

This is very useful. Let's read the key files fully.

Let me check what these two rewrite commits actually did.

Now let's look at `src/sase/agents/cli_sync.py` to see the full implementation.

Now let's look at `publication.py` which calls `apply_payload_atomic` — this is likely the "publish_hood" / signing entry point.

I now have all the material needed. Let me compile the structured report.

Confirmed read-only (git ls-tree / directory scan for provenance indexing). Now I have everything needed to write the report.

This confirms the model. Let me check `verify_run_files` and `content_digest`, plus `publication_validation.py::load_validated_publication`.

## Report: Sidecar chat.md digest-drift bug

### 1. The writer — no in-repo path performs an out-of-band rewrite

I could not find any code path in this repo that rewrites an already-published `agents/{global_name}/chat.md` file without going through the signed publish transaction. Every writer of that path is one of:

- **The only writer of live sidecar payload bytes**: `apply_payload_atomic()` in `src/sase/agents_sync/v2_io.py:75`. It stages a whole payload dict (`{relpath: bytes}`), atomically replaces changed files, and rolls back all of them together on any failure. It is called from exactly one place: `_publish_hoods()` in `src/sase/agents_sync/publication.py:98-113`, itself called only by `publish_agent_hood`/`reconcile_agent_hoods` (`publication.py:27`, `:74`).
- **`_prepare_prompt_archive_retry`** in `src/sase/agents_sync/commit_publication_transaction.py:320-346` regenerates `prompts/{month}/*.md` (a *separate* unsigned surface — see §6) during the same locked transaction; it never touches `agents/*/chat.md`.
- Everything else that mentions `chat.md` is read-only or foreign-import related: `src/sase/history/chat_catalog_provenance/sidecars.py:291,315,328` (provenance indexing, `git ls-tree`/directory scan, no writes), `src/sase/agents_sync/incoming_detection.py:449` and `incoming_cache_storage.py:239,245` (validating/staging *foreign* owners' incoming bundles into a local cache, not mutating one's own already-published hood), and `src/sase/agents_sync/io.py:123,314,317` / `v2_import_package.py:49` (legacy v1 bundle read/write, distinct format).
- `src/sase/agents_sync/prompt_archive/migration.py:_apply_month` (lines 300-360) is a genuine **out-of-band writer** — it acquires `bounded_agents_lock` directly and commits via raw `git commit` (`_commit_paths`, line 362), completely bypassing `commit_publication_transaction.py`/`plan_hoods`/owner-manifest re-signing. But it only ever touches `prompts/{month}/*.md`, which (per §6) is **not** referenced by any hood snapshot or owner manifest, so it can't explain a hood-snapshot digest mismatch on `chat.md`.

**Conclusion for item 1:** there is no supported command, doctor-fix, or migration in this repo capable of producing the observed symptom (73 `chat.md` files edited in place inside already-published hood directories, with no owner-manifest/hood-snapshot re-signing). The two sidecar commits ("chore(agents): revert stored chat prompt sections", "chore(prompts): revert stored prompt sections") must have been produced by direct, generic file edits + `git commit` against the sidecar checkout — i.e., an agent or human used ordinary file-editing tools on the sidecar working tree, outside any `sase agents_sync` code path. That is the actual root-cause gap: **the three listed commits removed the code that embedded "rendered prompt"/"XPrompt" sections in new `chat.md`/prompt-archive documents (`376a3b1bb`, `92b31a1b4`, `1239c5f5c`), but shipped no supported way to bring already-published historical payloads into the new format**, so someone manually "reverted" the stored sections in the sidecar files by hand to match, and that hand-edit desynced the payload bytes from their signed digests. There is no writer bug to fix in the sense of "stop this code from doing X"; the fix is a **missing safety net**: (a) a doctor check that detects payload/digest drift (§3), and (b) a supported "repair/resign" command so nobody needs to hand-edit sidecar files again (§4/§6).

### 2. Signing / hood-snapshot / owner-manifest code

- **Hood snapshot model**: `V2HoodSnapshot` in `src/sase/agents_sync/v2_models.py:194-244` (`owner`, `project`, `local_hood`, `global_hood`, `structural_ancestors`, `runs: tuple[V2RunRecord,...]`, `containers`, `relationships`, `schema_version`). `V2RunRecord` (`v2_models.py:49-75`) carries `files: tuple[tuple[str, V2FileReference], ...]` keyed by kind (`"meta"`, `"state"`, `"commits"`, `"prompt"`, `"chat"`, `"embedded_workflows"`, `"prompt_steps"`). `V2FileReference` (`v2_models.py:35-45`) = `{path, digest, size_bytes}`.
- **Building/signing a hood snapshot**: `build_hood_snapshot()` in `src/sase/agents_sync/publication_snapshot.py:43-112`. Per-run file records (including the `("chat", "chat.md", run.chat_bytes)` tuple) are produced by `_published_run()` at `publication_snapshot.py:115-171`; each file's digest/size is computed by `file_reference(path, content)` → `content_digest()` = `hashlib.sha256(payload).hexdigest()` in `src/sase/agents_sync/v2_io.py:57-63`.
- **Signing entry point (the actual "sign" step)**: `plan_hoods()` in `src/sase/agents_sync/publication_planning.py:35-92`. It builds the hood snapshot, serializes it deterministically via `v2_json_bytes()` (`v2_io.py:51-54`, canonical JSON + trailing `\n`), computes `content_digest(snapshot_bytes)`, and writes that into a `V2OwnerHoodEntry(digest, files, run_count, family_count)` (`v2_models.py:248-260`) keyed by hood name inside the owner manifest (`publication_planning.py:87-91`). It self-verifies via `load_validated_publication()` before returning the payload (`publication_planning.py:~90-100`).
- **Owner manifest model**: `V2OwnerManifest` in `v2_models.py:263-279` (`owner`, `project`, `hoods: tuple[tuple[str, V2OwnerHoodEntry],...]`).
- **Owner manifest read/write/path**: `src/sase/agents_sync/v2_manifest_io.py`. `owner_manifest_path(owner)` → `users/{username}/machines/{machine}/manifest.json` (line 32-37); `read_owner_manifest()` (line 40-53); `decode_owner_manifest()` (line 103-142, strict schema validation, requires files sorted+unique). Manifest is *written* as part of `plan_hoods()`'s payload dict (`publication_planning.py`, `payload[owner_manifest_path(owner)] = v2_json_bytes(manifest.to_json_dict())`), then physically written by `apply_payload_atomic()` (`v2_io.py:75`).
- **Verification**: `load_validated_publication()` in `src/sase/agents_sync/publication_validation.py:45-114`. It reads all owner manifests (`read_all_owner_manifests_lenient`, `v2_manifest_io.py:67-70,73-100`, globbing `users/*/machines/*/manifest.json`), then for every `(hood, entry)` in every manifest computes `snapshot_path(owner, hood)` = `users/{u}/machines/{m}/hoods/{hood}/snapshot.json` (`publication_validation.py:156-160`), reads the bytes, checks `content_digest(raw) == entry.digest` (line 80-83), reads/decodes the snapshot, checks identity match (line 86-93), checks `hood_file_set(snapshot) == entry.files` (line 94-98, exact set equality of every file path the hood claims), and finally calls `verify_run_files()` (line 99-100, defined 117-128) for every run's file references — comparing `len(content) == reference.size_bytes` and `content_digest(content) == reference.digest` for each. Any mismatch raises `AgentsSyncFormatError`, and since this function is invoked over *every* manifest/snapshot on disk, one bad `chat.md` anywhere blocks the whole thing (this is what's failing today: 73 rewritten `chat.md` files, digest/size no longer matching their `V2FileReference` entries recorded in old, unresigned hood snapshots).
- `hood_file_set()` (`publication_validation.py:140-153`) is the exact definition of "every file this hood's manifest entry must list": the snapshot file itself, `hoods/{hood}/README.md`, every run's file paths (`agents/{global_name}/...`), `agents/{global_name}/README.md` per run, and `families/{global_name}.md` per family container.

### 3. Doctor check pattern (for drift-detection check)

Structure to follow, modeled on `src/sase/doctor/checks_agent_publication.py` (689 lines) and the manifest-readability diagnostic added by `0e40decdc`:

- **Module** exports a `*_check_specs(context: DoctorContext) -> tuple[CheckSpec, ...]` factory (`checks_agent_publication.py:175-184`, `agent_publication_check_specs`).
- **`CheckSpec`** (`src/sase/diagnostics/registry.py:16-31`): `id`, `group`, `title`, `runner: Callable[[], DiagnosticCheck | Iterable[DiagnosticCheck]]`, `deep=False`. IDs are dotted, e.g. `"state.agent_publication_outbox"`.
- **Registration**: add the import + `*your_check_specs(context)` line inside `build_doctor_registry()` in `src/sase/doctor/runner.py:53-91` (agent-publication is registered at line 56 + 84).
- **Diagnostic reporting**: `_check_agent_publication_outbox()` (`checks_agent_publication.py:187-405`) builds a `DiagnosticCheck` (`src/sase/diagnostics/models.py:37`) with `status` in `{"OK","WARN","ERROR","SKIP"}`, `summary` (one line), `details` (tuple of per-problem strings, capped at `_MAX_DETAIL_ROWS = 10`), `next_steps` (tuple of remediation-command sentences), and `data` (full machine-readable dict for `-j`/JSON output).
- **The exact pattern for "owner manifest is broken" (0e40decdc)** is `_owner_manifest_problems()` (`checks_agent_publication.py:546-594`): resolves `require_agent_owner_identity()` and `resolve_sync_targets(...)` (from `src/sase/agents_sync/targets.py`), then for each target calls `read_owner_manifest(target.sidecar_path, owner, V2ProjectIdentity(...))` inside a `try/except (AgentsSyncFormatError, OSError, RuntimeError, ValueError)`, wrapping failures in `_OwnerManifestProblem` (dataclass at line 131-152) with a `remediation_command` (defaults to `_REMEDIATION_COMMAND = PUBLICATION_RETRY_COMMAND = "sase agent sync --retry-quarantined"`, line 38). These problems are merged into the outbox check's WARN branch at line 335-392, and `_next_step_for_command()` (line 635-655) maps each known command constant to human remediation text.
- **A new "chat.md digest drift" check should**: iterate `resolve_sync_targets(...)` targets, call `load_validated_publication(target.sidecar_path)` (or a lighter-weight walk reusing `hood_file_set`/`verify_run_files`) inside a try/except on `AgentsSyncFormatError`, and report WARN/ERROR with `next_steps` pointing at a new repair command (see §4). This is the natural place to plug in — it reuses the exact digest-checking logic that already blocks publication, so the check and the failure mode are provably in sync.

### 4. `sase agent sync` CLI

- **Parser**: `src/sase/main/parser_agent.py:135-195`. Subcommand `"sync"` registered under `agents_sub.add_parser("sync", ...)`. Existing flags: `-c/--check`, `-d/--drop-retired`, `-j/--json`, `-p/--project` (repeatable), `-r/--refresh`, `-q/--retry-quarantined`. A new repair mode would be added the same way, e.g. `sync_parser.add_argument("--repair-digests", action="store_true", ...)` (a new subcommand `sase agent sync repair` would instead need its own `agents_sub.add_parser("sync-repair", ...)` or a nested subparser under `sync_parser`, following the `retire-v1`/`tribe`/`archive` nested-subcommand precedent at `parser_agent.py:104-263`).
- **Dispatch**: `src/sase/main/agent_handler.py:37-40` — `if sub == "sync": from sase.agents.cli_sync import handle_agents_sync; sys.exit(handle_agents_sync(args))`.
- **Implementation**: `src/sase/agents/cli_sync.py:20-71`, `handle_agents_sync()`. `--check` calls `get_agents_sync_status()` (`src/sase/agents_sync/status.py`); otherwise it calls `sync_agents(projects, retry_quarantined=..., drop_retired=...)` from `src/sase/agents_sync/git_sync.py`. A repair flag would branch here similarly, e.g. calling a new `repair_hood_digests(projects, apply=...)` function.
- **"Locally owned" hoods / owner identity**: resolved via `AgentIdentitySnapshot.current()` / `require_agent_owner_identity()` → `AgentOwnerIdentity(username, machine_name)` (`src/sase/core/agent_identity_facade.py:20-22`), e.g. `bbugyi200`/`athena` maps directly to the sidecar path segment `users/bbugyi200/machines/athena/...` (`v2_manifest_io.py:32-37`, `publication_validation.py:156-160`). "Locally owned hoods" = `project_inventory.eligible_hoods()` (`ProjectHoodInventory`, `src/sase/agents_sync/inventory.py`) — used in `reconcile_agent_hoods()` (`publication.py:74-95`).
- **"Bounded agents lock"**: `bounded_agents_lock(path, timeout_seconds)` in `src/sase/agents_sync/git_sync_ops.py:298-318` — a `flock`-based, timeout-bounded exclusive file lock (`fcntl.flock(..., LOCK_EX | LOCK_NB)` polled until `deadline`), opened at `agents_git_dir(repo, git_runner) / "sase-agents-sync.lock"` (e.g. `git_sync.py:221`, `prompt_archive/migration.py:306-308`). `configured_agents_lock_timeout()` (`git_sync_ops.py:336-344`) reads an env-var override, else `DEFAULT_SYNC_LOCK_TIMEOUT_SECONDS`. Any new repair command must take this same lock before writing into the sidecar, exactly like `_apply_month()` does (`migration.py:316-321`) and like `publish_queued_transaction` implicitly relies on via the outer sync-agents flow.

### 5. Publication outbox / `sase agent sync -q -p sase`

- **Durable queue file**: one JSON file per project at `<projects_root>/<project_key>/agents-publication-outbox.json` (`AGENT_PUBLICATION_OUTBOX_FILENAME`, `src/sase/agents_sync/publication_outbox_store.py:21`). Items are `AgentPublicationOutboxItem` / `SidecarPublicationRequest` (`publication_outbox_models.py`), enqueued via `enqueue_agent_publication`/etc. (`publication_outbox_operations.py`).
- **`-q/--retry-quarantined`** clears quarantine and retries via `sync_agents(..., retry_quarantined=True)` (`git_sync.py`) → ultimately `publish_queued_transaction()` in `src/sase/agents_sync/commit_publication_transaction.py:45-209`, which pulls/rebases, imports foreign history, builds inventory, calls `hooks.publish_hood` (→ `publish_agent_hood`/`plan_hoods`/`apply_payload_atomic`, the same signed-transaction path from §2), commits (`git_sync.commit_agents_payload_if_dirty`), and pushes, with retry-on-non-fast-forward logic.
- **Background drainer**: `src/sase/scripts/sase_chop_sidecar_publication.py`, registered as `@builtin_chop("sidecar_publication")` (line 463), run periodically by the `publications` lumberjack (see `_AXE_*` constants referenced in the doctor check). It scans every project's outbox (`_projects_with_pending_publications`, line 210-246) and drains agent-hood requests via `drain_agent_publications` (`src/sase/agents_sync/commit_publication.py`), which again funnels into the same `commit_publication_transaction.py` path.
- **Where a repair mode plugs in**: same CLI surface as `sase agent sync` (`cli_sync.py`/`parser_agent.py`), guarded by the same `bounded_agents_lock`, but instead of (or in addition to) draining the outbox it would recompute+rewrite one or more hood snapshots' digests to match on-disk bytes (or vice versa) and push the fix through `apply_payload_atomic()` so the repair is itself an atomic, signed transaction — never a raw file edit.

### 6. Digest-audit approach / data structures for a repair script

No existing helper walks the sidecar computing actual-vs-signed digests standalone; `load_validated_publication()` (§2) is the closest thing (it *is* the audit, just wired to raise rather than report). A repair script should reuse it directly: catch `AgentsSyncFormatError`, or better, call the lower-level pieces (`hood_file_set`, `verify_run_files`, `content_digest`) per-hood to build a full diff report instead of failing fast on the first mismatch.

**Exact on-disk shapes** (all JSON via `v2_json_bytes()` = canonical JSON + `"\n"`, digest = `sha256` hex):

- Owner manifest — `users/{username}/machines/{machine}/manifest.json`:
```json
{
  "schema_version": 2,
  "owner": {"username": "...", "machine_name": "..."},
  "project": {"key": "...", "name": "..."},
  "hoods": {
    "<hood>": {"digest": "<sha256 of hoods/<hood>/snapshot.json bytes>",
               "files": ["agents/<global>/chat.md", "...", "..."],
               "run_count": N, "family_count": N}
  }
}
```
- Hood snapshot — `users/{username}/machines/{machine}/hoods/{hood}/snapshot.json` (`V2HoodSnapshot.to_json_dict()`, `v2_models.py:227-244`):
```json
{
  "schema_version": 2, "owner": {...}, "project": {...},
  "hood": {"local_name": "...", "global_name": "..."},
  "structural_ancestors": [...],
  "runs": [{"source_run_id": "...", "local_name": "...", "global_name": "...",
            "state": "...", "started_at": "...", "finished_at": "...",
            "dismissed_at": "...", "metadata": {...}, "commits": [...],
            "files": {"chat": {"path": "agents/<global>/chat.md",
                                "digest": "<sha256>", "size_bytes": N}, "meta": {...}, ...}}],
  "containers": [...], "relationships": [...]
}
```
- Payload files referenced by `files{}`: `agents/{global_name}/meta.json`, `state.json`, `commits.json`, `prompt.md`, `chat.md`, `embedded_workflows.json`, `prompt_steps.json` (`publication_snapshot.py:141-159`), plus `agents/{global_name}/README.md` and `families/{global_name}.md` (rendered, not digest-tracked individually but included in the manifest's `files` set per `hood_file_set`).
- **A from-scratch repair script** would: glob `users/*/machines/*/manifest.json`; for each hood entry, read `hoods/{hood}/snapshot.json`, recompute `content_digest(raw_bytes)` and compare to `entry.digest`; if snapshot itself matches but a referenced payload file's actual bytes differ from its recorded `V2FileReference.size_bytes/digest` (i.e. the exact drift here — `chat.md` edited after the snapshot was signed), it must choose: (a) **restore** the payload bytes to match the old signed digest (revert the sidecar edit — safest, matches "publication was already correct"), or (b) **rebuild and re-sign**: recompute the file's real digest/size, rewrite the `files` entry inside the hood snapshot, recompute the snapshot digest, update the owner-manifest hood entry, and write all three (payload + snapshot + manifest) atomically via `apply_payload_atomic()` under `bounded_agents_lock`, then commit+push exactly like `plan_hoods()`/`_publish_hoods()` do. Option (b) is the one consistent with "publish archived prompt bodies verbatim" being the intended new format — i.e., re-sign forward rather than revert.

**Important caveat for the repair-script author**: the *prompt archive* under `prompts/{month}/*.md` (managed by `src/sase/agents_sync/prompt_archive/*`) is validated separately by `validate_prompt_archive()` in `prompt_archive/validation.py` and is **not** part of `hood_file_set()`/owner-manifest digests at all — so if any of the 73 rewritten files are prompt-archive documents rather than hood-run `chat.md` payloads, they need a completely different remediation path (there is no digest to fix there, only `sase agent prompts migrate --write` /`prepare_prompt_archive` regeneration).

Investigation confirms the root cause: an earlier phase (`sase-f2.6`) ran a throwaway migration tool that hand-edited already-published `chat.md` files directly in the agents sidecar and committed them with raw git commits — bypassing the signed publish transaction entirely, so the hood-snapshot digests went stale. Now I'll set up a task list and read the remaining core modules before implementing the fix.

Now let me read the remaining core modules.

Now let me look at git_sync.py, cli_sync.py, parser_agent.py's sync section, and git_sync_ops.py's locking + commit/push helpers.

Let me look at the owner-manifest doctor tests specifically to mirror for the digest-drift check.

Now I'll implement the core repair module.

This is an existing, accepted pattern in this exact codebase (`v1_retirement.py:286`) for `IntegrateExportPass` callbacks, so the diagnostic is cosmetic and consistent with prior art — not something to change. Now let's write the doctor check module.

Now register it in `runner.py` with a minimal single-line addition:

Now let's wire the CLI. First the parser flag:

Now let's update `handle_agents_sync` to dispatch the new flag.

Now let's verify the file compiles and check imports are all correct.

Good, everything imports cleanly. Let me mark tasks done and now write the tests.

Let's run this test file now to iterate quickly before writing the doctor test.

All four core tests pass. Now let's write the doctor check tests, mirroring the existing owner-manifest doctor test pattern.

Now fix the `_sidecar` unused warning in the second test:

Now let's run these doctor tests.

Excellent, both git-integration tests pass on the first try. Now let's add a CLI-level test for the `--repair-digests` flag dispatch.

All 14 tests pass. Now let's mark task 5 done and run `just check`.

`just install` finished. Now let's run `just check`.

Good, `just fmt` auto-reformatted those files. Let's re-run `just check`.

Now let's remove it from `__all__` and update the test import.

Now let's re-run just check.

All still pass. Now let's run the full `just check`.

`just check` passes cleanly this time (the earlier failure was flaky/order-dependent, unrelated to this phase's changes — confirmed to pass in isolation). Let's verify the changed files list.

`just check` is fully green. Let's mark task 6 complete and note the flaky test found.

Now let's move to the live repair. First let's check the current doctor state to confirm the corruption before touching anything.

Clean working tree, up to date with origin. Now let's run the live repair, scoped to the `sase` project only.

The repair committed and pushed successfully, re-signing all 73 drifted files. Let's verify the digest audit now reports 0 mismatches.

Confirmed idempotent — no-op on the second run. Let's check the sidecar's git log to confirm the repair commit landed cleanly.

This is running in the background now — I'll wait for it to complete rather than poll.

While the sync runs in the background, let's check for the `sidecar_publication_backoff.json` residue mentioned in the plan.

While that continues, let's investigate the beads sidecar divergence mentioned in the plan.

`sase` project shows zero drift — confirmed. Bob-cli still shows drift (out of scope, deliberately left alone per the plan). Let's check final outbox state one more time to confirm stability.

Now let's record the discovered follow-up work before closing.

Now let's do a final `just check` pass to confirm everything is still green before closing.

Let me do a final review of the complete diff before closing.

Bead `sase-fa.4` is closed. Summary of what was done:

**Root cause**: The 73 stale hood-snapshot digests came from a since-deleted throwaway migration tool (`sase-f2.6`) that hand-committed rewritten `chat.md` files directly into the agents sidecar without going through the signed publish transaction. No reachable code path today can reproduce this.

**Repair built**:
- `src/sase/agents_sync/publication_repair.py` — re-derives file digests from on-disk payload and re-signs the owning hood snapshot + owner manifest, strictly scoped to one owner's path family (structurally can't touch a foreign owner).
- `sase agent sync --repair-digests [-p PROJECT]` CLI flag, reusing the existing locked pull/commit/push/retry transaction.
- New doctor check (`state.agent_publication_digest`) that reuses the same repair-planning logic in dry-run form, so detection and remediation can never disagree.
- 11 new tests covering repair/no-op/foreign-owner-refusal/doctor-check/CLI dispatch, all passing.

**Live verification against the real `sase` agents sidecar**: repaired all 73 drifted files (pushed commit `686ac5a2c`), cleared all 18 quarantined outbox requests down to empty, confirmed the beads-sidecar divergence had already landed cleanly, and deleted the stale `sidecar_publication_backoff.json` residue. Bob-cli was deliberately left untouched per the plan's scope decision.

`just check` passed clean once fully; three later runs each hit a different unrelated pre-existing flaky test (confirmed to pass in isolation). Filed as PROPOSED FOLLOW-UP notes on the bead, along with a discovered bug where family-lane publications (like the epic's own `t2` example) are misdetected as "not materialized," and bob-cli's own digest drift for `sase-f6` to pick up.

I'll verify the bead's actual status and the working tree state before committing.

Bead sase-fa.4 is confirmed CLOSED. Now invoking the commit skill to commit the listed files.

This matches the described work. Now writing the commit message.

Commit succeeded. Verifying the working tree is clean and pushed.

Working tree is clean and in sync with `origin/master`.

**Summary**: Bead sase-fa.4 was already closed (confirmed via `sase bead show`). Committed the phase's remaining uncommitted work — `publication_repair.py`, the new `state.agent_publication_digest` doctor check, the `--repair-digests` CLI flag wiring, and their tests (9 files, 818 new lines + 69 changed) — as `fix(agents-sync): repair stale hood-snapshot digests and add drift check`. The commit pushed cleanly and the working tree is clean and up to date with `origin/master`.
