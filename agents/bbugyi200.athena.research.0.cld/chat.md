# Chat History - ace-run

- **TIMESTAMP:** 2026-07-07 22:29:46 EDT
- **MODEL:** claude/opus
- **AGENT:** research.0.cld
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260707_221544.md`

## Prompt

%name:research.@.cld %m:@research_assist %g:research #gh:gh_sase-org__sase We currently store all plans, prompts, research markdown files, and sase beads directly in this repo in the sdd/ directory. This results in a very large number of git commits that are not related to the code. This clutters the git history. I would like to start using a separate GitHub repo for these files per project. We should search for this repo in the same GitHub organization in a repo named either `sdd` or `<project>-sdd`, where `<project>` is the name of the main repo (`sase` in the case of this repo). Each VCS type should be able to opt in to this behavior. BareGit repos should continue to use the old behavior but the GitHub VCS should opt in. Can you do some research to help me understand the best way to implement this? End your analysis with a recommended approach. Write this research to a new markdown file under the sdd/research/$(date +%Y%m)/ directory.


## Response

I'll research this properly. Let me start by orienting myself in the codebase, then fan out parallel exploration into the key subsystems involved.

Let me read the SDD README and core VCS abstraction files while I fan out exploration agents in parallel.

This gives me a clear picture of the workspace_provider hook architecture. Now let me fan out focused exploration agents in parallel to understand the key subsystems, while I continue reading core files myself.

I'll investigate the SASE codebase systematically. Let me start with parallel searches for `sdd/` path references and the relevant CLI/commit files.

This is a large codebase with a dedicated `sase.sdd` package. Let me explore that package and the key files in parallel.

I'll investigate the workspace_provider plugin architecture. Let me start by exploring the directory structure and reading the key files in parallel.

The central path resolver is `get_sdd_dir`. Let me read the core sdd files: `files.py`, `beads.py`, `_commit.py`, `_write.py`, `links.py`, `__init__.py`.

Let me read the core plugin infrastructure files in parallel.

Now let me read `_write.py`, `links.py`, `bead/project.py`, and the commit_finalizer, plus find CLI entry points.

I'll investigate the linked repositories mechanism in the SASE codebase. Let me start by exploring the structure and searching for relevant code.

Now let me read the registry files and the VCS provider detection module.

While the agents work, let me open the `sase-github` linked repo to understand the GitHub VCS provider and how it discovers repos in an org — central to the "search for `sdd`/`<project>-sdd`" requirement.

Now let me find the CLI entry points and the `commit_sdd`/`write_sdd` plan-chain step handlers, plus the beads sync and commit_finalizer_git logic.

Let me read the key files for linked repos, config, and workspace handling.

There's a separate `vcs_provider` module. Let me read its detection code, hookspec, and registry, plus find `detect_vcs`.

Now let me read the VCS hookspec, bare_git VCS plugin, entry point config in pyproject.toml, and the bare_git workspace plugins.

Let me examine the plan-accept write path, the effect-string executor, the main CLI dispatch, and the beads sync/commit-finalizer-git logic.

Now let me examine the workspace CLI command implementation and config schema.

Let me read the entry-points section of pyproject.toml and the bare_git workspace plugins.

Let me read the config files, schema, workspace_handler_list, and the workspace_provider store/utils.

Important lead: `ws_get_workspace_directory` in bare_git_workspace.py calls `ensure_bare_git_sdd_initialized` from `sase.sdd.files`. This is directly relevant to the "SDD docs in a separate repo" feature. Let me read the remaining bare_git plugins and investigate the SDD module.

Let me read the schema's linkedRepo definition, the sase.yml, and the workspace_provider store/utils.

Let me find the version-controlled `_commit_sdd_files` helper and read the beads sync, commit_finalizer_git, and CLI handlers.

Let me read the schema's linkedRepo definition and the workspace store for how numbered dirs are derived.

Now let me investigate the SDD module (the key lead for "SDD docs in a separate repo"), find the sase-github repo, and search for the commit workflow and any per-VCS capability flags.

Let me read the version-controlled `_commit_sdd_files` helper, beads `sync.py` git_sync, and the bead/sdd CLI handlers.

Let me read the version-controlled SDD commit path (`commit_sdd_files_for_exec_plan`) and the CLI handlers for sdd/plan/bead.

Let me check how linked repos and VCS config are declared, and look at the config structure while agents continue.

Let me examine the agent launch integration, the memory-roots generation, and the commit workflow for linked repos.

Now let me read the CLI parsers/handlers for sdd, plan, and bead commands, plus bead cli_common.

Let me examine the SDD module (highly relevant to the end goal) and the linked-repo memory config.

This is the key mechanism. Let me check the config schema for `linked_repos` and any VCS opt-in patterns, then I'll wait for the exploration agents.

Let me check for any `bd` binary subprocess, the config defaults for `sdd.version_controlled`, and the plan-propose write path plus precommit hooks.

Let me examine the SDD storage mechanism, which is directly relevant to the SDD-docs-repo goal.

Let me check how commits and reverts handle linked repos, to answer whether they're committed independently.

Let me read the plan propose handler, precommit hooks, plan_paths, plan_approval_choices, and check the repo .gitignore for beads.

Let me read the commit finalizer state to confirm how linked repos are committed.

Two plugin systems exist: `workspace_provider` (`ws_*` hooks) and `vcs_provider` (`vcs_*` hooks). Let me read the `vcs_provider` hookspec to complete my picture of extension points while agents finish.

I have a thorough understanding now. Let me verify one detail about the current workspace numbering and how the SDD directory currently sits.

Let me pinpoint the single most important design lever — where the `sdd/` root path is resolved — since redirecting it is central to the recommendation.

Let me verify the beads commit history, check whether `sase bead create/update` auto-commit, and read the remaining CLI/hook pieces.

Interesting — there's already a `get_sdd_dir(workspace_dir, 1, version_controlled)` with a `version_controlled` flag and a `.sase/sdd` (non-VC) variant. This is a major find. Let me read the SDD path resolution module.

Let me confirm whether `sase bead` CRUD auto-commits or only stages, and check the beads doctor path assumptions.

`sdd.version_controlled` config flag already exists, and there's an `sdd/_commit.py`. This is the crux of the design. Let me read the path resolver, the SDD commit flow, and the current config value.

Let me read the precommit hooks and bead conflict resolver to complete the commit picture.

Now the picture is crisp: `version_controlled: true` → committed to main repo's `sdd/` (current pain); `false` → machine-local `.sase/sdd/` (not shared). The user wants a **third mode**: separate git repo. Let me read the SDD commit flow, the beads path logic, and confirm the current config value.

I now have a complete picture. Let me do one final check on the config loading layer and the `_SDD_PLAN_DIRS` diff-badge constant to round out the inventory.

Major discovery: `commit_sdd_files` **already** auto-commits SDD into a local `.sase/sdd/` git repo when `version_controlled: false`. So a "separate SDD repo" is partially built — it just lacks remote discovery/clone/push. Let me confirm the current config value and trace who calls these functions and who decides VC-vs-non-VC.

Confirmed: this repo sets `sdd.version_controlled: true`. Let me trace the callers that branch on this flag and who triggers SDD commits, then check on my exploration agents.

Excellent leads. There are multiple `detect_vcs(...) == "bare_git"` per-VCS-type checks. Let me read the SDD files module, beads.py, and the SDD commit code.

The model is now fully clear. Let me verify one more thing relevant to the "search for the repo" requirement — whether the GitHub plugin has any repo-existence/creation capability — then I'll consolidate with the exploration agents' findings.

This confirms the pattern. `get_effective_sdd_config()` in `sase/sdd/beads.py:18-33` is precisely a per-VCS-type capability check hard-coded as `detect_vcs(...) == "bare_git"`. Let me read the SDD commit code, commit_instructions.py, and check the sase-github search result.

Let me locate the sase-github package and examine the commit workflow entry point and config schema.

Let me read the beads push machinery — it's the existing template for pushing a standalone `.sase/sdd` repo to a remote, directly relevant to the recommendation.

I now have a complete picture. Here is my report.

---

# Linked Repositories in SASE — Investigation Report

Everything below is from real code in the current workspace (`.../sase/sase_11`, which is itself workspace number **11** — a `sase_<N>` clone of `git@github.com:sase-org/sase.git`).

## Executive summary

"Linked repositories" is a mature, first-class feature. A project's `sase.yml` declares a list of related repos (`linked_repos`), each resolved to a **workspace-number-matched git clone** that shares the *same* `<N>` as the primary repo's ephemeral workspace. Agents open them with `sase workspace open`, and each linked repo is **committed independently** (its own branch/commit via the finalizer), not folded into the primary's commit.

Crucially for your goal: an **SDD docs repo is NOT currently a linked repo**. SDD lives *inside* the primary repo at `sdd/` (when `sdd.version_controlled: true`) or in `.sase/sdd` otherwise — see `get_sdd_dir` in `src/sase/sdd/_paths.py:108`. The linked-repo machinery is, however, the cleanest existing vehicle to model a second GitHub repo. Details and recommendation at the end.

---

## 1. How linked repositories are configured

**Canonical module:** `src/sase/linked_repos.py`. The docstring (lines 1-8) states `linked_repos` is the public key; `sibling_repos` is a deprecated alias parsed during a compatibility window; `src/sase/sibling_repos.py` is a thin re-export shim (whole file, 1-41).

**Config keys** (`src/sase/linked_repos.py:36-37`):
```
LINKED_REPOS_CONFIG_KEY = "linked_repos"
SIBLING_REPOS_CONFIG_KEY = "sibling_repos"   # deprecated alias
```

**Default value:** `linked_repos: []` in `src/sase/default_config.yml:4`.

**This repo's actual config** — `sase.yml:14-26`:
```yaml
linked_repos:
  - name: sase-core
    path: ../sase-core
    description: Shared Rust core backend ...
  - name: sase-github
    path: ../sase-github
    description: GitHub VCS and workspace provider plugin ...
  - name: sase-telegram
    path: ../sase-telegram
    description: Telegram integration plugin ...
  - name: sase-nvim
    path: ../sase-nvim
    description: Neovim integration plugin ...
```
(I confirmed `../sase-core`, `../sase-nvim`, `../sase-telegram` exist on disk as sibling checkouts next to `sase_11`.)

**Fields of a linked-repo entry** — the JSON Schema definition `linkedRepo` in `src/sase/config/sase.schema.json:8-42`:
- `name` (**required**, minLength 1): "Stable alias used in prompts, metadata, and `SASE_LINKED_REPO_<NAME>_DIR` env vars."
- `path` (**required**): "Primary checkout path. Relative paths are resolved from the project's primary `WORKSPACE_DIR`."
- `description` (**required**): "Human-readable purpose used when generating agent memory."
- `workspace.strategy` (optional): enum `["suffix", "none"]`, default `"suffix"` (schema lines 28-40).

Note there is **no `url` and no `vcs` field** — a linked repo is identified purely by a local filesystem `path`. VCS type is inferred (git detection via `subprocess git rev-parse` in `src/sase/main/workspace_handler_context.py:468-479`). The `linked_repos` / `sibling_repos` array schemas are at `src/sase/config/sase.schema.json:958-973`.

**Where config is read:**
- Resolution for launched agents: `resolve_linked_repos_for_project()` → `_resolution_config()` → `load_merged_config()` merged with a project-local `sase.yml` (`src/sase/linked_repos.py:301-326`, `410-423`, `515-523`).
- Cross-key merge (canonical wins over legacy, dedupe, warnings): `_merged_entries_from_config()` (`src/sase/linked_repos.py:441-498`).
- Memory generation reads it separately: `linked_entries_from_config()` (`src/sase/main/init_memory/config.py:194-270`), preferring `linked_repos` then `sibling_repos` (`_linked_repos_raw`, lines 179-191). Here `name`, `description`, `path` are all **required** or memory generation errors out (lines 220-238).

---

## 2. `sase workspace open` implementation

**CLI parser:** `src/sase/main/parser_workspace.py:52-85` defines the `open` subcommand: positional `workspace_num`, `-p/--project`, **required** `-r/--reason`, plus compat flags `-P/--print` and `-c/--clean`.

**Dispatch:** `handle_open_command` (`src/sase/main/workspace_handler_commands.py:72-82`) → `handle_open_clean` in `src/sase/main/workspace_handler_list.py:172-231`. That function:
1. Validates the non-empty reason (`_normalize_workspace_open_reason`, lines 30-41).
2. Resolves the project to a `ProjectContext` (see below).
3. Initializes SDD generated files for the bare-git checkout (`ensure_bare_git_sdd_initialized`, line 196).
4. **Materializes the checkout** via `resolve_checkout(ctx, workspace_num, materialize=True)` → `resolve_checkout_path` (lines 126-144) → `ensure_workspace_checkout(...)`.
5. Cleans/prepares the checkout on the default branch (`prepare_workspace`, lines 207-217).
6. If the project is a linked repo, records the open: `record_opened_linked_repo(ctx.project_name, path, reason=..., opened_at=...)` (lines 220-228).
7. Prints the prepared path (line 230).

**How a linked-repo *name* is resolved to a filesystem path** — the important part, in `src/sase/main/workspace_handler_context.py`:
- `resolve_project_context()` (lines 43-116). When you pass `-p sase-core`, that project has no local ProjectSpec/`WORKSPACE_DIR`, so it falls into `_materialize_sibling_project_context()` (lines 119-161).
- `_configured_linked_repo()` (lines 210-257) resolves the name: first checks env (`SASE_LINKED_REPOS_JSON` via `_linked_repo_project_from_env`, lines 260-270), else calls `resolve_linked_repos_for_project(project_file=<current project>, workspace_num=0, materialize=False)` on the **current** project's config and matches by `repo.name` (lines 233-257). This is why `sase workspace open -p <linked_repo>` must be run from inside the primary repo's workspace — the current project's `sase.yml` supplies the linked-repo table.
- It validates the primary path exists and is a git checkout (`_validate_linked_repo_primary`, lines 292-310), then **stamps a synthetic ProjectSpec** with `PROJECT_STATE: sibling` and `WORKSPACE_DIR: <linked primary>` (`_ensure_sibling_project_spec`, lines 379-411; metadata built in `_sibling_project_metadata`, 349-376, which can also carry `BARE_REPO_DIR`). The lifecycle state is literally named `sibling` (legacy backing state for linked-repo bookkeeping — noted at lines 128-131).
- A `WorkspaceStore` is built on the linked repo's primary dir, and the command then materializes workspace `<N>` for it.

So the mapping is: **linked-repo `name` → configured `path` (its primary checkout) → `WorkspaceStore(primary).resolve(N)` → git clone at `<primary>_<N>`.**

---

## 3. How a numbered `sase_<N>` workspace is created for primary + linked repos

**Numbered-dir derivation** lives in `src/sase/workspace_provider/store.py`. `WorkspaceStore.resolve(workspace_num)` (lines 318-372):
- `num == 0` (or legacy `1` under adjacent) → the primary checkout itself (materialization `"primary"`).
- Otherwise the checkout dir is `<root>/<project_basename>_<num>/` (xdg-state/absolute roots, lines 361-372) or `<primary>_<num>/` (adjacent legacy, lines 345-355). `project_basename` is the basename of the primary dir (line 296). That is exactly why this repo's dir is `sase_11` (basename `sase`, num `11`).
- Root policy is from `workspace.root` config (`default_config.yml:375-384`): `xdg-state` (default), `adjacent`, or an absolute path; `SASE_WORKSPACE_ROOT` overrides (`_resolve_root`, store.py:210-247). project_key namespacing derives from the git remote `<owner>/<repo>` for GitHub (`_derive_project_key`, lines 145-174) — here `sase-org/sase`.

**Materialization (actual clone):** `ensure_workspace_checkout()` in `src/sase/workspace_provider/utils.py:304-339` → `_ensure_git_clone_at()` (lines 186-301) does `git clone <primary> <target>`, resets the origin URL to the real remote, and fetches. It also records a registry entry + checkout marker for managed roots (`_record_managed_workspace`, lines 342-361).

**The tie between primary and linked = the same `workspace_num`.** At agent launch, `resolve_linked_repos_for_project(..., workspace_num=workspace_num)` is called with the primary's `<N>` (`src/sase/agent/launch_spawn.py:189-197`). Inside, each linked repo's path is resolved via `_resolve_workspace_dir(primary_dir, workspace_num=<same N>, strategy, ...)` (`src/sase/linked_repos.py:556-580`), which calls `ensure_workspace_checkout(primary_dir, <same N>)`. So primary `sase_11` pairs with `sase-core_11`, `sase-github_11`, etc. — same N.

Two special cases in `_resolve_workspace_dir` (linked_repos.py:564): `strategy == "none"` OR `workspace_num <= 1` returns the primary path directly (no per-workspace clone). Strategy `"none"` = the "static linked repo" mode.

**Env exposed to the agent** (`LinkedRepoResolution.to_env`, `src/sase/linked_repos.py:78-95`):
- `SASE_LINKED_REPOS_JSON` (+ legacy `SASE_SIBLING_REPOS_JSON`) — full JSON array of resolved repos.
- Per repo: `SASE_LINKED_REPO_<NAME>_DIR` (the workspace-matched dir) and `SASE_LINKED_REPO_<NAME>_PRIMARY_DIR` (+ `SASE_SIBLING_REPO_*` aliases). Applied in launch via `apply_linked_repo_env` (launch_spawn.py:244-246); stale inherited values are scrubbed first (`scrub_linked_repo_env`, linked_repos.py:98-115).

The generated agent memory documents the whole flow to agents — `src/sase/main/init_memory/roots.py:69-110` renders the "## Linked Repositories" section including the exact instruction:
```
sase workspace open -p <linked_repo> -r "<reason>" <workspace_num>
```
with the note that `<workspace_num>` must match the primary repo's number (lines 96-107).

---

## 4. Are linked repos committed/managed independently?

**Yes — each linked repo commits on its own, sharing the same overall flow but as a separate `cd` + commit.** The commit finalizer treats them as distinct dirty repos:

- Discovery: `collect_dirty_state()` in `src/sase/llm_provider/commit_finalizer_state.py:34-86` builds a `main` `DirtyRepo` plus one `DirtyRepo(kind="sibling")` per dirty linked repo (`_dirty_configured_sibling_repos`, lines 95-130). Targets come from env (`SASE_LINKED_REPOS_JSON`) or config (`_configured_sibling_targets`, lines 204-265).
- Only linked repos the agent **actually opened** (recorded by `record_opened_linked_repo` during `sase workspace open`) are "blocking" candidates — see `opened_linked_repo_names` / `opened_linked_repo_workspace_dirs` consumption (lines 54-66; `_blocking_sibling_candidates`, 133-165). The opened-marker files are `opened_linked_workspaces.json` (+ legacy `opened_siblings.json`) written under `SASE_ARTIFACTS_DIR` (`src/sase/linked_repos.py:26,153-194`).
- Instructions produced for the agent (`src/sase/llm_provider/commit_finalizer_prompting.py:66-98`) literally tell it, per linked repo: ``For `<name>`, run `cd <path>` before using your /sase_git_commit skill`` and to verify `git status` is clean afterward (lines 75-84). So each linked repo gets its **own commit on its own branch** in its **own `<name>_<N>` clone**.
- `strategy: none` (static) repos are **advisory only** — uncommitted changes there don't fail the finalizer (`_dirty_configured_advisory_sibling_repos`, state.py:168-201; prompting lines 86-98).

**Revert** is likewise per-repo: `src/sase/ace/revert_agent_workspace.py` claims a fresh workspace, prepares the primary branch, then materializes and prepares each **suffix-strategy** linked repo the agent touched (`_resolve_linked_checkouts`, lines 284-308; only `workspace_strategy == "suffix"` participate). Reverts run per repo (`RepoRevertPlan` / `RevertRepo`).

So: shared *lifecycle/tooling* (same `<N>`, same finalizer pass, same `/sase_git_commit` skill), but **independent git commits/branches/pushes** per repository.

---

## 5. Config schema & sase.yml structure (VCS / workspace / linked-repo)

- **`linked_repos`** — array of `linkedRepo` (`sase.schema.json:958-965`); `sibling_repos` deprecated alias (966-973). Default `[]` (`default_config.yml:4`).
- **`workspace`** — `default_config.yml:375-384`: `root` (`xdg-state`|`adjacent`|abs path), `project_key`, `cleanup_ttl_days`. Consumed by `WorkspaceStore` (store.py:250-296).
- **`vcs_provider`** — `default_config.yml:346-349`: `provider: auto`, `use_project_pr_prefix`, `pr_tags`; this repo also sets `vcs_provider.default_hooks` (`sase.yml:7-12`).
- **`sdd`** — `default_config.yml:372-373`: only `version_controlled: bool` (schema `sase.schema.json:974-985`). This repo sets `sdd.version_controlled: true` (`sase.yml:4-5`).
- Dataclasses/models: `_ResolvedLinkedRepo` and `LinkedRepoResolution` (`src/sase/linked_repos.py:43-95`); `LinkedRepoMemoryEntry` / `WorkspaceStrategy` (referenced from `src/sase/main/init_memory/models.py`, used in config.py:17,254-262); `SiblingTarget` / `DirtyRepo` (`src/sase/llm_provider/commit_finalizer_types.py`); `WorkspacePath` / `WorkspaceStore` (store.py:36-45, 260+); `ProjectContext` / `_LinkedRepoProject` (workspace_handler_context.py:24-40).

---

## End goal: can an "SDD docs repo" be modeled as a linked repo?

**Current SDD reality:** SDD is not a separate repo. `get_sdd_dir()` (`src/sase/sdd/_paths.py:108-120`, mirrored in `files.py:76-84`) returns `<workspace_dir>/sdd` when `sdd.version_controlled: true`, else `<primary>/.sase/sdd`. I confirmed `sdd/{prompts,tales,epics,legends,myths,research,beads,assets}` all live inside this primary repo. So SDD docs are committed *with* the primary repo today.

**Assessment of the linked-repo path.** A linked repo is already exactly "a second repo attached to a project, materialized at the matching `<N>`, committed independently." An SDD-docs repo maps onto it cleanly:

Strengths:
- Zero new concept: add `{name: <project>-sdd, path: ../<project>-sdd, description: ...}` to `linked_repos`. It would get `SASE_LINKED_REPO_<NAME>_DIR`, workspace-matched clones, and its own independent commit flow for free.
- `strategy: suffix` gives isolated per-agent clones + blocking commits (agent must `cd` and commit SDD changes). `strategy: none` gives a single shared static path with advisory (non-blocking) commits — closer to "docs I edit in place."

Gaps you'd have to bridge (why it's not a perfect drop-in):
1. **No auto-discovery.** Linked repos are explicit `path` entries only — there is no "look for `<project>-sdd` in the same GitHub org" logic anywhere. `_derive_project_key`/`_normalize_git_url` (store.py:80-174) know the org (`sase-org`), so auto-discovering `sase-org/<repo>-sdd` is feasible, but it would be **new code**. There is no `url` field and nothing clones from a remote org today — linked repos assume the primary checkout already exists locally at `path` (validated at linked_repos.py:365-370 and workspace_handler_context.py:298-303).
2. **SDD path resolution is hard-coded to the primary workspace.** All of `sase.sdd` computes SDD paths relative to the primary/`.sase` (`_paths.py:108-153`), and `sase workspace open` even auto-initializes SDD inside the *primary* checkout (`workspace_handler_list.py:194-201`). To make SDD live in a second repo you'd need `get_sdd_dir()` (and `find_sdd_file`, `sdd_kind_roots`) to redirect into the linked repo's resolved dir. That's the real integration work, independent of the linked-repo plumbing.
3. **Naming/state overloading.** The backing lifecycle state for any attached repo is literally `PROJECT_STATE: sibling` (workspace_handler_context.py:379-411; project file minted at `src/sase/workflows/commit/project_file_utils.py:95-98`). An SDD repo would reuse that same "sibling" machinery, so it wouldn't be distinguishable from a code sibling without a new marker.

**Cleanest recommendation:**
- **Reuse the linked-repo mechanism as the transport** (materialization, `<N>` matching, independent commit/revert are all solved), rather than inventing a parallel numbered-clone system.
- Add a small amount of new concept on top: (a) an optional discriminator on a linked-repo entry (e.g. a `role: sdd` field on `linkedRepo` in `sase.schema.json:8-42`, defaulting absent) so SDD path resolution can find *which* linked repo holds docs; and (b) teach `sase.sdd._paths.get_sdd_dir` to return that linked repo's resolved workspace dir when present. Auto-discovery of `<project>-sdd` in the same org would be an additive convenience layered on `_derive_project_key` (store.py:145-174) that, when it finds/clones the repo, synthesizes the `linked_repos` entry — but note nothing currently clones a linked repo *from a remote*, only from an existing local primary, so remote auto-clone is genuinely new behavior.

Net: an SDD docs repo is best modeled as a **special-role linked repo** (small new `role`/discovery layer) rather than a brand-new attachment concept — the heavy lifting (second numbered clone, independent commits, env exposure, agent memory instructions) already exists in `src/sase/linked_repos.py`, `src/sase/workspace_provider/store.py`, and the commit finalizer.

The linked-repo agent delivered a thorough report. Two exploration agents remain (SDD write/commit flow, VCS plugin architecture). Let me wait for them — they're central to the recommendation.

I have a strong first-hand picture. `get_effective_sdd_config()` is the central VC-vs-non-VC decision chokepoint. Let me wait for the two remaining exploration agents (SDD commit flow inventory + VCS plugin architecture) before synthesizing.

I have thoroughly traced the SDD storage and commit architecture. Here is the complete map.

## Executive summary

SASE has **two SDD storage modes**, switched by the `sdd.version_controlled` config flag:

- **VC mode** — SDD lives at `<repo>/sdd/` **inside the main repo working tree** and is committed to the main repo's git. This is what *this* repo uses (`sase.yml:5` sets `version_controlled: true`).
- **Non-VC mode (default)** — SDD lives at `<primary_workspace>/.sase/sdd/` as a **separate standalone git repo** (`.sase/sdd/.git`, created via `git init`). This is the shipped default (`src/sase/default_config.yml:373` → `false`).

The single decision point is `get_effective_sdd_config()` (`src/sase/sdd/beads.py:18`), and the single path resolver is `get_sdd_dir()` (`src/sase/sdd/_paths.py:108`, mirrored at `src/sase/sdd/files.py:76`). The non-VC mode already proves the "separate repo" design; VC mode is the one that embeds `sdd/` in the main working tree.

---

## 1. Where `sdd/` paths are constructed

**Central definitions (the canonical places):**

- `src/sase/sdd/_paths.py:108` `get_sdd_dir(workspace_dir, workspace_num, version_controlled)` — THE base-path resolver:
  - VC: `Path(workspace_dir) / "sdd"` (main working tree)
  - non-VC: `primary_workspace / ".sase" / "sdd"`
  - Duplicated verbatim as a facade at `src/sase/sdd/files.py:76`.
- `src/sase/sdd/_paths.py:7-15` `_SDD_CANONICAL_DIRS = {prompts, tales, epics, legends, myths, research, beads}` — the canonical child-dir set.
- `src/sase/sdd/_paths.py:30` `sdd_kind_roots()` and `:49` `find_sdd_file()` — resolve `base_dir/"sdd"/kind` plus legacy `base_dir/kind` aliases.
- `src/sase/bead/project.py:39` `BEADS_DIRNAME = "sdd/beads"` and `:42` `BEADS_DIRNAME_NON_VC = "beads"` — THE beads subdir constant.
- `src/sase/sdd/links.py:39-46` `resolve_sdd_root()` — probes `base/"sdd"` then `base/".sase"/"sdd"`, defaulting to `base/"sdd"`.

**The literal `sdd/` write target (`sdd_dir / kind / YYYYMM`)** is built in `src/sase/sdd/_write.py:43-49` (`write_sdd_files`): `sdd_dir/"prompts"/yyyymm` and `sdd_dir/<plan_kind>/yyyymm`.

**Scattered hardcoded `sdd/`-in-working-tree literals** (these assume `Path.cwd()`/workspace root, i.e. the main repo tree):

- `src/sase/ace/tui/actions/_startup_watchers.py:53` — `Path.cwd() / "sdd" / "beads"`
- `src/sase/ace/tui/actions/event_refresh/_artifact_delta.py:38` — `Path.cwd() / "sdd" / "beads"`
- `src/sase/ace/tui/actions/event_refresh/_watcher.py:86` — `Path.cwd() / "sdd" / "beads"`
- `src/sase/workflows/commit/precommit_hooks.py:199` — `os.path.join(cwd, "sdd", "tales", yyyymm, ...)`
- `src/sase/workflows/commit/plan_paths.py:70` — special-cases `.sase/sdd` prefix
- `src/sase/ace/tui/models/_diff_badge.py:16,26` — `_SDD_PLAN_DIRS = {prompts, tales, epics, legends}`, matched under a leading `sdd` segment
- `src/sase/ace/revert_agent_models.py:7` — `_SDD_PATH_PREFIX = "sdd/"`
- `src/sase/llm_provider/commit_finalizer_git.py:14-19` — `_SDD_PLAN_DIR_PREFIXES = ("sdd/tales/", "sdd/epics/", "sdd/legends/", "sdd/myths/")`
- `src/sase/main/bead_fast_path.py:12` — `_BEADS_DIRNAME = "sdd/beads"` (a second literal copy of the constant)
- Path-tail checks assuming `sdd/beads` or `.sase/sdd/beads`: `src/sase/integrations/_mobile_helper_beads.py:251,253,414,416`; `src/sase/agent/bead_display.py:192,195`; `src/sase/doctor/checks_beads.py:106,117`.

**Config wiring:** `src/sase/sdd/beads.py:12-15` `get_sdd_config()` reads `config["sdd"]["version_controlled"]` via `load_merged_config()`; default `false` at `src/sase/default_config.yml:372-373`; this repo overrides to `true` at `sase.yml:4-5`. Config init/toggle logic lives in `src/sase/main/sdd_init_config.py` (writes `sdd.version_controlled: true` into `sase.yml`).

---

## 2. How `sase sdd`, `sase plan`, `sase bead` write files

**`sase sdd`** (`src/sase/main/sdd_handler.py`): subcommands are `init`, `validate`, `links`, `list`, `repair-links` — these are **read/validate/scaffold only**. `init` (`run_sdd_init`, `:40`) writes generated README/directory-map guide files via `ensure_sdd_initialized` and flips the config flag; it does **not** write plans/prompts. Validation/list/links resolve the root via `resolve_sdd_root`.

**`sase plan`** (`src/sase/main/parser_plan.py`, handlers in `src/sase/main/plan_*_handler.py`):
- `sase plan propose <file>` (`src/sase/main/plan_propose_handler.py:15`) does **not** write into `sdd/`. It moves the scratch plan into the machine-local archive `~/.sase/plans/` (`move_plan_to_sase`, `:58`) and drops a `.sase_plan_pending` marker for approval.
- The actual `sdd/` write happens at **plan approval**. `sase plan approve --kind tale|epic|legend` maps to the same transition that the ACE UI uses. The write is executed in `src/sase/axe/run_agent_exec_plan_accept.py:276-355`:
  - resolves `version_controlled` (`:292`), `sdd_dir = get_sdd_dir(...)` (`:293`),
  - `write_sdd_files(sdd_dir, name, expanded_prompt, plan_file, plan_kind=...)` (`:309`) writes `sdd/prompts/YYYYMM/<name>.md` + `sdd/<kind>/YYYYMM/<name>.md`.
  - The consequence text is defined in `src/sase/plan_approval_choices.py:141,160,179` ("Commit to sdd/tales / sdd/epics / sdd/legends").
- The CLI-triggered archive-to-`sdd/` also appears in `src/sase/plan_approval_actions.py:306-349` (`_archive_plan_for_approval`), which builds `sdd_dir / plan_kind / get_yyyymm()` the same way.
- **Directory target:** always the result of `get_sdd_dir()`, i.e. the working tree in VC mode, `.sase/sdd` in non-VC mode. It is configurable only through the `version_controlled` flag — there is no independent "sdd root" override for writes.

**`sase bead`** (`src/sase/bead/cli*.py`; parser at `src/sase/main/parser_bead.py`, fast path `src/sase/main/bead_fast_path.py`): all writes go through `get_project()` → `find_beads_location()` (`src/sase/bead/cli_common.py:15-53`), which returns `(root, "sdd/beads")` in VC mode or `(primary/.sase/sdd, "beads")` in non-VC mode. `BeadProject` then writes issues.jsonl/beads.db/events into that dir (see §4).

---

## 3. How `sdd/` files get committed to git

SDD artifacts are committed in **their own dedicated commits, separate from code commits.** The git log confirms this pattern: `chore: Add SDD prompt and plan for <name>` and `chore(beads): close sase-5i.5` are distinct from the `feat(...)`/`fix(...)` code commits.

There are **three distinct commit paths**, chosen by mode:

1. **VC-mode plan/prompt commit** — `src/sase/axe/run_agent_exec_plan_sdd.py:14` `commit_sdd_files_for_exec_plan()`. It finds the prompt+plan via `find_sdd_file` and shells out to **`sase commit -M <msgfile> -f <file> -f <file>`** (`:53`) in the workspace, message `chore: Add SDD prompt and plan for <name>` tagged type `sdd`. Called from `run_agent_exec_plan_accept.py:345` via the wrapper `_commit_sdd_files` (`:74`). This commits SDD files into the **main repo working tree** (a separate commit, done *before* the code commit so the `#gh` pre-step `git checkout . && git clean -fd` doesn't wipe them, per the docstring `:22-29`).

2. **Non-VC-mode plan/prompt commit** — `commit_sdd_files()` in `src/sase/sdd/_commit.py:180`. Runs `git add`/`git commit` **inside the standalone `.sase/sdd/.git` repo** (`sdd_dir/".git"` guard at `:191`). Called at `run_agent_exec_plan_accept.py:326,351`. Message tagged via `apply_auto_commit_tags_with_runtime(..., auto_commit_type)`.

3. **SDD init/scaffold commit** — `ensure_bare_git_sdd_initialized()` (`src/sase/sdd/_commit.py:229`) → `commit_bare_git_sdd_init_paths()` (`:318`), a "Initialize SDD" commit of only the generated guide files, used for SASE's built-in bare-git local-remote workspaces.

**`commit_finalizer.py` (the stop-hook finalizer):** Its only SDD-specific behavior is `auto_commit_done_sdd_plan_status()` (`src/sase/llm_provider/commit_finalizer_git.py:61`), invoked from `commit_finalizer.py:299` `_auto_commit_done_plan_status_if_possible`. This is a **very narrow** path: it auto-commits a single `sdd/{tales,epics,legends,myths}/*.md` file whose *only* change is a frontmatter `status: wip` → `status: done` flip (`:157-196`), committed with `git commit --no-verify` (`:250`), message `chore: Mark SDD plan done`. It does **not** bundle general SDD content into code commits — beyond this closeout flip, the finalizer just drives the agent to commit remaining dirty state itself.

**Commit-time SDD handling in precommit hooks** (`src/sase/workflows/commit/precommit_hooks.py`): `handle_sase_plan()` (`:169`), in VC mode, copies the approved plan from `~/.sase/plans/` into `cwd/sdd/tales/YYYYMM/` (`:199`), adds frontmatter/prompt links, and appends a `PLAN=<repo-relative>` tag to the code commit message. So a code commit can *reference* (and, if the plan file isn't yet in-repo, *pull in*) the plan, but the plan/prompt content itself is normally landed by path #1 above.

---

## 4. Beads specifically

**No `bd`/beads binary is used.** Despite the docstring in `src/sase/sdd/beads.py:41` mentioning `bd init`, the actual implementation uses an **in-process Rust extension** via `sase.core.bead_mutation_facade` / `bead_read_facade` / `bead_conflict_facade` (e.g. `src/sase/bead/project.py:85-92,119`). `BeadProject.init()` calls `rust_beads.init_store(root, beads_dirname, ...)` and `db_mod.init_db(...)`. `grep` for a `bd` subprocess returns nothing.

**Where the beads dir is configured:** `BEADS_DIRNAME = "sdd/beads"` (`src/sase/bead/project.py:39`). Location resolution is `find_beads_location()` (`src/sase/bead/cli_common.py:15`):
- VC mode → nearest ancestor of cwd containing `sdd/beads/`, else primary workspace (`:37-40`) — i.e. **inside the main repo working tree**.
- non-VC mode → `primary/.sase/sdd/beads/` (`:43`) — inside the standalone `.sase/sdd` git repo.

**What gets written:** `BeadProject` writes into `beads_dir`: `beads.db` (SQLite, `project.py:68,93`), `issues.jsonl`, `config.json`, `metadata.json`, and `events/` (streams + manifest, written by the Rust facade). The SQLite `beads.db` is a **compatibility mirror rebuilt from JSONL** (`rebuild_from_jsonl`, `src/sase/bead/sync.py:122`) and is **gitignored** — `.gitignore:62` `sdd/beads/beads.db*`. Tracked/committed bead files are `config.json`, `issues.jsonl`, `metadata.json`, and `events/**` (confirmed via `git ls-files sdd/beads/`).

**How beads get committed (into whichever repo owns `sdd/beads`):** all bead git ops resolve the repo via `_find_git_root(beads_dir)` (`src/sase/bead/sync.py:151`) — in VC mode that's the **main repo**; in non-VC mode it's the `.sase/sdd` repo.
- `git_sync()` (`sync.py:31`) only **stages** (`git add`) the bead-state files (excludes `beads.db*`, `:200-211`) — no commit. Called by `BeadProject.sync()` (`project.py:340-343`), which is invoked from `sase bead sync` (`cli_admin.py:31`) and from the commit precommit hook `handle_beads()` (`precommit_hooks.py:106-121`, which shells `sase bead close` + `sase bead sync`).
- `commit_bead_work_launch()` (`sync.py:49`) **commits** bead state for `sase bead work` launches (message `chore: mark bead/legend work launched for <id>`), with optional `git push` (`push_bead_work_launch*`, `:248,292`). Driven by `src/sase/bead/cli_work_commit.py:38-88`.
- Beads init commit: `init_beads()` (`sdd/beads.py:36`, non-VC) does `git init` in `.sase/sdd`, writes `.gitignore` with `beads/beads.db`, then `commit_sdd_files(..., auto_commit_type="beads")`; the VC init path is `ensure_beads_initialized` (`sdd/beads.py:85-102`) → `ensure_bare_git_sdd_initialized` + `BeadProject.init(primary)`. Same logic in `cli_common.py:56-85`.
- Plain `sase bead create/update/close` do **not** commit or even sync on their own (no `.sync()`/commit calls in `cli_crud.py`/`cli_basic.py`); their JSONL/event changes are staged/committed later by `sase bead sync`, the precommit hook, `sase bead work`, or a subsequent code commit.
- Merge-conflict resolution for the tracked bead store is `src/sase/bead/conflict_resolver.py` (`resolve_bead_conflicts`, `:28`), operating on `repo_root / BEADS_DIRNAME` (`:51`).

---

## Concrete inventory: every place that assumes `sdd/` lives in the main repo working tree

VC mode is what puts `sdd/` in the main tree. The assumptions are:

| Concern | Location | Assumption |
|---|---|---|
| Base path resolver | `src/sase/sdd/_paths.py:116-117`, `src/sase/sdd/files.py:80-81` | VC → `Path(workspace_dir)/"sdd"` |
| Beads dir constant | `src/sase/bead/project.py:39`; dup `src/sase/main/bead_fast_path.py:12` | `sdd/beads` relative to repo root |
| Beads location (VC) | `src/sase/bead/cli_common.py:37-40`; `src/sase/bead/workspace.py:187,197` | walk up from cwd to find `sdd/beads` in the tree |
| Plan/prompt VC commit | `src/sase/axe/run_agent_exec_plan_sdd.py:31-62`; `run_agent_exec_plan_accept.py:343-349` | `find_sdd_file(workspace_dir,...)` + `sase commit` in the main repo |
| Precommit plan copy | `src/sase/workflows/commit/precommit_hooks.py:199` | writes to `cwd/sdd/tales/...` in the main tree |
| Finalizer done-flip | `src/sase/llm_provider/commit_finalizer_git.py:14-19,153-154` | `sdd/{tales,epics,legends,myths}/` paths committed to main repo |
| Bead git ops | `src/sase/bead/sync.py:151` (`_find_git_root(beads_dir)`); `src/sase/bead/conflict_resolver.py:51` | `sdd/beads` shares the main repo's `.git` |
| TUI watchers | `src/sase/ace/tui/actions/_startup_watchers.py:53`; `event_refresh/_artifact_delta.py:38`; `event_refresh/_watcher.py:86` | `Path.cwd()/"sdd"/"beads"` |
| Diff/revert badges | `src/sase/ace/tui/models/_diff_badge.py:16,26`; `src/sase/ace/revert_agent_models.py:7` | `sdd/` path prefix within main-repo diffs |
| Doctor / mobile / display path-tail checks | `src/sase/doctor/checks_beads.py:105,116`; `src/sase/integrations/_mobile_helper_beads.py:251,253,414,416`; `src/sase/agent/bead_display.py:163,192,195` | `sdd/beads` or `.sase/sdd/beads` tails |
| gitignore | `.gitignore:62` (`sdd/beads/beads.db*`) + perf-artifact ignores `:68-82` | `sdd/` tracked by the main repo's gitignore |
| Config switch | `sase.yml:5` (`version_controlled: true`); default `src/sase/default_config.yml:373` (`false`) | the flag that selects in-tree vs `.sase/sdd` |

Note the important asymmetry for your migration goal: in **non-VC mode the SDD tree is already a standalone git repo** at `.sase/sdd/.git` (created by `init_beads`, `src/sase/sdd/beads.py:51-61`, and `cli_common.py:69-76`), with its own `.gitignore` and its own commit path (`commit_sdd_files` in `src/sase/sdd/_commit.py`). That existing standalone-repo machinery is the closest existing analogue to a fully separate SDD repository.

Let me review an existing research doc to match the house style/format while the remaining agents finish.

Two comprehensive reports in. Waiting on the final agent (VCS plugin architecture), which maps the opt-in extension points. Let me hold for it.

Strong evidence for the motivation: **76 of the last 200 commits (38%) are SDD/bead-related clutter.** Now waiting on the final agent (VCS plugin architecture / opt-in extension points).

`detect_vcs` classifies via entry-point plugins; crucially `get_effective_sdd_config` **already forces `bare_git` → version-controlled (in-tree)** regardless of config — that's the "old behavior" to preserve. This makes `get_effective_sdd_config` the natural per-VCS chokepoint. Let me read the bare_git plugin's SDD-relevant behavior while the last agent finishes.

The opt-in seam is confirmed: `get_effective_sdd_config` already branches per-VCS (`bare_git` forced to VC). Let me read the exact VC-path SDD commit that generates the "chore: Add SDD prompt and plan" clutter commits, then I'll write the research.

Let me check the sase-github location and examine the commit workflow dispatch and precommit hooks.

I now have an exhaustive, first-hand picture across all subsystems (the two remaining agents' scope — VCS plugin architecture — I've already covered directly via the hookspecs, GitHub plugin, registry, and `detect_vcs`). One more critical finding: `build_sdd_plan_ref` (`run_agent_exec_plan_sdd.py:73`) embeds mode-dependent plan-path references (`sdd/...` vs `.sase/sdd/...`) passed to downstream agents — a real design consideration for a third mode. Let me write the research doc.

Let me check the background search results and look at the dist-info entry points directly.

sase-github is not installed here (only `bare_git` and `cd` plugins registered), confirming it's a separate external plugin repo. Let me do final checks on the SDD config default and stop the lingering background searches.

I've completed the research and written it to the target directory. The third background exploration (VCS plugin internals) was still finishing, but its scope was fully covered first-hand, so the document is complete and grounded.

**Written to:** `sdd/research/202607/separate_sdd_repository_per_project.md`

(No `just check` needed — the only change is a new markdown file under `sdd/research/`, which CLAUDE.md explicitly exempts.)

## What I found

**The motivation is real and measurable:** 76 of the last 200 commits on `master` (38%) are SDD/bead housekeeping (`chore: Add SDD prompt and plan…`, `chore(beads): close…`, `chore: Mark SDD plan done`), interleaved with real feature/fix commits.

**The key discovery that shapes everything:** a "separate SDD repo" is **~80% already built**. SASE has two SDD storage modes switched by `sdd.version_controlled`:
- `true` (this repo) → `sdd/` **in the main repo tree**, committed to main history (the pain).
- `false` (default) → `.sase/sdd/` as a **standalone `git init` repo** with its own `.gitignore` and its own auto-commit path (`commit_sdd_files`). It's just **local-only — no remote, never pushed**.

So the feature is essentially: give that standalone repo a **remote** (`<org>/<project>-sdd` or `<org>/sdd`), discovered + cloned + pushed.

**The opt-in seam already exists per-VCS.** `get_effective_sdd_config()` (`src/sase/sdd/beads.py:18`) already special-cases `bare_git → always in-tree`. Extending that from a bool into a three-way policy (`in_tree` / `local` / `separate_repo`) is the natural home for "BareGit keeps old behavior; GitHub opts in."

**GitHub already has the discovery/clone primitives:** `gh repo list <org>` (`sase_github/workspace_plugin.py:480`), `_clone_gh_repo` (`:392`), and `github_orgs` config — so "search the org for `sdd`/`<project>-sdd`" is a small composition of existing code. (One gap: no `gh repo create`, so "repo missing" needs a decision.)

## Recommended approach

A **third SDD storage mode** (`separate_repo`) layered on the existing `.sase/sdd` standalone-repo machinery — **not** a new subsystem:
1. `get_effective_sdd_config` → a per-VCS **policy enum**; BareGit branch unchanged.
2. A new **VCS-provider hook** (`vcs_resolve_sdd_repo`) — GitHub discovers/clones `<org>/<project>-sdd`/`sdd` into `.sase/sdd`; BareGit returns `None` → falls back to old behavior.
3. Reuse `commit_sdd_files` + the existing bead **push** machinery (which already no-ops gracefully when no remote is configured).

I also evaluated modeling it as a `role: sdd` **linked repo** (Option B) and rejected it: linked repos are path-based with no remote/auto-discovery and use agent-driven commits, which fights SDD's automatic, centralized flow.

The doc ends with concrete edit sites (§5), open decisions (§6 — repo-name precedence, shared-vs-dedicated repo, create-if-missing, plan-reference scheme, offline behavior, the Rust-core boundary), and a code-reference appendix.

One decision worth flagging early: a **shared** `sdd` repo for the whole org would require namespacing content per-project (`sdd/<project>/tales/…`), whereas a **dedicated** `<project>-sdd` repo can use the existing layout as-is — that choice drives a fair amount of the design.

I now have a comprehensive picture. Here are my findings.

---

# VCS / Workspace-Provider Plugin Architecture

There are **two separate pluggy plugin systems**, which is the key structural fact:

- `sase_workspace` — high-level workflow/ref/workspace orchestration (`src/sase/workspace_provider/`)
- `sase_vcs` — low-level VCS operations + repo classification (`src/sase/vcs_provider/`)

`sase-github` is **not installed** in this workspace. The only registered plugins are `bare_git` + `cd` (workspace) and `bare_git` (vcs), confirmed in `.venv/.../sase-0.10.2.dist-info/entry_points.txt`. sase-github is an external package that ships its own entry points into these two groups.

---

## 1. Plugin registration & discovery

**Two hookspec markers / project names:**
- `src/sase/workspace_provider/_hookspec.py:8-9` — `HookspecMarker("sase_workspace")`, class `WorkspaceHookSpec` (lines 114-241).
- `src/sase/vcs_provider/_hookspec.py:5-6` — `HookspecMarker("sase_vcs")`, class `VCSHookSpec` (lines 9-267).

**Workspace discovery** — `src/sase/workspace_provider/_registry.py:27-41` (`_get_manager`): builds a singleton `pluggy.PluginManager("sase_workspace")`, calls `add_hookspecs(WorkspaceHookSpec)`, then iterates `importlib.metadata.entry_points(group="sase_workspace")`, loading and registering every plugin class. Wrapped by `WorkspacePluginManager` (`_plugin_manager.py:13-23`), which holds **all** plugins and relies on pluggy `firstresult=True` (first non-`None` wins), except `ws_get_workflow_metadata` which aggregates across all plugins (`_plugin_manager.py:25-29`).

**VCS discovery** — `src/sase/vcs_provider/_registry.py:16-26` (`_build_classification_pm`): builds `pluggy.PluginManager("sase_vcs")` and iterates `entry_points(group="sase_vcs")`. Two lookup styles: a full classification PM for detection, and a *single-plugin* PM for actually operating on a repo (`_find_plugin_class` + `_create_provider_for`, lines 204-242, matches by `ep.name`).

**Entry-point group names: `sase_workspace` and `sase_vcs`.** Registered in `pyproject.toml:125-130`:
```
[project.entry-points."sase_vcs"]
bare_git = "sase.vcs_provider.plugins.bare_git:BareGitPlugin"
[project.entry-points."sase_workspace"]
bare_git = "sase.workspace_provider.plugins.bare_git_workspace:BareGitWorkspacePlugin"
cd = "sase.workspace_provider.plugins.cd_workspace:CdWorkspacePlugin"
```
An external plugin (sase-github) hooks in by declaring the same two entry-point groups in its own `pyproject.toml` (e.g. `github = ...:GitHubWorkspacePlugin` under `sase_workspace`, `github = ...:GitHubPlugin` under `sase_vcs`).

**Note on the two "registry" files (they are unrelated despite the names):**
- `src/sase/workspace_provider/_registry.py` — plugin discovery + dispatch facade (public functions re-exported by `__init__.py:38-63`).
- `src/sase/workspace_provider/registry.py` — a completely different thing: the **materialized-workspaces registry** persisted to `<root>/registry.json` (`WorkspaceRegistry`/`WorkspaceEntry`, lines 35-93). Not part of plugin discovery.

---

## 2. VCS detection (`detect_vcs`)

`src/sase/vcs_provider/_registry.py`:

- `detect_vcs(cwd)` lines **112-139**: walks up from `cwd`; at each dir asks plugins `vcs_detect_repo_type` (non-git markers like `.hg/`, hookspec lines 238-251); if a `.git` exists (checked with `os.path.exists`, not `isdir`, to support gitdir-pointer files), calls `_classify_git_repo`.
- `_classify_git_repo(git_dir, pm)` lines **29-54**: (1) ask plugins `vcs_classify_repo` (first non-`None` wins), else (2) `_classify_by_url` fallback.
- `_classify_by_url` lines **71-109**: reads `remote.origin.url`; **any** resolvable URL (local path or hosted) → `"bare_git"`. Only raises `VCSProviderNotFoundError` when origin is unreadable/absent.

**What distinguishes "github" from "bare_git" at runtime:** solely the `vcs_classify_repo` hook (`VCSHookSpec` lines 253-267). The sase-github plugin claims repos whose origin URL is github.com and returns `"github"`. With no plugin claiming the repo, everything with a remote falls through to the `"bare_git"` default. So `github` requires the installed plugin; `bare_git` is the built-in fallback.

- `detect_vcs_family(cwd)` lines **142-150**: collapses `github`/`bare_git` → `"git"`.
- `_resolve_vcs_name(cwd)` lines **153-181**: precedence = env `SASE_VCS_PROVIDER` → config `vcs_provider.provider` (sase.yml) → `detect_vcs`. Legacy `"git"` re-classified via `_classify_git_repo`.

---

## 3. bare_git plugin behavior

**Ref resolution** — `plugins/bare_git_ref.py`:
- `resolve_git_ref(git_ref)` lines **129-241**: four dispatch modes — (1) project shorthand → read `BARE_REPO_DIR`/`WORKSPACE_DIR` from `~/.sase/projects/<name>/<name>.sase`; (2) ChangeSpec name match via `find_all_changespecs()`; (3) missing project → `_init_missing_project_ref` (auto-init); (4) bare-repo path (contains `/`) → derive name, auto-create project + clone. **The plugin knows the repo location via the `BARE_REPO_DIR` and `WORKSPACE_DIR` fields in the `.sase` project file** (`parse_bare_repo_dir`/`parse_workspace_dir`, `set_bare_repo_dir` at lines 29-80).

**Workspace plugin** — `plugins/bare_git_workspace.py` (`BareGitWorkspacePlugin`):
- `ws_get_workflow_metadata` lines **78-87**: `workflow_type="git"`, `display_name="Git (bare)"`, `pre_allocated_env_prefix="SASE_GIT"`, `vcs_family="git"`, `vcs_provider_name="bare_git"`.
- `_is_bare_git_project` lines **49-76**: requires `.git` dir + either a `BARE_REPO_DIR` field or a local (non http/git@/ssh) origin URL.
- `ws_get_workspace_directory` lines **142-162**: **calls `ensure_bare_git_sdd_initialized(...)` then `ensure_workspace_checkout(...)`** — this is where SDD docs get materialized in-repo on checkout. Highly relevant to your feature.

**Init** — `plugins/bare_git_init.py`:
- `init_bare_git_project` lines **46-113**: bare repo defaults to `~/.sase/repos/<name>.git`, clone to `~/projects/git/<name>/`; assesses bare/clone state (enums lines 21-44); `_fresh_init_empty_bare_project` (263-281) inits+clones, calls `ensure_sdd_initialized`, stages SDD paths, initial commit+push; `_clone_existing_bare_and_init_sdd` (284-295) clones then `ensure_bare_git_sdd_initialized`. Writes `BARE_REPO_DIR` + `WORKSPACE_DIR` back to the project file (lines 110-111).

**Submit** — `plugins/bare_git_submit.py`:
- `submit_bare_git` lines **75-221**: kills running processes, checks no active children, claims a pool workspace, fetches+checks out branch.
- `_submit_via_local_merge` lines **224-318**: checkout default branch → `git merge` (abort on conflict) → `git push` → delete local+remote branch → `finalize_submission`.
- `prepare_mail_git` lines **16-72**: shows branch/description, prompts before push.

**cd** — `plugins/cd_workspace.py`: trivial no-VCS `#cd:<dir>` workflow; `ws_get_workspace_directory` just returns the primary dir (lines 61-71).

---

## 4. WorkflowMetadata & the per-VCS capability question — THIS IS THE KEY SECTION

`WorkflowMetadata` is defined in `src/sase/workspace_provider/_hookspec.py:88-111`:
```python
workflow_type, ref_pattern, display_name, pre_allocated_env_prefix,
vcs_family = "", vcs_provider_name = ""
```
It is the per-workflow/per-VCS-type metadata record, aggregated across plugins via `get_all_workflow_metadata()` (`_registry.py:44-47`, `@functools.cache`).

**How `vcs_provider_name` is used today:** it is the join key from a runtime `detect_vcs()` result back to plugin metadata:
- `get_display_name_by_vcs(vcs_name)` — `_registry.py:82-95` — iterates metadata, matches `m.vcs_provider_name == vcs_name`, falls back to family. **This is the existing template for "look up a per-VCS-type attribute keyed on the detect_vcs result."**
- `project_aliases.py:40-51` uses `vcs_family`/`vcs_provider_name` to decide which workflows are VCS-like.

**The existing per-VCS-type capability flag (and it is almost exactly your feature):** SDD storage location is *already* a per-VCS capability, but it is **hard-coded to `detect_vcs(...) == "bare_git"`** rather than declared in metadata. The distinction:
- **bare_git** → SDD docs are **version-controlled in the main repo** (an `sdd/` tree committed alongside code).
- **github / everything else** → SDD docs live in a **separate standalone git repo** at `.sase/sdd/` (`sdd/beads.py:init_beads`, lines 36-82 — `git init` inside `.sase/sdd/`).

So your proposed "this VCS type stores SDD docs in a separate repo" opt-in is the inverse of the current `version_controlled` boolean.

The capability is computed by `get_effective_sdd_config()` — **`src/sase/sdd/beads.py:18-33`**:
```python
configured = get_sdd_config()            # sdd.version_controlled from config
if configured: return True
...
return detect_vcs(str(cwd)) == "bare_git"   # <-- HARD-CODED per-VCS capability
```
The base config default is `sdd.version_controlled: false` (`src/sase/default_config.yml:372-373`).

This hard-coded `== "bare_git"` capability check is duplicated across the codebase:
- `src/sase/sdd/_commit.py:269-295` (`is_local_bare_git_workspace`, `detect_vcs(...) != "bare_git"`).
- `src/sase/sdd/beads.py:31`.
- `src/sase/commit_instructions.py:162` (`_resolve_commit_skill_name`, picks `/sase_<provider>_commit` skill).
- `src/sase/axe/run_agent_directives.py:53,175`.

And `get_effective_sdd_config()` (the derived capability) is consumed in at least: `plan_approval_actions.py:316-330`, `workflows/commit/precommit_hooks.py:175-255`, `bead/workspace.py:195-198`, `ace/tui/actions/agents/_notification_modals.py:298-309`, `main/bead_fast_path.py:99-101`, `axe/run_agent_exec_plan_accept.py:277-294`, `sdd/files.py:76-84` (`get_sdd_dir` branches on `version_controlled`).

**Cleanest extension point (recommendation):**
Add a capability field to `WorkflowMetadata` (`_hookspec.py:88-111`) — e.g. `sdd_version_controlled: bool = True` (or a more general `capabilities: frozenset[str]`) — and have each workspace plugin declare it in `ws_get_workflow_metadata` (bare_git sets it true; a github plugin sets it false → "SDD in separate repo"). Then replace the hard-coded `detect_vcs(...) == "bare_git"` in `get_effective_sdd_config()` (`sdd/beads.py:18-33`) with a metadata lookup keyed on the `detect_vcs()` result, mirroring the existing `get_display_name_by_vcs()` pattern (`_registry.py:82-95`) — add a sibling like `get_sdd_version_controlled_by_vcs(vcs_name)`. That centralizes the per-VCS decision in plugin-declared metadata (so the external sase-github plugin can opt in/out itself) and removes the scattered string comparisons.

Why `WorkflowMetadata` and not the `sase_vcs` layer: the capability is about SDD/workspace document policy, which is conceptually a *workspace_provider* concern, and `WorkflowMetadata` already carries `vcs_provider_name` as the exact join key `detect_vcs()` returns. `get_all_workflow_metadata()` is already cached and aggregated across all plugins.

---

## 5. The commit workflow (is it VCS-type-aware?)

`src/sase/workflows/commit/workflow.py` — `CommitWorkflow` (lines 60-90+). Methods `create_commit` / `create_proposal` / `create_pull_request` (aliases `commit`/`propose`/`pr`, lines 51-57). It dispatches through the **`sase_vcs` provider hooks** rather than branching on VCS name directly: `vcs_create_commit`, `vcs_create_proposal`, `vcs_create_pull_request`, `vcs_finalize_commit` (`VCSHookSpec` lines 197-213), implemented for git in `src/sase/vcs_provider/plugins/_git_commit_dispatch.py`. So commit *operations* are VCS-type-aware **polymorphically** (the installed plugin decides), which is the clean pattern.

However, commit is **also** VCS-type-aware in two hard-coded spots you'd want to be aware of:
- `precommit_hooks.py:169-255` (`handle_sase_plan`) branches heavily on `version_controlled = get_effective_sdd_config(cwd)` — deciding whether to copy the plan into the repo `sdd/tales/...` tree, add frontmatter, and append `PLAN=` to the message. This is exactly the SDD-location capability again.
- `commit_instructions.py:155-164` picks the commit skill name from `detect_vcs`.

`sase commit --resume` messaging lives in `workflow.py:218,364,383`. The `sase_git_commit` console-script entry (`pyproject.toml:108` area; `entry_points.txt [console_scripts]`) is the git-specific commit shim.

---

### Summary of the recommended change surface
- Declare the capability: `src/sase/workspace_provider/_hookspec.py:88-111` (`WorkflowMetadata`) + each plugin's `ws_get_workflow_metadata` (bare_git at `bare_git_workspace.py:78-87`).
- Add a metadata lookup helper next to `get_display_name_by_vcs`: `src/sase/workspace_provider/_registry.py:82-95`.
- Re-point the single source of truth: `src/sase/sdd/beads.py:18-33` (`get_effective_sdd_config`) and `src/sase/sdd/_commit.py:269-295` (`is_local_bare_git_workspace`), which today hard-code `== "bare_git"`. Everything else already funnels through `get_effective_sdd_config()`.

The final agent confirmed my architecture read and added one genuinely valuable refinement: the per-VCS opt-in is cleanest as a **`WorkflowMetadata` capability field** declared by each plugin (mirroring the existing `get_display_name_by_vcs` lookup), rather than another hard-coded `== "bare_git"` check — and it found those hard-coded checks are scattered across several files. Let me fold this into the doc.

The `get_display_name_by_vcs` lookup pattern (`_registry.py:82-95`) is exactly the template. Let me refine the doc's recommendation to declare the opt-in as a plugin-owned `WorkflowMetadata` capability, and add the scattered hard-coded sites.

Now let me fix the step numbering in section 4 (my insertion created a collision) and add the scattered hard-coded sites to section 5.

Now let me add the scattered hard-coded `== "bare_git"` sites to section 5, since the recommendation now says to centralize them.

Let me add the `WorkflowMetadata`/lookup references to the appendix table so the key extension point is discoverable, and lightly refine the TL;DR to name the plugin-declared mechanism.

The research document is complete. I folded in one refinement from the final architecture pass that improves the recommendation:

**The opt-in is cleanest as a plugin-declared `WorkflowMetadata` capability, not another hard-coded check.** Each workspace plugin already publishes a `WorkflowMetadata` record carrying `vcs_provider_name` — the exact key `detect_vcs()` returns — and the repo already has the lookup template `get_display_name_by_vcs()` (`_registry.py:82-95`). So "each VCS type opts in" becomes: BareGit declares `in_tree`, the external `sase-github` plugin declares `separate_repo`, read via a sibling `get_sdd_storage_by_vcs()` helper. That lets the GitHub plugin opt *itself* in without core code special-casing provider names — and it centralizes the `detect_vcs(...) == "bare_git"` checks that are currently **scattered across four files** (`sdd/beads.py:31`, `sdd/_commit.py:269-295`, `commit_instructions.py:162`, `run_agent_directives.py:53,175`).

The final recommendation therefore splits into two complementary pieces:
- **Declaration** (cheap, cached, side-effect-free): a `WorkflowMetadata` capability field per plugin.
- **Materialization** (network work): a separate `ws_resolve_sdd_repo` hook where GitHub discovers/clones `<org>/<project>-sdd` or `<org>/sdd` into `.sase/sdd`, reusing `gh repo list` + `_clone_gh_repo` + the existing bead push machinery.

The doc at `sdd/research/202607/separate_sdd_repository_per_project.md` now covers: the motivation with hard numbers, the two current storage modes and why the "separate repo" is ~80% already built (the standalone `.sase/sdd/.git`), both plugin systems, three design options with an A-vs-B verdict, the detailed 8-step recommended approach, the ~20 edit sites that assume in-tree `sdd/`, eight open design decisions, and a code-reference appendix.

I made this change in this session — it's the research document I was asked to write. I'll commit it using the git commit skill.

I'll record the skill usage, then examine and commit the change.

The change is my untracked research doc. Let me write the commit message and commit.

The commit succeeded and the working tree is clean, with `master` in sync with `origin/master` (not ahead) — so it was pushed as part of the workflow.

## Summary

The finalizer flagged my one uncommitted change — the research document I created this session at `sdd/research/202607/separate_sdd_repository_per_project.md`. I committed it via the `sase_git_commit` skill using `create_commit`:

- **Commit:** `docs: add research on separate SDD repository per project`
- **File:** the single new research markdown doc (staged explicitly with `-f`)
- **Result:** commit succeeded, pushed, working tree clean, `master` in sync with `origin/master`

The research doc itself (delivered earlier) analyzes how to store SDD artifacts in a separate per-project GitHub repo (`<project>-sdd` or `sdd` in the same org), with the key finding that the "separate repo" is ~80% already built via the existing standalone `.sase/sdd/.git` mode — the recommended approach adds remote discovery/clone/push and a plugin-declared per-VCS opt-in so BareGit keeps in-tree behavior while GitHub opts in.
