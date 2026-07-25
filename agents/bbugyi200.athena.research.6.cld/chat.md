# Chat History - ace-run

- **TIMESTAMP:** 2026-07-09 16:21:05 EDT
- **MODEL:** claude/opus
- **AGENT:** research.6.cld
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260709_160924.md`

## Prompt

%name:research.@.cld %m:@research_assist %g:research #gh:gh_sase-org__sase When preparing a workspace directory for a SASE agent, we currently always clone the sdd repo locally. I've been wondering if that is necessary and if we could instead have a single clone of the sdd repo live locally on each machine. Agents can just share that and sync it when they need to and push changes to it when they need to. Can you do some research to help me understand if this is a good idea and if we can solve the concurrent rights problem where multiple agents try to make changes to sdd files at the same time? When you have concluded your research, express your answer by setting some sase variables. Write this research to a new markdown file under the $(sase sdd path research)/$(date +%Y%m)/ directory.


## Response

I'll research this thoroughly. Let me start by understanding the current workspace preparation, what the "sdd repo" is, and any existing concurrency mechanisms — plus how to set sase variables and the expected research-file format.

Let me kick off parallel exploration and read the relevant skill/format references.

`.sase/sdd/` is itself a git repo, and there's already a prior research file about the sdd repo. Let me dig into both, plus the `checkout.json` and how workspaces are prepared.

Now I have strong grounding. `.sase/sdd/` is a real git repo tracking `git@github.com:sase-org/sdd.git`, and there's prior research on a separate SDD repo. The user's question is a different, adjacent concern: **per-workspace clone vs. one shared clone per machine + concurrent writes.** Let me determine how the sdd repo is materialized today (per-workspace vs. shared), check for symlinks, and map the workspace-prep code.

This is the crux. Confirmed key facts:
- `sdd.storage: separate_repo` — this repo stores SDD in a **separate git repo** (`sase-org/sdd`).
- The workspace's `.sase/sdd` (inode `19270215`) is a **distinct clone** from the primary's `.sase/sdd` (inode `17715618`) — so **each `sase_<N>` workspace gets its own full clone of the sdd repo**. That's exactly the "always clone locally" the user is questioning.

Now let me map the code paths (clone/prep, beads storage format, commit/push/sync, existing locking) and read the research-file conventions + the sase_var mechanism. Launching parallel exploration.

Critical finding: beads are stored as **aggregate files** — `beads.db` (SQLite, 930K) and `issues.jsonl` (1.1M) — not one-file-per-bead. That makes beads the real content-level conflict hotspot (binary SQLite can't be git-merged; JSONL appends collide), unlike per-file research/plans. Let me record skill use and fan out code exploration to nail the remaining specifics.

I'll research the SDD materialization code. Let me start with parallel searches across the key areas.

Let me read the core store resolution files and search for the clone/materialization code.

I'll investigate the SDD git store concurrency safety. Let me start with parallel searches across the key areas.

Now let me look at the workspace_provider hooks and the GitHub plugin, plus workspace creation logic.

While those agents work, let me quantify the actual costs (clone size, workspace count) that make or break the shared-clone idea.

Now let me read the sync module and search broadly for callers and locking primitives.

Now let me search broadly for locking primitives and bead SQLite/db access.

~213 MiB pack per sdd clone (bloated by the infographic PNGs in research/), and **27 workspaces** on this machine each holding their own clone. Let me get the exact total duplication figure — that's the core economic argument.

The `db.py` header says production routes through `sase_core_rs` facades. Let me examine the production bead write path, the finalizer callers, and JSONL writes.

Let me examine the production bead write path via Rust, and the finalizer/plan-accept callers to determine commit frequency.

Let me read the bead project.py write path, which contains the SQLite connection, git_sync and export_to_jsonl calls.

Let me look at the Rust bead mutation facade for locking, and the plan-accept commit callers for frequency.

Let me check the bead mutation facade, whether a bead daemon exists, and the changespec locking that wraps git.

Let me check the git index.lock stale-lock handling and whether it wraps SDD commits.

472 MiB per clone, **~3.3 GiB currently duplicated** across active workspaces (and each fresh workspace re-pays it). Strong disk/time argument for sharing the object store. One more thing I need before synthesizing: whether the SQLite `beads.db` is actually tracked in git or is a rebuildable cache (that determines the true bead conflict surface).

Excellent — this reshapes the concurrency picture significantly:
- `beads.db` (SQLite) is **gitignored** — a rebuildable cache, *not* a git conflict surface.
- Tracked bead state is **event-sourced**: per-bead append-only streams (`beads/events/streams/sase-<id>.jsonl`) — separate files per bead, so different beads never collide — plus aggregate projections (`issues.jsonl`, `manifest.json`).
- Commits already carry `SASE_AGENT` / `SASE_MACHINE=athena` trailers and are tiny (1 file, 1 line).

Let me confirm where the clone comes from (network vs local hardlink) — central to the startup-time argument — while the agents finish.

Let me examine the hook spec, plugin manager, and the plugins directory including the GitHub provider.

Decisive detail: the clone is created **fresh from GitHub over the network** every time (`clone: from github.com:sase-org/sdd.git`, pack has **1 link** = no hardlink sharing). So each of the ~27 workspaces pays a ~213 MiB network transfer at prep time. And `manifest.json` is a **derived projection** (`"generated_from": "issues.jsonl"`), confirming bead aggregates are regenerable.

A reframing is emerging: **concurrent writes to shared SDD state already happen today** — 27 independent clones all push to the same `sase-org/sdd` master; conflicts are mediated at the *remote*. Let me wait for the two agents to confirm the clone code path and the current push/rebase/retry posture, which is the linchpin of the recommendation.

Let me check the plugin registration mechanism and find the sase-github plugin location.

Let me find where plugins are registered (entry points) and locate the sase-github plugin package.

I have gathered enough. Here is the focused structured summary.

## Concurrency analysis: SDD git store commit/push and locking

### 1. SDD commit path — `src/sase/sdd/_commit.py`

`commit_sdd_files()` (lines 212-271) is the core. It runs, all via `_run_git` (subprocess `git`, bounded timeout, `check=True` so failures raise):

- L227: bails unless `sdd_dir/.git` exists.
- L652-669 `changed_sdd_files()`: `git ls-files --modified --others --deleted --exclude-standard -z -- <pathspecs>`.
- L235-241: `git add -- <files>`.
- L243-249: `git diff --cached --quiet -- <files>` (detect staged change).
- L256-262: `git commit -m <message> -- <files>`.

Key facts:
- **No pull / rebase / fetch** anywhere in the commit path.
- **`commit_sdd_files` does not push.** Push is only added by the wrapper `commit_sdd_store_files()` (L274-300) → `_push_sdd_store_after_commit()` (L408-440), and only for `SDD_STORAGE_SEPARATE_REPO` stores.
- **No dirty-index / `index.lock` handling.** If git's `.git/index.lock` is held by a concurrent process, `git add`/`commit` return nonzero and `_run_git` raises `CalledProcessError` (or `SddGitCommandTimeout` at the 30s default local timeout, `SASE_SDD_GIT_LOCAL_TIMEOUT`, L19/L23). There is **no wait, no retry, no stale-lock removal** here.
- Push mode is config-driven `sdd.push_after_commit`, default `"async"` (`_sdd_push_after_commit_config`, L394-405).
- The bare-git init variant `commit_bare_git_sdd_init_paths()` (L532-614) does `add`/`commit` and optional `push origin HEAD`; on non-fast-forward/timeout it only logs a warning (L597-614) — best effort, no rebase-retry.

### 2. Push + sync path — `src/sase/bead/sync.py`

SDD separate-repo pushes are delegated here (`_commit.py` L426 imports `push_bead_work_launch` / `push_bead_work_launch_async`).

- `push_bead_work_launch()` (L248-296): finds git root, checks a remote exists, then:
  - L270 `git push` (inherits stdio for creds).
  - On failure → L274 `git pull --rebase` → L285 `git push` **once**.
  - Returns `_PushOutcome`, **never raises**. This is the only "non-fast-forward" recovery: **single naive rebase-and-retry, no backoff, no loop.**
- `push_bead_work_launch_async()` (L310-339): spawns **detached** `sh -c "git push || (git pull --rebase && git push)"` (L331-338), `start_new_session=True`, stdin `DEVNULL`, output to a log file under `bead_push_logs`. Fire-and-forget.
- `git_sync()` (L31-46): only `git add` (stages, no commit/push). `commit_bead_work_launch()` (L49-105): stages + commits bead-state files, explicitly excluding `beads.db` (L200-212).

**Pushes are NOT serialized across processes.** There is no lock around `push`/`pull --rebase`. Multiple agents sharing one clone would race on `git pull --rebase` (which rewrites the working tree/HEAD) while others commit — the only implicit serialization is git's own `.git/index.lock` / ref locks, which fail hard rather than queueing.

### 3. Locking / mutual-exclusion primitives (grep results)

`fcntl.flock` exists in the repo but **none of it wraps SDD commits or bead-store git operations**:
- `src/sase/memory/locks.py:7-20` (`locked_file`), used by `memory/proposals/*`, `memory/read_log.py:346/360`.
- `src/sase/history/prompt_store.py:368`, `src/sase/dev_update/journal.py:41`, `src/sase/integrations/chat_install.py:241/346` (`install.lock`), `src/sase/agent/names/_resume.py:57` (`agent_name_allocation.lock` + `threading.RLock` L37), `src/sase/ace/agent_tags.py:180` (per-file `.lock`), `src/sase/ace/tui/actions/agents/_directive_persistence.py:334`.
- `src/sase/ace/changespec/locking.py` (L3, L137-183): advisory `fcntl.flock` on ChangeSpec `.gp` files (`changespec_lock`, `acquire_edit_lock` writing a `.edit_lock` PID sentinel). **This is the ChangeSpec subsystem, not SDD/bead git.**
- Git `index.lock` handling exists **only** in `src/sase/ace/tui/actions/agent_workflow/_prompt_bar_save_xprompt_git.py:234-259` (`_is_index_lock_error`, `_remove_git_index_lock`, `git_index_lock_retry_message`) — used by the TUI xprompt-save flow (`models_panel.py:442-470`). **Not used by `_commit.py` or `bead/sync.py`.**
- Numerous `threading.Lock`/`RLock` (e.g. `ace/tui/...`, `ace/changespec/cache.py:26`) are **in-process only**.

**Conclusion:** no process-wide, machine-wide, or file-based advisory lock guards SDD commits or bead git writes. The only real serialization on a shared clone would be git's own `.git/index.lock` and ref locks — which SDD/bead code does **not** wait on or retry (except the unrelated TUI xprompt path), so concurrent writers would surface hard `CalledProcessError`/timeouts.

### 4. Bead read/write and SQLite concurrency

- **Canonical store is `issues.jsonl`, owned by Rust.** `src/sase/bead/db.py:1-4` and `jsonl.py:1-4` both state production reads/mutations route through `sase_core_rs`. Mutations go through `src/sase/core/bead_mutation_facade.py` (`create`/`update`/`close`/`add_dependency`/`preclaim_epic_work`/`export_jsonl`, each `require_rust_binding("bead_*")`, invoked statelessly with just `beads_dir`). Reads via `bead_read_facade`.
- **`beads.db` (SQLite) is only a compatibility mirror, and it is gitignored** (excluded in `sync.py:200-212`). `src/sase/bead/project.py:430-439` `_refresh_db_from_jsonl()`: closes the connection, **deletes `beads.db`, `beads.db-shm`, `beads.db-wal`, then rebuilds from JSONL** after every mutation. `_export()` (L415-423) calls Rust `export_jsonl`, falling back to Python `export_to_jsonl`.
- SQLite `_connect` (`db.py:75-80`): `PRAGMA journal_mode=WAL`, `foreign_keys=ON`. **No `busy_timeout`, no `check_same_thread` tuning.** WAL here is on a throwaway per-process mirror, so it provides **no cross-process concurrency control** for canonical bead state. The delete-and-rebuild of `beads.db` is itself a race hazard if a clone/dir is shared by concurrent agents.
- **No bead daemon/server exists** (grep for bead daemon/server: no hits). Access is **direct file access per agent process**; any real cross-process locking would have to live inside the Rust `sase_core_rs` layer (not present in this Python tree).

### 5. When SDD commits/pushes happen per agent run (callers)

- **Plan accept** — `src/sase/axe/run_agent_exec_plan_accept.py`: writes spec+plan SDD files then commits (in-tree via `_commit_sdd_files`→`commit_sdd_files_for_exec_plan`, L74-77 / L346; separate-repo via `commit_sdd_store_files(..., push_after_commit=True)`, L326-331 and L352-357). Also `ensure_bare_git_sdd_initialized(commit=True, push=False)` at L295. Roughly **once per plan acceptance**, committing a small set of markdown files (spec + plan).
- **Finalizer** — `src/sase/llm_provider/commit_finalizer.py:325-344` `_auto_commit_separate_sdd_store_if_possible()`: best-effort at agent finalization, `commit_sdd_store_files(store, "chore(sdd): sync uncommitted SDD store changes")`. One sweep per finalize.
- **Other callers:** `plan_approval_actions.py:492`, `ace/tui/actions/agents/_notification_modals.py:325` (TUI accept), `sdd/store.py:527`, `sdd/migrate.py:85`, `sdd/beads.py:74`, and `bead/cli_common.py:331/362` (bead-store init). Bead-state commits fire at `sase bead work` launch (`bead/cli_work_commit.py:72/83` → `push_bead_work_launch[_async]`).

**Frequency/size:** SDD commits are event-driven (plan accept + finalize), not high-frequency, and each stages a handful of files (default pathspec `.`, `normalize_sdd_commit_pathspecs` L629-649, or targeted `paths`). Pushes for separate-repo stores default to **async detached** background pushes.

### Bottom line for a shared per-machine clone
- SDD commit and bead git write paths have **no application-level locking, no serialization, and only a single naive `pull --rebase` + one-shot retry** for non-fast-forward on push.
- The only mutual exclusion touching these paths is git's own `.git/index.lock`/ref locks, which the SDD/bead code does **not** wait on or retry — concurrent writers would hit hard failures/timeouts.
- `beads.db` is deleted-and-rebuilt per mutation and gitignored; canonical bead state is Rust-owned `issues.jsonl` with no visible cross-process lock in the Python layer and **no daemon** — direct per-agent file access.

Primary files: `src/sase/sdd/_commit.py`, `src/sase/bead/sync.py`, `src/sase/bead/project.py`, `src/sase/bead/db.py`, `src/sase/core/bead_mutation_facade.py`, `src/sase/ace/changespec/locking.py`, `src/sase/ace/tui/actions/agent_workflow/_prompt_bar_save_xprompt_git.py`, `src/sase/axe/run_agent_exec_plan_accept.py`, `src/sase/llm_provider/commit_finalizer.py`.

The sync/locking agent delivered a thorough picture. Key confirmations:

- **No machine/process-wide lock guards SDD commits or bead git writes.** `flock` exists in the repo but only for memory proposals, ChangeSpec `.gp` files, agent-name allocation — never around `_commit.py`/`bead/sync.py`.
- **Commit path** (`git add`+`git commit`, `check=True`) has **no index.lock wait/retry** — concurrent writers hit hard `CalledProcessError`.
- **Push** does a single naive `git push || (git pull --rebase && git push)`, fire-and-forget async, **not serialized**. `pull --rebase` rewrites the working tree — only safe today *because each clone is private*.
- **Beads**: canonical `issues.jsonl` is Rust-owned (`sase_core_rs`); `beads.db` is a gitignored SQLite mirror that's **deleted-and-rebuilt per mutation** — a serious shared-directory race hazard. No bead daemon.

While the clone-prep agent finishes, let me quantify the working-tree vs object-store split (informs a sparse-checkout recommendation).

Clean split confirmed: of 472 MiB per clone, **220 MiB is `.git` (shareable object store)** and **208 MiB is 171 infographic PNGs** in `research/` that an implementing agent essentially never reads. Only ~44 MiB is "live" SDD text. That makes the waste almost entirely eliminable.

I have enough to write the deliverable. Let me draft the research document now and fold in the clone-prep agent's exact code citations when it returns.

Found the sase-github plugin. Let me read the entry-points config and locate the GitHub SDD materialization hook implementation.

Let me determine which sase-github workspace is actually linked to this sase_12 environment, then read its SDD hook.

The linked plugin is `sase-github_12`. Let me read its workspace plugin SDD hooks.

Now let me read the core of the GitHub SDD materialization hook and the clone helpers.

Now let me investigate workspace creation (sase_<N> dir creation) and any object-store sharing mechanisms (--reference, --shared, worktree, rsync).

Let me examine the managed checkout creation in workspace_provider/utils.py and the agent setup path.

Deliverable written. Now let me set the answer as SASE variables (my conclusion is solid; the still-running clone agent only adds code-citation precision, not a change in recommendation).

Let me verify the agent setup flow and confirm no object-store sharing exists anywhere (including the plugin).

Research written, variables set. Let me give you the findings while the last background scan (exact clone code-path) wraps up.

## Research complete: `shared_sdd_clone_per_machine.md`

Written to `.sase/sdd/research/202607/shared_sdd_clone_per_machine.md`, and I set the answer variables (`shared_clone_recommended=yes_objects_only`, `concurrency_solvable=yes`, `recommended_option=A_plus_sparse`, plus `per_clone_mib`, `duplicated_gib`, `research_file`).

**The short version:** your instinct is right — per-workspace cloning is wasteful — but "one shared clone" bundles two separable problems, and only one of them is worth taking on now.

**What I verified on this machine (`athena`):**
- `sdd.storage: separate_repo` → SDD is its own repo (`sase-org/sdd`), **freshly network-cloned into every `sase_<N>/.sase/sdd`** (reflog confirms `clone: from github.com`, no hardlinks/alternates).
- **472 MiB per clone**; ~**3.3 GiB duplicated** across active workspaces right now; **~213 MiB network transfer per workspace prep**. Of each clone, 220 MiB is the shareable `.git` and **208 MiB is 171 research infographic PNGs** an implementing agent basically never reads — only ~44 MiB is live SDD text.

**The reframe that matters:** the per-workspace clone does *not* avoid concurrent writes — all 27 clones already push to the same `sase-org/sdd master`, and conflicts are mediated **at the remote** via `git pull --rebase`. So "share a clone" and "solve concurrent writes" are orthogonal. Today there is **no local lock** around SDD commits, the commit path has **no `index.lock` retry**, and push is a **single-shot** `push || (pull --rebase && push)`.

**Recommendation (Option A+):**
- Share the **object store**, not the working tree: workspaces do a **local hardlink/reference clone from one per-machine SDD mirror + fetch**, instead of a network clone. This kills the 213 MiB fetch and ~all the `.git` duplication **with zero change to the concurrency model** (trees stay private, remote-mediated as today).
- Add a **sparse checkout** dropping `research/**/*.png` → per-workspace SDD footprint goes from **472 MiB to well under ~50 MiB**.
- **Don't** share a single *working tree* in v1: it exposes the unguarded commit path to `index.lock` races, the `pull --rebase` rewrites a shared tree, and the `beads.db` delete-and-rebuild races. That path needs a machine-wide `flock` transaction + push retry loop + moving `issues.jsonl` single-writer serialization into `sase-core` (per the Rust boundary) — a much bigger change, reserved for later only if bead-aggregate merge pain shows up.

One nuance on beads: they're **event-sourced** (per-bead stream files don't collide; `manifest.json`/`beads.db` are regenerable), so the *only* genuine content-conflict surface is the Rust-owned `issues.jsonl` aggregate — which is where any single-writer guarantee belongs.

I'm folding one more detail — the exact workspace-prep clone code path — into the doc's implementation section as the background scan finishes; I'll confirm shortly.

I have a complete picture. Here are my findings.

## Summary: How SASE materializes the per-workspace SDD clone

### 1. Where the SDD store directory (physical path) is resolved

The physical path decision lives in **`src/sase/sdd/store.py`**, function `_sdd_dir_for_storage` (lines 361-370):

```python
def _sdd_dir_for_storage(workspace_dir, workspace_num, storage) -> Path:
    workspace = Path(workspace_dir)
    if storage == SDD_STORAGE_IN_TREE:
        return workspace / "sdd"                      # <workspace>/sdd
    if storage == SDD_STORAGE_SEPARATE_REPO:
        return workspace / ".sase" / "sdd"            # <workspace>/.sase/sdd  <-- your case
    primary = get_primary_workspace_dir(str(workspace), workspace_num)
    return Path(primary) / ".sase" / "sdd"            # <primary>/.sase/sdd (local mode)
```

So the three cases you asked about map exactly to the three branches: `separate_repo` -> `<workspace>/.sase/sdd` (workspace-local), `local`/auto-fallback -> `<primary>/.sase/sdd`, `in_tree` -> `<workspace>/sdd`.

Callers/entry points:
- `resolve_sdd_dir` (store.py:130-138) and `resolve_sdd_store` (store.py:141-159) both call `_resolve_sdd_storage` (store.py:340-358) to pick the storage enum, then `_sdd_dir_for_storage`. Note `resolve_sdd_store` sets both `sdd_dir` and `repo_root` to the same workspace-local dir (lines 153-159), and copies `provider`/`remote_url` from the store record only for `separate_repo`.
- `_resolve_sdd_storage` decides the enum: explicit config wins (line 349-350); else a materialized `sdd-store.json` record forces `separate_repo` (line 351-352); else provider policy -> `in_tree` or default `local` (line 354-357).
- `src/sase/sdd/_paths.py:get_sdd_dir` (lines 109-119) is a thin legacy shim delegating to `sdd_dir_for_in_tree_bool` (store.py:331-337), which only handles the boolean in_tree/local split — it does NOT produce the `.sase/sdd` separate_repo path; that comes only through `resolve_sdd_store`/`resolve_sdd_dir`.
- The storage enum/config resolution: `get_configured_sdd_storage` (store.py:108-127) reads `sdd.storage` from merged config.
- `SddStore`/`SddStoreRecord` dataclasses: `src/sase/sdd/_store_types.py:31-57`. The record is persisted as `sdd-store.json` (const at `_store_types.py:18`) in the **primary** workspace (read/written via `src/sase/sdd/_store_records.py`).

### 2. Where the separate_repo SDD clone is actually created

There are TWO distinct clone stages:

**A) Initial materialization into the PRIMARY** — done by the GitHub provider hook. The linked plugin is `sase-github_12` (resolved via `.venv/.../_editable_impl_sase_github.pth` -> `/home/bryan/.local/state/sase/workspaces/sase-org/sase-github/sase-github_12/src`).

`ws_materialize_sdd_store` in **`sase-github_12/src/sase_github/workspace_plugin.py:205-270`** clones the companion `--sdd` repo into the **primary** workspace, not the per-workspace dir:
```python
sdd_dir = Path(primary_workspace_dir).expanduser() / ".sase" / "sdd"   # line 235
...
cloned_remote_url = _clone_sdd_repo(owner, repo, sdd_dir, host=origin.host)  # line 264
```
- `_clone_sdd_repo` (workspace_plugin.py:944-959) clones to a temp dir then atomically renames into place.
- `_clone_gh_repo` (workspace_plugin.py:962-1004) runs plain `git clone <url> <target>` trying SSH then HTTPS (line 985). No `--reference`/`--shared`/`--depth`.
- The companion repo name is derived in `_companion_sdd_candidates`/`_companion_sdd_repo` (workspace_plugin.py:593-609); the provider declares `sdd_storage_policy="separate_repo"` in its workflow metadata (workspace_plugin.py:73).

This hook is dispatched from Python core via `_dispatch_materialize_sdd_store` (store.py:398-424) -> `sase.workspace_provider.materialize_sdd_store` -> pluggy `ws_materialize_sdd_store` (`_plugin_manager.py:89-99`, hookspec `_hookspec.py:190-202`).

**B) Per-workspace clone into `<workspace>/.sase/sdd`** — done by `ensure_workspace_sdd_clone` in **`src/sase/sdd/_store_link.py:19-76`** (public wrapper at store.py:320-328). This is the code that materializes the per-`sase_<N>` clone. Logic:
```python
workspace_sdd = workspace / ".sase" / "sdd"          # line 34 (target)
primary_sdd   = primary / ".sase" / "sdd"            # line 36 (source fallback)
...
cloned = False
if store.remote_url:
    cloned = _clone_sdd_store(store.remote_url, workspace_sdd)     # line 63-64: PREFER remote
if not cloned:
    cloned = _clone_sdd_store_from_primary(primary_sdd, workspace_sdd)  # line 66: fallback
    if cloned and store.remote_url:
        _set_sdd_origin(workspace_sdd, store.remote_url)           # line 68: fix origin
```
- `_clone_sdd_store` (_store_link.py:134-171): `git clone <remote_url> <workspace_sdd>` — a **fresh network clone** from the companion GitHub repo (the preferred path).
- `_clone_sdd_store_from_primary` (_store_link.py:174-221): fallback `git clone <primary/.sase/sdd> <workspace_sdd>` (a local clone from the primary's clone), then rewrites origin to the real remote.
- If the target already exists and matches the store remote (`_is_matching_store_clone`, lines 263-278), it is reused and only refreshed via `_sync_workspace_sdd_clone` (pull --rebase, or ff-only from primary) — lines 42-60, 79-93.

So: the per-workspace `.sase/sdd` is **cloned fresh** (network-first from the companion remote, local-clone-from-primary as fallback), NOT copied/rsynced. It targets the per-workspace `<workspace>/.sase/sdd`, not a shared location.

### 3. How `sase_<N>` workspace dirs themselves are created (copied vs cloned)

Managed-checkout creation lives in **`src/sase/workspace_provider/utils.py`**:
- `ensure_workspace_checkout` (lines 304-345) resolves the target dir via `WorkspaceStore.resolve(workspace_num)`, then calls `_ensure_git_clone_at`, records the workspace in the registry + writes a `checkout.json` marker, and finally calls `ensure_workspace_sdd_clone(checkout_dir, workspace_num)` (line 340-342) — i.e. the SDD clone is a separate step layered on top of the main-repo clone.
- `_ensure_git_clone_at` (lines 186-301) creates the `sase_<N>` main-repo checkout with a plain local clone:
  ```python
  git clone <primary_workspace_dir> <target_checkout_dir>   # lines 253-265
  git remote set-url origin <real_url>                      # lines 282-289
  git fetch --quiet                                          # lines 291-299
  ```
  `workspace_num <= 1` is treated as the primary and returned as-is (lines 210-215); existing valid checkouts are reused via `git status` probe (lines 217-226).

So the main repo is **cloned** (local `git clone` from the primary), not rsync-copied. The SDD store is **cloned fresh** afterward (section 2B). `.sase/` itself is not bulk-copied into the new checkout — it is kept untracked (see note at `src/sase/axe/run_agent_runner_setup.py:253`), and the SDD subtree under `.sase/sdd` is populated by its own clone.

Setup-path invocation: `src/sase/axe/run_agent_runner_setup.py:64-76` runs `prepare_workspace(...)` then `ensure_workspace_sdd_clone(workspace_dir, workspace_num)` (line 75). Other materialize callers: `run_agent_exec_plan_accept.py:291`, `plan_approval_actions.py:470`, `sdd/beads.py:91`, `main/sdd_handler.py:125/130/196`.

### 4. Existing object-store sharing / re-clone avoidance

There is **no** git-alternates / `--reference` / `--shared` / `--dissociate` / `--mirror` / local-mirror / cache-dir mechanism anywhere. Grep across both `src/sase` and the `sase-github_12` plugin for `--reference`, `--shared`, `--dissociate`, `alternates`, `objects/info/alternates`, `--mirror`, `--depth` returned nothing.

The only forms of re-clone avoidance that exist:
- **Implicit hardlinking**: the main-repo `git clone <local primary> <target>` (utils.py:253) is a local-path clone, so git hardlinks `.git/objects` by default — but this is git's implicit behavior, not an explicit SASE optimization, and it does not apply to the network-first SDD clone.
- **Reuse-if-present**: `ensure_workspace_sdd_clone` reuses an existing `<workspace>/.sase/sdd` when its origin matches the store remote (`_is_matching_store_clone`, _store_link.py:263-278) and just pulls/fast-forwards instead of re-cloning (`_sync_workspace_sdd_clone`, lines 79-93).
- **Local fallback clone from primary**: `_clone_sdd_store_from_primary` (_store_link.py:174-221) clones the SDD from the primary's on-disk clone (network-free) when the remote clone fails — again a full clone, not a shared object store.

Net: each `sase_<N>` gets its own full SDD clone at `<workspace>/.sase/sdd`, preferentially fetched over the network from the `sase-org/sdd` companion remote, with a local clone-from-primary fallback. No shared/alternates object store exists today.

Key files:
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/sdd/store.py`
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/sdd/_store_link.py`
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/sdd/_store_types.py`
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/sdd/_paths.py`
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/workspace_provider/utils.py`
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/workspace_provider/_hookspec.py`
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/axe/run_agent_runner_setup.py`
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase-github/sase-github_12/src/sase_github/workspace_plugin.py` (the linked GitHub plugin)

The clone-path scan confirms and sharpens the picture. Two findings materially strengthen the recommendation:

1. The **main-repo** workspace clone already does a **local `git clone` from the primary** (`utils.py:253`), which **hardlinks `.git/objects` by default** — so the main repo is already cheap. The **SDD clone is the lone outlier** doing a network-first clone.
2. There's already a **local-clone-from-primary path** for SDD (`_clone_sdd_store_from_primary` in `_store_link.py`) — it's just used only as a *fallback*. Phase 1 is largely "prefer that existing local/hardlinked path (sourced from a per-machine mirror or the primary) over the network clone."

Let me fold these exact citations into the doc.

Done. The clone-path scan confirmed the picture and let me pin down the exact code, which I've folded into the research doc.

## Final answer

**Research file:** `.sase/sdd/research/202607/shared_sdd_clone_per_machine.md` (enriched with verified code citations)
**Variables set** on `research.6.cld`: `shared_clone_recommended=yes_objects_only`, `concurrency_solvable=yes`, `recommended_option=A_plus_sparse` (+ `per_clone_mib=472`, `duplicated_gib=3.3`, `research_file`).

*(No `just check` needed — the only change is a new markdown file under `sdd/research/`, which is an explicit exception in CLAUDE.md.)*

### Is the shared-clone idea good? — Yes, if you share the object store, not the working tree.

The clone-code scan surfaced the cleanest possible fix: **the SDD clone is the lone outlier.** The *main-repo* workspace clone already does a local `git clone` from the primary (`workspace_provider/utils.py:253`), which hardlinks `.git/objects` for free. Only the SDD clone (`sdd/_store_link.py:19-76`) does a **network-first** clone from GitHub — and it *already has* a local-clone-from-primary path (`_clone_sdd_store_from_primary`), used today only as a fallback.

So **Phase 1 is small and low-risk**: in `ensure_workspace_sdd_clone`, prefer a local hardlink clone from a per-machine SDD mirror (reusing existing machinery) and demote the network clone to "no local source." Add a sparse checkout dropping the 208 MiB of research PNGs. Result: per-workspace SDD footprint **472 MiB → under ~50 MiB**, no network fetch, and **zero change to the concurrency model**.

### Can we solve concurrent writes? — Already mostly solved; keep it that way.

The reframe is the important part: concurrency is **already** handled today at the *remote* — all ~27 private clones push to the same `master` and reconcile via `pull --rebase`. Sharing only the *object store* keeps that intact.

Sharing a single *working tree* is the tempting-but-risky path, because the current code has **no local lock** around commits, **no `index.lock` retry**, a **single-shot** push, and a **delete-and-rebuild `beads.db`** that races in a shared dir. If you ever want it (the one upside: a single `issues.jsonl`, no bead-aggregate merges), it needs a machine-wide `flock` transaction + push retry loop + moving `issues.jsonl` single-writer serialization into `sase-core` (which already owns it — aligns with the Rust boundary). I've documented that as Phase 3–4, to do only if bead-merge pain actually shows up.

Bottom line: **take the disk/latency win now via shared objects + sparse checkout; leave concurrency mediated at the remote as it is today.**
