# Chat History - ace-run

- **TIMESTAMP:** 2026-07-12 15:17:29 EDT
- **MODEL:** claude/opus
- **AGENT:** research.a.cld
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260712_150419.md`

## Prompt

%name:research.@.cld %m:@research_b %g:research #gh:gh_sase-org__sase Can you help me audit this codebase and my chezmoi repo and produce some research with the goal of improving lumberjacks? Namely, what does lumberjack/chop configuration allow for now and should it have better built-in support for certain capabilities (make sure to review the lumberjack chops defined in my chezmoi repo; don't just review the builtin lumberjacks/chops)? Write this research to a new markdown file under the $(sase sdd path research --ensure)/$(date +%Y%m)/ directory.


## Response

I'll help you research improving lumberjacks. Let me start by orienting myself — understanding what lumberjacks/chops are in this codebase, finding the `/202607/` directory, and accessing your chezmoi repo.

Let me kick off several investigations in parallel.

Now let me understand where research reports live and read the core lumberjack/chop implementation. Let me investigate the research directory structure and the chezmoi chops in parallel.

The `/202607/` directories are month-bucketed folders. Let me pin down exactly where research reports belong. Let me look at the research repo content and confirm the convention.

The research repo (`sase--research`, currently empty) is where `/202607/` reports belong. Let me set up task tracking and then read the key config while dispatching parallel deep-dives.

The bulk of the real lumberjack config is in `sase_athena.yml`. Let me read both configs' lumberjack sections in full.

I now have a clear picture of the config surface. Let me dispatch parallel deep-dives across the three areas while I read the core config schema myself.

I'll investigate the lumberjack and chop subsystem. Let me start by exploring the directory structure and reading the key files.

Let me read the core config and model files first.

Now let me read the chop runner files and state files.

I'll start by locating all the relevant files, then read them systematically.

Now the agent chop runner and script runner files.

Let me read all the chop scripts and the key axe files in parallel.

Now the chop_agents, chop_script_runner, and chop_script_context.

Now the state files, orchestrator, maintenance, lock, and the inventory/doctor/render files.

Now the orchestrator, maintenance, and lock files.

While the agents work, let me read the core config schema and default config myself for first-hand grounding.

Now let me read the core axe files: chop_agents.py, chop_script_context.py, and the runner scripts.

I'll start by reading all the specified files in parallel.

Now let me read the inventory, doctor, and render files, plus the default_config.yml axe section.

Confirmed the config schema is quite minimal (name/description/agent/run_every/timeout/env for chops; interval/chop_timeout/chops for lumberjacks). Let me read the default config wiring and the chop runner to see how chops resolve.

Now let me read the config files and search for the xprompt definitions.

Now let me look at the default_config.yml axe section and search for the agent launch path and xprompt directives.

Now let me read the config, the default_config.yml lumberjacks section, and the underlying runners (hook_jobs, check_cycles).

Now let me find the xprompt definitions for the agent chops. Let me search the chezmoi repo for xprompts directories and these specific names.

Now let me read the full lumberjacks section of default_config.yml and the underlying runners.

Now let me investigate the agent launch path and what xprompt directives the `agent:` field supports.

Let me read the chop runner dispatch and inventory to understand chop resolution first-hand.

The xprompt definitions aren't in the chezmoi config. The `#!sase/...` xprompts are likely defined in the primary sase repo's xprompts source directory. Let me search there.

I notice a naming detail: config uses `cl_submitted_checks` but the script is `sase_chop_pr_submitted_checks.py`. Let me check the entry-point mapping in pyproject.toml and read hook_jobs.py.

The `agent:` field is passed as the `query` to `launch_agent_from_cwd`. Let me read the axe docs and the launch implementation to understand directive support.

The resolution model is now clear: `agent is None` → script chop resolved by locating a `sase_chop_<name>` executable on configured dirs/PATH; otherwise agent chop. Let me read the agent-chop launcher and context builder to round out my first-hand understanding.

The xprompts live in the primary repo's `xprompts/` directory (the `sase/` namespace = the sase project). Let me read all five.

Let me examine the runner pool for concurrency and confirm how the agent prompt/query is processed for directives.

Let me read the scripts/__init__.py entry-point wrappers and the hook_jobs.py runner.

Let me confirm the absence of gating/retry/dependency/enabled fields and check the error_digest chop for failure notification handling.

I have all the chop definitions. Let me verify the existing chop-config capabilities and the `%g:chop`/`chop_prompt` directive semantics in the primary repo, to ground the capability-gap analysis.

Let me read the lumberjack scheduler, context builder, and telemetry to complete the invocation picture.

Let me find the Chop config model to enumerate the exact fields already supported by config.

I have strong first-hand grounding now. Let me confirm exactly where the research file should live while the audit agents run.

Let me verify a few remaining details: the telemetry cleanup function, error-digest state, and confirm whether pushgateway_cleanup is wired anywhere.

Found it — the user's `research` snippet writes to `$(sase sdd path research --ensure)/$(date +%Y%m)/`. Let me resolve that path and check for README conventions.

Let me confirm how script-chop names resolve to the executables and how the chop context (`state_dir`, `all_changespecs_file`) is provided.

Let me confirm the meaning of a few directives (`-@` name template, `%auto`, `%g`/`%group`, `#!`) to be precise in the report.

Let me confirm the CLI one-shot path and the telemetry cleanup for a complete invocation picture.

The research repo is empty (unborn branch) — I'll create `202607/` there. Let me independently read two representative custom chops to ground the strongest findings while the audit agents finish.

This `gh_actions_fix` script is a perfect specimen — a ~550-line program that hand-rolls per-repo fan-out, poll+predicate triggering, fire-once dedup state, and an in-flight ChangeSpec guard, all things absent from chop config. Let me verify the refresh_docs fan-out and locate the xprompt definitions to confirm the duplication story.

The referenced `#!sase/refresh_docs` etc. are builtin xprompt skills in the main repo. Let me confirm their location, then wait for the audit agents.

The fan-out story is confirmed: `refresh_docs` takes `project`/`gh_ref`/`threshold` inputs and the user hand-copies 5 chops differing only in those values (plus an internal threshold gate inside the xprompt). I have strong first-hand grounding across all areas. Let me check on the audit agents' progress.

I've mapped the core mechanics first-hand and confirmed the key evidence. Three parallel audit agents are still running (core engine/config schema, builtin chop scripts, and your chezmoi custom chops). Here's where things stand:

**Confirmed so far:**
- **Config surface is deliberately thin** — a chop supports only `name`, `description`, `agent`, `run_every`, `timeout`, `env`; a lumberjack supports only `interval`, `chop_timeout`, `chops` (`src/sase/axe/config.py`). No `enabled`, no conditional/gate, no dependencies, no fan-out, no jitter/backoff, no dynamic env.
- **Two chop kinds**: `agent is None` → script chop (resolved by locating a `sase_chop_<name>` executable on `chop_script_dirs`/PATH); otherwise agent chop (the `agent:` string is launched through the full xprompt directive pipeline: `%n`, `#gh`, `%g:chop`, `#!`, `%auto`).
- **Your chezmoi `gh_actions_fix` chop is the smoking gun** — a ~550-line program hand-rolling per-repo fan-out (`SASE_GHA_FIX_REPOS`), poll+predicate triggering, fire-once dedup state (`gh_actions_fix_seen.json`), and an in-flight ChangeSpec guard — none of which chop config can express.
- **`refresh_docs` fan-out** — 5 near-identical chops differing only by `(project, gh_ref, threshold)`, plus a threshold gate that had to live inside the xprompt.

I'll write the research report to `sase/repos/research/202607/` (resolved via `sase sdd path research`) once the agents return their detailed inventories. Waiting on them now.

I now have a complete picture of the subsystem. Let me compile the comprehensive report.

---

# CORE ENGINE & CONFIG SCHEMA — Lumberjack/Chop Subsystem Audit

All paths are under `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/`. Line references are to the files as read.

## 1. Full Config Schema (exhaustive)

The config models are **plain `@dataclass`es, not pydantic**, defined in `src/sase/axe/config.py`. Parsing is hand-rolled in `_parse_lumberjacks` / `load_axe_config`. There is **no separate config schema module** — this is the whole schema.

### 1a. `AxeConfig` — top-level (`config.py:59-70`)

```python
@dataclass
class AxeConfig:
    max_hook_runners: int = 3
    max_agent_runners: int = 3
    zombie_timeout_seconds: int = 7200
    lumberjack_log_max_bytes: int = DEFAULT_LUMBERJACK_LOG_MAX_BYTES  # 50*1024*1024
    verbose_lumberjack_diagnostics: bool = False
    query: str = ""
    chop_script_dirs: list[str] = field(default_factory=list)
    lumberjacks: dict[str, LumberjackConfig] = field(default_factory=dict)
```

| Field | Type | Default | Meaning |
|---|---|---|---|
| `max_hook_runners` | int | 3 | Global concurrent hook-runner slots. Enforced by chop *scripts* via `SharedRunnerPool`, not the framework. Passed into `ChopScriptContext`. |
| `max_agent_runners` | int | 3 | Global concurrent agent-runner slots (same enforcement model). |
| `zombie_timeout_seconds` | int | 7200 | Age after which jobs are marked zombie; passed to script context. |
| `lumberjack_log_max_bytes` | int | 52428800 | Byte cap on each bounded lumberjack log. Sanitized by `_positive_int` (`config.py:73-82`). |
| `verbose_lumberjack_diagnostics` | bool | False | Adds verbose diagnostics into `context.json`. |
| `query` | str | `""` | ACE ChangeSpec query filter; parsed once at Lumberjack construction (`lumberjack.py:105-106`); filters changespecs passed to chops, **not** whether a chop runs. |
| `chop_script_dirs` | list[str] | `[]` | Extra directories searched for chop scripts. |
| `lumberjacks` | dict[name→LumberjackConfig] | `{}` | The lumberjack definitions. |

Loaded via `load_axe_config()` (`config.py:132-176`) from the merged config `axe:` section. Defaults live in `src/sase/default_config.yml:248-298`.

### 1b. `LumberjackConfig` (`config.py:44-56`)

```python
@dataclass
class LumberjackConfig:
    name: str
    interval: int
    chop_timeout: int | None = None   # seconds, default timeout for all chops
    chops: list[ChopConfig] = field(default_factory=list)
```

| Field | Type | Default | Meaning / parsing |
|---|---|---|---|
| `name` | str | — | Map key from YAML. |
| `interval` | int | `cfg.get("interval", 1)` → **1 second** if omitted (`config.py:125`) | Seconds between scheduler ticks. Raw int seconds (no duration-string parsing — unlike chop fields). |
| `chop_timeout` | int\|None | None | Default per-chop **script** timeout. Parsed from a duration string (`"90s"`) via `_parse_duration` (`config.py:122`). |
| `chops` | list[ChopConfig] | `[]` | Chops this lumberjack runs each tick. |
| `chop_names` (property) | list[str] | — | Names only. |

Note: `interval` is **not** run through `_parse_duration` — it must be a bare integer of seconds. `chop_timeout` **is** a duration string.

### 1c. `ChopConfig` (`config.py:32-41`)

```python
@dataclass
class ChopConfig:
    name: str
    description: str
    agent: str | None = None
    run_every: int | None = None   # seconds, parsed from duration string (e.g. "60m")
    timeout: int | None = None     # seconds, parsed from duration string (e.g. "30s")
    env: dict[str, str] = field(default_factory=dict)
```

| Field | Type | Default | Meaning / parsing (`config.py:100-121`) |
|---|---|---|---|
| `name` | str | — (required, `entry["name"]`) | Chop identifier. A bare string YAML entry becomes `ChopConfig(name=entry, description="")` (`config.py:120-121`). |
| `description` | str | `""` | Human-readable; `entry.get("description", "")`. |
| `agent` | str\|None | None | `entry.get("agent") or entry.get("xprompt")` — **`xprompt` is an accepted alias key** (`config.py:114`). Presence of this field is the sole switch between agent-chop and script-chop. |
| `run_every` | int\|None | None | Time-based throttle, seconds. Parsed from duration string via `_parse_duration` (`"60m"`, `"30s"`, `"2h"`). Invalid/absent → None → runs every tick. |
| `timeout` | int\|None | None | Per-chop **script** timeout override; duration string. |
| `env` | dict[str,str] | `{}` | Custom env vars; coerced to `{str:str}` (`config.py:104-109`). **Applied to script chops only — silently dropped for agent chops** (see §4). |

**Duration parsing** (`config.py:14-29`): `_DURATION_RE = ^(\d+)(s|m|h)$`, multipliers `s=1, m=60, h=3600`. No support for days, compound (`1h30m`), fractional, or bare integers for chop-level fields.

### Fields the task asked about that DO NOT exist
- **No `enabled`/`disabled`** field on lumberjacks or chops. To disable, you delete the entry from config.
- **No lumberjack-level `env`** (only per-chop `env`).
- **No `gate`/`when`/`if`/`unless`/`depends_on`/`retry`/`backoff`/`jitter`/`concurrency`/`singleton`/`on_failure`/`notify`/`cron`** — confirmed absent by grep across `config.py`, `lumberjack.py`, `chop_runner*.py`.
- Any unknown YAML keys on a chop/lumberjack are **silently ignored** (the parser only reads known keys; it never rejects extras).

---

## 2. Chop Resolution Model

Dispatch is in `run_configured_chop_once` (`chop_runner.py:139-182`). The **only** discriminator is whether `chop.agent is not None`:

```python
if chop.agent is not None:
    return _run_agent_chop_once(...)   # agent chop
return _run_script_chop_once(...)      # script chop
```

### Script chop resolution (`chop_script_runner.py:18-53`, `discover_chop_script`)
Given `name`, search order:
1. `<dir>/<name>` (exact, executable) for each `chop_script_dirs` entry.
2. `<python-bin-dir>/sase_chop_<name>` (beside the running interpreter — resilient to broken PATH symlinks).
3. `shutil.which("sase_chop_<name>")` on `$PATH`.

If none found → outcome `missing_script` (`chop_runner_script.py:177-207`). Scripts are invoked as `<script> --context <context.json>` (`chop_script_runner.py:139`). Built-in scripts are packaged entry points `sase_chop_*` (e.g. `src/sase/scripts/sase_chop_hook_checks.py`, `sase_chop_error_digest.py`, etc.).

### Agent chop resolution / launch
An "agent chop" is any chop whose `agent:` (or `xprompt:`) field is set. `run_agent_chop_once` (`chop_runner_agent.py:70-178`):
1. Dedup: compute `prompt_hash(chop.agent)` (SHA-256 of whitespace-normalized prompt, `chop_agents.py:54-57`); if any **live** registry record matches `(lumberjack, chop_name, prompt_hash)` → return `already_running` (`chop_runner_agent.py:85-97`).
2. Build metadata env via `build_chop_launch_env` (`chop_agents.py:60-76`): sets `SASE_CHOP_LUMBERJACK`, `SASE_CHOP_NAME`, `SASE_CHOP_RUN_ID` (fresh uuid), `SASE_CHOP_PROMPT_HASH`.
3. **Launch:** `launch_agent_from_cwd(chop.agent, extra_env=extra_env)` (`chop_runner_agent.py:104-109`).

Crucially, **`chop.agent` is passed verbatim as the `query`/prompt string** to `launch_agent_from_cwd` (`src/sase/agent/launch_cwd.py:36-55` → `launch_cwd_agents.py:launch_agents_from_cwd_impl`). This is the *same* launcher as `sase run`. Therefore the `agent:` field is a **full SASE agent prompt** and supports the entire prompt/xprompt/directive pipeline, not a restricted "agent name":

- **xprompt expansion** `#foo` and xprompt swarms (via `expand_xprompt_swarms_with_metadata`, `launch_cwd_agents.py`).
- **Multi-prompt / swarm `---`** separators → fan-out into multiple agents (docstring `launch_cwd_agents.py:29-31`; note `launch_agent_from_cwd` returns only the *first* result — `launch_cwd.py:47-55`).
- **Project-alias canonicalization**, VCS/known-project ref resolution (`resolve_ref_from_prompt`).
- Naming/grouping/visibility directives such as `%n`, `%group:`/`%g:`, `#gh`, `%auto`, `%hide`, `%wait`, `%effort`/`%model` — these are handled downstream by the shared prompt/directive machinery, not by the chop code. The chop layer treats `agent:` as an opaque prompt string; whatever directives `sase run` supports are supported here identically. (The axe docs, `docs/axe.md:272-277`, explicitly note e.g. `%hide` applies to agent chops and that agent chops are visible-by-default.)

There is **no validation** in the chop layer of what directives the prompt contains; a bad prompt surfaces at launch time as `agent_failed`.

Resolution status is also computed statically for `sase axe chop list`/`doctor` in `chop_inventory.py:134-166`: agent chops → status `agent-backed` (`resolved_path=None`); script chops → `configured` if `discover_chop_script` finds it else `missing`.

---

## 3. Scheduling & Lifecycle

**Process model (3 tiers):**
1. **Orchestrator** (`orchestrator.py`) — one supervisor. Holds the `orchestrator.lock` flock (`lock.py:AxeLifecycleLock`), writes `orchestrator.pid`, spawns one child per lumberjack via `sase axe lumberjack run <name>` (`orchestrator.py:61-96`), monitors with `poll()` every 1s and **restarts** any child that exits unexpectedly (`orchestrator.py:203-227`). Forwards SIGTERM to children on shutdown with 10s grace then SIGKILL (`orchestrator.py:232-244`).
2. **Lumberjack** (`lumberjack.py:Lumberjack`) — one process per lumberjack. Uses the **`schedule` library** (not systemd/cron): `self.scheduler.every(self.config.interval).seconds.do(self._run_tick)` (`lumberjack.py:554`), plus status every 5s and metrics every 30s. First tick runs immediately (`lumberjack.py:570`). Main loop: `while running: scheduler.run_pending(); time.sleep(0.1)` (`lumberjack.py:572-575`).
3. **Chop** — one job per tick.

There is **no systemd timer / no cron**. Scheduling is a userspace Python loop; the daemon must stay alive. The ACE TUI auto-starts axe unless `--no-axe`.

**`interval` (lumberjack) vs `run_every` (chop):**
- `interval` = how often the lumberjack ticks (fixed, seconds).
- `run_every` = per-chop *minimum* spacing, enforced in the tick's main-thread eligibility filter (`lumberjack.py:202-214`): if `now - last_run < run_every`, the chop is skipped this tick. So effective cadence = `max(interval, run_every rounded up to interval)`. Last-run timestamps persist to `chop_timestamps.json` (`_state_lumberjack.py:180-204`) and are only updated on success (`lumberjack.py:239-241, 293`), so a chop with no `run_every` runs **every tick**.
- Manual runs (`sase axe chop run`, TUI `r`) call `run_configured_chop_once` directly, which **does not check `run_every`** — the throttle lives only in the scheduler tick filter. (`docs/axe.md:259-262`.)

**Concurrency within a tick (`lumberjack.py:216-229`):**
- Script chops: submitted to a `ThreadPoolExecutor()` **with no `max_workers`** → Python default (`min(32, cpu+4)`). So script chops in one tick run **concurrently, effectively unbounded** by the framework.
- Agent chops: run **sequentially** in configured order (`lumberjack.py:225-226`) — deliberately, to avoid same-tick workspace-allocation races (comment `lumberjack.py:216-218`; `docs/axe.md:283-285`).
- **No per-chop or per-lumberjack concurrency cap** in config. The only concurrency limiting is the global `max_hook_runners`/`max_agent_runners`, and that is enforced *by the chop scripts themselves* through `SharedRunnerPool` (`runner_pool.py:126-248`, flock on `~/.sase/axe/shared/runner_count`), not by the chop-runner framework.

**Locking (all `fcntl.flock`):**
- Orchestrator lifetime lock — single-orchestrator guarantee (`lock.py`).
- Per-lumberjack agent registry lock `agent_chops.json.lock` (`chop_agents.py:132-145`) — plus an in-process `threading.RLock` per path.
- Shared runner counter lock (`runner_pool.py`).
- No dedicated per-chop lock file; chop singleton behavior comes from dedup checks (§4), not locks.

**Cross-tick overrun:** if a tick exceeds `interval` it logs a "Tick overrun" warning (`lumberjack.py:254-258`) but does not skip/queue — `schedule` just fires the next pending run.

---

## 4. Timeouts, Env, Gating, Retries, Error Handling

**Timeouts:**
- `resolved_timeout = chop.timeout or chop_timeout_default` where default is the lumberjack's `chop_timeout` (`chop_runner_script.py:159`, passed `lumberjack.py:277`). If both None → **no timeout** (script `proc.wait(timeout=None)`).
- Applies to **script chops only.** On expiry, `stream_chop_script` kills the whole process group (`SIGKILL` via `os.killpg`, new session) to reap grandchildren (`chop_script_runner.py:192-206`), returns `timed_out=True` → outcome `timeout`.
- **Agent chops ignore timeout entirely** — launch is fire-and-forget of a background agent; `resolved_timeout` is never consulted in the agent path.

**Env injection:**
- Script chops (`chop_runner_script.py:209-216`): `env = dict(chop.env)` then `.update(build_chop_launch_env(...))`. In `stream_chop_script` (`chop_script_runner.py:129-132`) this is layered on top of a copy of `os.environ`. So subprocess sees full process env + `chop.env` + `SASE_CHOP_*` metadata.
- **Agent chops: `chop.env` is NOT applied.** `run_agent_chop_once` builds only `build_chop_launch_env(...)` metadata (`chop_runner_agent.py:99-103`) and passes that as `extra_env`. The configured `env:` dict is silently dropped for agent chops. (Notable gap — see §5.)

**Gating / conditional run — the only mechanisms:**
1. `run_every` time throttle (§3).
2. **Maintenance marker** (`maintenance.py`): each tick reads `~/.sase/axe/maintenance.json`; if present, the tick records a cycle and skips **all** chop execution (`lumberjack.py:153-164`). Stale markers (>24h, malformed, or dead owner PID) are auto-cleared (`maintenance.py:85-108`).
3. **Dedup / singleton guard** (implicit, not configurable):
   - Agent chops: live-registry prompt-hash dedup → `already_running` (`chop_runner_agent.py:85-97`; also pre-checked in tick via `_is_agent_eligible`, `lumberjack.py:409-442`).
   - Script chops: `active_script_chop_run` inspects the newest run-history entry; if still `running` with a live PID → `already_running` (`chop_runner_script.py:60-107`). Stale detection: dead-PID rows finalized; PID-less rows kept only for a grace window = `resolved_timeout` or `PIDLESS_SCRIPT_CHOP_STALE_FALLBACK_SECONDS=300` (`chop_runner_script.py:34-41`).

   There is **no `when:`/`gate:`/condition** on ChangeSpec state — the `query` filter only shapes the changespec list handed to a chop.

**Retries: none.** No retry/backoff/attempt config anywhere. Failure handling is throttle-only:
- Script/agent **failures do not update the `run_every` timestamp** (except a special case): a failing script chop is retried on the next eligible tick (`lumberjack.py:301-309`, `update_timestamp=False`). `agent_failed` **does** update the timestamp when `run_every` is set (`lumberjack.py:356-368`) — an intentional throttle so a misconfigured agent chop won't retry every tick and flood digests.

**Error handling on failure (`lumberjack.py:489-508`, `_state_scheduler.py:173-203`):**
- `_handle_error` logs red, increments `LumberjackMetrics.errors_encountered` and `AXE_ERRORS{error_type="chop"}`, and appends to `~/.sase/axe/recent_errors.json` (capped at **last 100**). Tracebacks must be captured inside the `except` block (`_ChopResult.traceback`); `_handle_error` never calls `format_exc()` itself.
- Per-run persistence: every run writes a `ChopRunEntry` (`_state_chops.py:37-61`) with `status` (`success/failure/timeout/missing_script/agent_launched/running`), `error`, `traceback`, `exit_code`, `pid`/`agent_pid`, `output_bytes`, `source`, `started_by`. Streamed stdout+stderr → `<run_id>.log`. History pruned to newest `MAX_CHOP_RUN_HISTORY=10` terminal runs per chop (`_state_chops.py:117-147`).
- **Notifications:** there is no per-chop notification hook. The built-in `error_digest` chop (`src/sase/scripts/sase_chop_error_digest.py`, housekeeping lumberjack, hourly) reads `recent_errors.json`, filters to the last hour above a high-water mark, and calls `notify_axe_error_digest(...)`. That is the entire failure-notification surface, and it is a chop like any other, not a framework feature.

`ChopRunOutcome` status enum (`chop_runner_types.py:11-19`): `success, failure, timeout, missing_script, agent_launched, agent_failed, already_running`. The Lumberjack maps each to a `_ChopResult` in `_outcome_to_result` (`lumberjack.py:282-390`); an unknown status is surfaced as a loud `RuntimeError`.

---

## 5. Capabilities: EXIST vs NOTABLY ABSENT

### Expressible in config today
- Grouping chops under named lumberjacks, each with its own tick `interval`.
- Two chop kinds via one field: script (`sase_chop_<name>`) vs agent (`agent:`/`xprompt:` = full prompt with directive support).
- Per-chop time throttle (`run_every`, `s/m/h`).
- Per-chop and per-lumberjack **script** timeout (`timeout` / `chop_timeout`).
- Per-chop custom env (**script chops only**).
- Custom script search dirs (`chop_script_dirs`).
- Global (not per-chop) runner caps `max_hook_runners`/`max_agent_runners` (self-enforced by scripts).
- Global ChangeSpec `query` filter (shapes context, not gating).
- Implicit singleton/dedup per `(lumberjack, chop, prompt_hash)` and per running script row.
- Bounded run history + streamed logs + a `source` provenance tag.

### Notably ABSENT (cannot be expressed in config)
- **`enabled`/toggle** — must delete the entry to disable; no soft-disable.
- **Conditional/gated triggers** — no `when:`/`if:` on ChangeSpec state, file changes, event, or prior-run result. Only run_every + maintenance + dedup.
- **Inter-chop dependencies / DAG ordering** — no `depends_on`, no run-after. Script chops run concurrently in arbitrary thread order; agent chops run in listed order but with no dependency semantics.
- **Retries / backoff / jitter** — none. Failures simply re-run next eligible tick (or throttle to `run_every` for `agent_failed`). No exponential backoff, no max-attempts, no jitter to de-sync ticks.
- **Per-chop / per-lumberjack concurrency limits** — the script ThreadPoolExecutor is unbounded; only global runner caps exist, and they aren't enforced by the framework.
- **`env` for agent chops** — the `env:` dict is silently ignored on the agent path (only script chops get it). This is a latent footgun.
- **Cron / absolute-time / calendar scheduling** — only fixed relative intervals; `interval` must be a bare integer of seconds (no duration string) and `run_every` maxes out at hours (no days/weeks/compound).
- **Per-repo / per-project fan-out** — no config-level fan-out. Fan-out only happens if the agent prompt itself uses `---`/xprompt swarm; script chops receive all changespecs and must loop internally.
- **Secrets/credentials handling** — none built in. Secrets come from ambient process env or per-chop `env` plaintext in `sase.yml`; only Telegram has bespoke token-source discovery in `chop_doctor.py:271-310` (env → `~/.sase/telegram_bot_token` 600 → `pass`), which is a doctor check, not a config capability.
- **Structured output capture / result passing** — chop output is just streamed text to `<run_id>.log`; there's no typed result, no output var, no way to feed one chop's output to another.
- **Per-chop notification / alerting config** — no `on_failure: notify`. The only alert path is the shared hourly `error_digest` chop.
- **Timeout for agent chops** — impossible; timeout applies to scripts only.
- **Duration-string richness** — regex is `^(\d+)(s|m|h)$`: no days, fractions, or compound (`1h30m`) durations; invalid strings silently become `None`.
- **Schema validation** — unknown keys are silently ignored; typos in field names (e.g. `run-every` vs `run_every`) fail silently rather than erroring.

### Key file map (for the design doc)
- Config models + parsing: `src/sase/axe/config.py`
- Scheduler loop + tick + eligibility/dedup: `src/sase/axe/lumberjack.py`
- Dispatch/outcome types: `src/sase/axe/chop_runner.py`, `chop_runner_types.py`
- Agent-chop launch: `src/sase/axe/chop_runner_agent.py` → `src/sase/agent/launch_cwd.py`
- Script-chop run + dedup + timeout: `src/sase/axe/chop_runner_script.py`, `chop_script_runner.py`
- Context to scripts: `src/sase/axe/chop_script_context.py`, `chop_runner_context.py`
- Run history/state: `src/sase/axe/_state_chops.py`, `_state_lumberjack.py`, `_state_scheduler.py`
- Registry/dedup + env metadata: `src/sase/axe/chop_agents.py`
- Supervisor / lock / pause: `src/sase/axe/orchestrator.py`, `lock.py`, `maintenance.py`
- Global concurrency: `src/sase/axe/runner_pool.py`
- Inventory/doctor/render (config UX): `src/sase/axe/chop_inventory.py`, `chop_doctor.py`, `chop_render.py`
- Defaults + docs: `src/sase/default_config.yml:248-298`, `docs/axe.md`

Core-engine agent is back with a thorough report — confirms and enriches my findings (process model, unbounded script concurrency vs sequential agent chops, `env` silently dropped for agent chops, no agent-chop timeout, no schema validation). Waiting on the builtin-scripts and chezmoi-chops agents.

Both remaining agents (builtin chop scripts, chezmoi custom chops) are still running. I'll continue once they return — waiting on them now.

I have a complete picture. Compiling the report now.

---

# BUILTIN CHOP SCRIPTS — Investigation Report

Scope: `src/sase/scripts/sase_chop_*.py` (13 scripts) plus their runner, registry, and default wiring, all under the primary workspace `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12`.

## Key architectural fact up front

All 13 builtin scripts are **script chops**, not `agent` chops. In `ChopConfig` (`src/sase/axe/config.py:32-41`) a chop is an "agent chop" only if it has an `agent`/`xprompt` prompt; otherwise it's a script chop dispatched to a `sase_chop_<name>` executable. None of the builtin scripts are agent chops. Several of them *internally* cause agents or background subprocesses to launch (mentors, CRS/fix-hook workflows, background `gh` checks), but that happens inside the shared Python runner libraries, not via the chop-agent registry. The chop-agent registry in `chop_agents.py` exists for the *other* kind of chop (config-defined `agent:` prompts) and is not exercised by any of these 13 scripts.

The scripts themselves are extremely thin: 9 of the 13 are byte-for-byte structural clones that construct a `HookJobRunner` and call one method on it. The real logic lives in `src/sase/ace/scheduler/*` and `src/sase/axe/{hook_jobs,check_cycles}.py`.

---

## 1. Inventory table

Cadence note: cadence = the owning lumberjack's `interval` unless the chop sets `run_every` (per-chop override, `config.py:39`, `lumberjack.py:202-214`). **No builtin chop sets `run_every` in `default_config.yml`**, so each runs every tick of its lumberjack.

| # | Script file | Chop name (entry point) | Lumberjack (interval) | One-line purpose | Category |
|---|---|---|---|---|---|
| 1 | `sase_chop_hook_checks.py` | `hook_checks` | `hooks` (5s) | Complete finished hooks, start stale ones, zombie-detect | poll/check + dispatch |
| 2 | `sase_chop_mentor_checks.py` | `mentor_checks` | `hooks` (5s) | Start mentor workflows once hook prereqs met | dispatch (launches agents) |
| 3 | `sase_chop_workflow_checks.py` | `workflow_checks` | `hooks` (5s) | Complete/start CRS & fix-hook workflows | poll/check + dispatch |
| 4 | `sase_chop_pending_checks_poll.py` | `pending_checks_poll` | `hooks` (5s) | Poll `~/.sase/checks/` for background check results; reap orphan files | poll/check |
| 5 | `sase_chop_comment_zombie_checks.py` | `comment_zombie_checks` | `hooks` (5s) | Mark comment threads older than zombie timeout as ZOMBIE | cleanup/maintenance |
| 6 | `sase_chop_suffix_transforms.py` | `suffix_transforms` | `hooks` (5s) | Strip stale suffixes/markers; update mail-readiness | cleanup/maintenance |
| 7 | `sase_chop_orphan_cleanup.py` | `orphan_cleanup` | `hooks` (5s) | Release workspace claims orphaned by reverted PRs w/ dead PIDs | cleanup/maintenance |
| 8 | `sase_chop_stale_running_cleanup.py` | `stale_running_cleanup` | `hooks` (5s) **and** `checks` (300s, backstop) | Release workspace claims held by dead processes | cleanup/maintenance |
| 9 | `sase_chop_wait_checks.py` | `wait_checks` | `waits` (10s) | Resolve agent wait deps; write `ready.json` when satisfied | poll/check + dispatch (unblocks agents) |
| 10 | `sase_chop_pr_submitted_checks.py` | `cl_submitted_checks` (alias → `pr_submitted_checks`) | `checks` (300s) | Start background `is_cl_submitted` checks for leaf PRs with submitted parent | dispatch (launches bg checks) |
| 11 | `sase_chop_comment_checks.py` | `comment_checks` | `comments` (60s) | Start background `critique_comments` checks for mailed PRs | dispatch (launches bg checks) |
| 12 | `sase_chop_error_digest.py` | `error_digest` | `housekeeping` (3600s) | Notify a digest of errors from the last hour | error digest / notification |
| 13 | `sase_chop_pushgateway_cleanup.py` | `pushgateway_cleanup` | **not wired** in `default_config.yml` | Delete stale Prometheus pushgateway groups | cleanup/maintenance + telemetry |

Default wiring source: `src/sase/default_config.yml:256-298`. Entry-point → module mapping: `pyproject.toml:102-115` and `src/sase/scripts/__init__.py:83-163`.

### Two naming/wiring gotchas worth flagging for the report

- **`cl_submitted_checks` vs `pr_submitted_checks`**: The lumberjack config uses the chop name `cl_submitted_checks` (`default_config.yml:285`), but the script file is `sase_chop_pr_submitted_checks.py`. This is bridged by a legacy alias entry point: `pyproject.toml:113` maps `sase_chop_cl_submitted_checks` to `sase.scripts:sase_chop_cl_submitted_checks`, which is a one-line forwarder to the PR-submitted `main()` (`src/sase/scripts/__init__.py:149-151`). So there are two console scripts (`sase_chop_pr_submitted_checks` and `sase_chop_cl_submitted_checks`) pointing at one implementation.
- **`pushgateway_cleanup` is an orphan builtin**: It has a module, a `main()`, and an entry point (`pyproject.toml:110`), but it is not referenced by any lumberjack in `default_config.yml` and is not in the user overlay's `lumberjacks:` block either (I grepped `~/.config/sase/sase.yml` — only `lumberjacks:` at line 97, no `pushgateway_cleanup`). It is runnable only via `sase axe chop run pushgateway_cleanup`. It is also the only builtin that takes **no `--context` argument** (`sase_chop_pushgateway_cleanup.py:7`).

---

## 2. Recurring patterns

### (0) The dominant pattern: an identical "read-context → build HookJobRunner → call one method" scaffold

9 of 13 scripts (`hook_checks`, `mentor_checks`, `workflow_checks`, `pending_checks_poll`, `comment_zombie_checks`, `suffix_transforms`, `orphan_cleanup`, `stale_running_cleanup`) are structurally identical. Representative (`sase_chop_hook_checks.py:14-33`):

```python
def main() -> None:
    parser = argparse.ArgumentParser()
    parser.add_argument("--context", required=True)
    args = parser.parse_args()

    ctx = read_chop_context(args.context)
    filtered = load_changespecs_from_file(ctx.filtered_changespecs_file)

    def log(message: str, style: str | None = None) -> None:
        print(message)

    runner = HookJobRunner(
        AxeMetrics(),
        ctx.zombie_timeout_seconds,
        ctx.max_hook_runners,
        ctx.max_agent_runners,
        log,
        verbose_diagnostics=ctx.verbose_lumberjack_diagnostics,
    )
    runner.run_hook_checks(filtered)
```

The only per-script variation is (a) which changespec file it loads (`filtered_changespecs_file` vs `all_changespecs_file` vs both vs none) and (b) the final `runner.run_*()` call. The other 4 scripts (`comment_checks`, `pr_submitted_checks`, `wait_checks`, `error_digest`) deviate but still repeat the `argparse(--context)` + `read_chop_context` + local `log` closure preamble (`pushgateway_cleanup` is the sole exception with no preamble at all).

Every script also redefines the same throwaway logger:

```python
def log(message: str, style: str | None = None) -> None:
    print(message)
```

This closure appears verbatim in 12 of 13 scripts (the `style` arg is always ignored — combined stdout/stderr is captured by the runner and the style is meaningless in a subprocess).

### (a) Polling external state

Polling is not done in the scripts; it's delegated. `pending_checks_poll` walks the on-disk check output directory once per tick and reaps orphans (`hook_jobs.py:229-278`):

```python
reaped = reap_orphan_check_files(self._log)
by_name = scan_all_pending_checks()
...
updates = process_pending_checks_for(changespec, pending, self._log)
```

`comment_checks` / `pr_submitted_checks` route through `CheckCycleRunner` (`check_cycles.py`), which is the layer that actually starts the background `gh`-backed checks (`start_cl_submitted_check`, `start_reviewer_comments_check`). `wait_checks` is the one script that polls filesystem state inline — it scans every project's agent artifact dirs for `waiting.json`/`ready.json`/`agent_meta.json` markers (`sase_chop_wait_checks.py:57-141`).

### (b) Gating / dedup so work isn't repeated — fragmented across many mechanisms

There is **no single dedup mechanism**. Each concern rolls its own "already handled?" state:

- **Run-level dedup** (don't start the same chop while a prior run is live) is handled once, centrally, by the shared runner via chop run-history — `active_script_chop_run` (`chop_runner_script.py:60-107`) inspects the head of the run index, trusts a live PID, and finalizes stale PID-less runs after a grace window. Scripts do **not** reimplement this. Good.
- **`run_every` throttle** — main-thread gate in the scheduler (`lumberjack.py:202-214`).
- **`sync_cache`** 5-minute throttle for PR-submitted checks (`check_cycles.py:251-255`, `should_check`/`update_last_checked`).
- **`has_pending_check(...)`** guards so a second background check isn't started (`check_cycles.py:258`, `:289`).
- **`waiting.json` already resolved → skip** guard, keyed on presence of `ready.json` (`sase_chop_wait_checks.py:79-82`).
- **`last_error_digest_ts` high-water mark** so the same errors aren't re-notified (`sase_chop_error_digest.py:48-57`; state at `_state_scheduler.py:206-230`).
- **prompt-hash + live-record dedup** for agent chops (`chop_agents.py:222-237`) — unused by these scripts but the sixth distinct dedup style in the subsystem.

### (c) Singleton / stale-lock cleanup

Three scripts are pure stale-claim reclaimers, each calling a different cleanup function:

- `orphan_cleanup` → `cleanup_orphaned_workspace_claims(all_cs, log)` (`hook_jobs.py:361-375`)
- `stale_running_cleanup` → `cleanup_stale_running_entries(log)` (`hook_jobs.py:377-386`)
- `comment_zombie_checks` → `check_comment_zombies(cs, timeout)` (`hook_jobs.py:280-311`)

Separately, the runner itself does stale-**run**-lock cleanup by finalizing dead-PID or PID-less-past-grace run entries (`chop_runner_script.py:110-141`, `_finalize_stale_script_chop_run`). And the chop-agent registry has *its own* live/dead pruning (`chop_agents.py:207-219`, `_is_live_record`/`_prune_chop_agent_records_unlocked`). So "detect a dead PID and release its claim" is implemented at least four times against four different state stores.

### (d) Launching agents / subprocesses in response to a condition

None of the scripts launch via the chop-agent path; they trigger launches indirectly:

- `mentor_checks` → `check_mentors(...)` starts mentor agents (`hook_jobs.py:139-180`).
- `workflow_checks` → `start_stale_workflows(...)` starts CRS/fix-hook workflow agents (`hook_jobs.py:182-227`).
- `hook_checks` → `check_hooks(...)` starts stale hook runners (`hook_jobs.py:93-137`).
- `comment_checks` / `pr_submitted_checks` → start background `gh`-backed check subprocesses (`check_cycles.py`).
- `wait_checks` → writes `ready.json`, which is the signal another process uses to unblock a waiting agent (`sase_chop_wait_checks.py:129-139`).

Concurrency/serialization policy lives in the scheduler, not the scripts: script chops run in a `ThreadPoolExecutor`, agent chops are run sequentially to avoid workspace races (`lumberjack.py:216-228`).

### (e) Telemetry / pushgateway

Only `pushgateway_cleanup` touches telemetry directly (`sase_chop_pushgateway_cleanup.py:4-10` → `telemetry.cleanup_stale_groups`, defined `telemetry/_registry.py:167`). Cycle/error telemetry is emitted centrally by the lumberjack, not the scripts (`lumberjack.py:24, 261-262, 494`: `AXE_CYCLES`, `AXE_CYCLE_DURATION`, `AXE_ERRORS`; `register_push_on_exit` at `:551`).

### (f) Error digest / notification

Only `error_digest` (`sase_chop_error_digest.py`) does this. It reads `recent_errors.json` (capped at 100, `_state_scheduler.py:173-203`), computes a 1-hour cutoff clamped to the last high-water mark, notifies via `notify_axe_error_digest`, then advances the high-water mark:

```python
cutoff = (datetime.now(get_timezone()) - timedelta(hours=1)).isoformat()
last_digest_ts = read_last_error_digest_ts()
effective_cutoff = max(cutoff, last_digest_ts) if last_digest_ts else cutoff
recent = [e for e in errors if e.get("timestamp", "") > effective_cutoff]
...
notify_axe_error_digest(recent)
write_last_error_digest_ts(newest_ts)
```

### (g) Structured one-line summary output — a strong shared convention that is not shared code

Every script (and every `HookJobRunner`/`CheckCycleRunner` method) prints a `key=value` summary line ending with a `reason=<...>` explaining any no-op. Examples: `sase_chop_wait_checks.py:143-161`, `hook_jobs.py:126-137`, `check_cycles.py:156-170`, `sase_chop_pushgateway_cleanup.py:9-10`. The format is a de-facto contract for log parsing but is hand-assembled with bespoke f-strings and per-script `reason` ladders in every location — no shared formatter.

---

## 3. How they're invoked

### Discovery (`chop_script_runner.py:18-53`, `discover_chop_script`)

The runner resolves a chop name to an executable in three ordered steps:
1. For each configured `chop_script_dirs`, look for an executable file named exactly `<name>` (`:34-37`). Default `chop_script_dirs` is empty (`default_config.yml:255`), so this is normally skipped.
2. Look in the running interpreter's bin dir for `sase_chop_<name>` (`:43-46`) — resilient to broken PATH symlinks during reinstall.
3. Fall back to `shutil.which("sase_chop_<name>")` on `$PATH` (`:48-51`).

So the operative naming convention is the `sase_chop_` prefix on a console script installed by `pyproject.toml:[project.scripts]` (lines 102-115), each of which imports `main` from the matching module in `src/sase/scripts/` (`scripts/__init__.py:83-163`). `list_chop_scripts` (`chop_script_runner.py:230-273`) enumerates available chops by scanning the same dirs + `$PATH` for the prefix.

### argv / env contract

- **argv**: `[script_path, "--context", context_file]` (`chop_script_runner.py:82-89` for the blocking variant, `:138-150` for the streaming variant). Every script parses exactly `--context` (required) and nothing else — except `pushgateway_cleanup`, which parses no args.
- **context file**: a JSON-serialized `ChopScriptContext` (`chop_script_context.py:24-37`) carrying `max_hook_runners`, `max_agent_runners`, `zombie_timeout_seconds`, `query`, `lumberjack_name`, `state_dir`, `all_changespecs_file`, `filtered_changespecs_file`, `verbose_lumberjack_diagnostics`. The lumberjack writes it once per tick along with two changespec snapshot files (`lumberjack.py:171-195`); one-shot runs rebuild the same trio via `build_oneshot_context` (`chop_runner_context.py:22-67`). All writes are atomic temp-then-rename (`chop_script_context.py:39-56`).
- **env**: The runner injects chop-identity env vars via `build_chop_launch_env` (`chop_agents.py:60-76`): `SASE_CHOP_LUMBERJACK`, `SASE_CHOP_NAME`, `SASE_CHOP_RUN_ID`, and (for agent chops) `SASE_CHOP_PROMPT_HASH` (`chop_runner_script.py:209-216`). Plus any `chop.env` overrides from config. These let agents launched downstream stamp `chop_*` fields into `agent_meta.json` for registry/dedup.
- **cwd**: set to the lumberjack `state_dir` (`chop_runner_script.py:254`) because the daemon's original launch dir may have been wiped (ephemeral workspaces).

### Exit codes & output capture

- **Exit codes**: `0` = success; nonzero → `_ChopResult`/`ChopRunOutcome` status `failure` with `exit_code` set (`chop_runner_script.py:300-340`). Timeout → SIGKILL of the whole process group, status `timeout` (`chop_script_runner.py:192-207`, `chop_runner_script.py:277-298`). A raise before/during streaming → `failure` with a Python traceback captured in the `except` block (`chop_runner_script.py:256-275`). Missing executable → `missing_script` (`chop_runner_script.py:177-207`).
- **Output capture**: The scheduler path uses `stream_chop_script` (`chop_script_runner.py:108-227`), which merges stdout+stderr (`stderr=STDOUT`), pumps them through a background thread into a per-run log file, records the child PID immediately via `on_pid` (`:182-190`, → `update_chop_run_pid`), and starts a new session so a timeout can kill grandchildren. The tail of that log is echoed into the aggregate lumberjack log on success/nonzero-exit (`lumberjack.py:392-407`, `read_chop_run_log_tail`). The one-shot CLI path (`sase axe chop run`) uses the same `run_configured_chop_once` and prints the tail + exits with a status-derived code (`axe/cli.py:72-166`).

### CLI / TUI entry

All three callers (scheduled tick, `sase axe chop run`, TUI manual run) funnel through the single service `run_configured_chop_once` (`chop_runner.py:139-182`), which dispatches agent-vs-script and does the run-level dedup. `sase axe chop list` / `doctor` provide inventory and diagnostics (`axe/cli.py:29-68`).

---

## 4. What's hand-rolled that a richer chop-config or shared library could absorb

Concrete, quotable duplication:

1. **The 9-way boilerplate clone (biggest win).** `hook_checks`, `mentor_checks`, `workflow_checks`, `pending_checks_poll`, `comment_zombie_checks`, `suffix_transforms`, `orphan_cleanup`, `stale_running_cleanup` differ only in (a) which changespec file they load and (b) which single `HookJobRunner.run_*` method they call. The `HookJobRunner(AxeMetrics(), ctx.zombie_timeout_seconds, ctx.max_hook_runners, ctx.max_agent_runners, log, verbose_diagnostics=ctx.verbose_lumberjack_diagnostics)` construction is copy-pasted 9 times (e.g. `sase_chop_hook_checks.py:25-32`, `sase_chop_mentor_checks.py:25-32`, `sase_chop_orphan_cleanup.py:25-32`, `sase_chop_stale_running_cleanup.py:21-28`, …). A shared helper — e.g. `run_hook_job(ctx, method_name, changespec_scope)` or a tiny decorator/registry — plus a config field declaring `{needs: filtered|all|both|none}` would collapse all nine into config rows. Today adding a chop means: new module + `main()` + `__init__.py` wrapper + two `pyproject.toml` entry-point lines + a `default_config.yml` row — five edit sites.

2. **The `log` closure duplicated 12×.** `def log(message, style=None): print(message)` is redefined in nearly every script (`sase_chop_comment_checks.py:17-18`, `sase_chop_wait_checks.py:37-38`, etc.). It ignores `style`, which is dead weight in a subprocess. A shared `chop_stdout_logger()` (or having `read_chop_context` also return a ready-made logger) removes it everywhere.

3. **`argparse(--context)` + `read_chop_context` + `load_changespecs_from_file` preamble.** Repeated in all 12 context-taking scripts. A single `@chop_script(scope=...)` entry helper could parse `--context`, hydrate the context, load the requested changespec scope, and hand the body a typed object — eliminating the argparse/log/hydrate triad from every file.

4. **Fragmented "already handled?" state (the deepest structural duplication).** Six independent dedup/gating stores coexist: chop run-history (`chop_runner_script.py`), `run_every` timestamps (`lumberjack.py`), `sync_cache` (`check_cycles.py:251-255`), `has_pending_check` files (`check_cycles.py:258,289`), `waiting.json`/`ready.json` markers (`sase_chop_wait_checks.py:79-82`), and `last_error_digest_ts` (`error_digest`). A richer chop-config could declare a dedup key / cadence / high-water-mark policy per chop and let the runner enforce it, instead of each downstream library inventing its own.

5. **Dead-PID reclamation implemented ~4×.** `active_script_chop_run` finalizes dead runs (`chop_runner_script.py:86-107`), `chop_agents._is_live_record` prunes dead agent records (`chop_agents.py:207-219`), `cleanup_stale_running_entries` (`hook_jobs.py:377`) and `cleanup_orphaned_workspace_claims` (`hook_jobs.py:361`) each reclaim workspace claims from dead PIDs. All four re-answer "is this PID alive, and if not, release its lock" against different files. A shared "PID-lease" abstraction could unify them.

6. **The `key=value ... reason=<...>` summary line is a convention, not a library.** Assembled by hand in every runner method and script with bespoke `reason` ladders (`hook_jobs.py:126-137`, `check_cycles.py:156-170`, `sase_chop_wait_checks.py:143-161`, `sase_chop_pushgateway_cleanup.py:9-10`). A shared `emit_chop_summary(chop, counters, reasons=...)` would standardize the log-parsing contract.

7. **The `cl_submitted_checks`/`pr_submitted_checks` alias** (`__init__.py:149-151`, dual entry points `pyproject.toml:112-113`) is legacy-naming debt a name-normalization layer in the registry could retire.

8. **`pushgateway_cleanup` is a config-orphan** — a builtin script and entry point that no default lumberjack references. Either wire it into `housekeeping` or drop it; today it silently exists only for manual `sase axe chop run`.

### Relevant files (all absolute)

- Scripts: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/scripts/sase_chop_*.py` and the entry-point wrappers `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/src/sase/scripts/__init__.py`
- Runner/registry: `src/sase/axe/chop_runner.py`, `chop_runner_script.py`, `chop_runner_context.py`, `chop_script_runner.py`, `chop_script_context.py`, `chop_agents.py`
- Business logic: `src/sase/axe/hook_jobs.py`, `check_cycles.py`; scheduler modules under `src/sase/ace/scheduler/`
- Scheduler loop: `src/sase/axe/lumberjack.py`; config: `src/sase/axe/config.py`; state: `src/sase/axe/_state_scheduler.py`, `_state_chops.py`
- Wiring & entry points: `src/sase/default_config.yml:256-298`, `pyproject.toml:102-115`
- Telemetry: `src/sase/telemetry/_registry.py:167`

I did not edit any files.

I have everything I need. Let me compile the report.

---

# CHEZMOI CUSTOM-CHOPS Audit — Lumberjack/Chop Subsystem

All paths below are absolute. The chezmoi linked repo root is
`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/linked/chezmoi` (abbreviated `<chez>` below). The referenced xprompt workflows live in the primary sase repo at `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/xprompts/` (abbreviated `<repo>/xprompts` below — the `sase/` namespace in `#!sase/…` = the sase project).

Note on terminology: the two files the task calls "bash chop scripts" are actually **Python 3** programs (`#!/usr/bin/env python3`), only their *test harnesses* are bash. Chezmoi's `executable_` filename prefix just marks the deployed file executable; the deployed name drops it, giving `sase_chop_sase_fix_just` and `sase_chop_gh_actions_fix`.

---

## How chops bind to config (grounding)

The chop config model is `ChopConfig` at `<repo>/src/sase/axe/config.py:32-41`. The **only** first-class fields are:

```
name, description, agent (aka xprompt), run_every, timeout, env
```

Parsing (`config.py:100-121`): a chop is an **agent chop** iff it has an `agent:` (or `xprompt:`) key; otherwise it is a **script chop**, resolved by name. Script resolution strips the `sase_chop_` prefix (`<repo>/src/sase/axe/chop_inventory.py:185-188`), so config `name: sase_fix_just` → executable `sase_chop_sase_fix_just`, and config `name: gh_actions_fix` → `sase_chop_gh_actions_fix`. There is **no `script:` field and no per-chop gating/guard/matrix field** — anything beyond name/agent/run_every/timeout/env must be pushed into an external script or into the xprompt body. The lumberjack passes each script chop a context JSON exposing `state_dir` and `all_changespecs_file` (`<repo>/src/sase/axe/chop_script_context.py:33-34`).

---

## 1. Custom chop inventory

### Script chops (name-resolved to chezmoi `home/bin/` executables)

| # | Chop name | Lumberjack | Cadence (`run_every`) | Kind | What it does |
|---|-----------|-----------|----------------------|------|--------------|
| 1 | `sase_fix_just` | `run_every` | `60m` | Script → `<chez>/home/bin/executable_sase_chop_sase_fix_just` | Guard: if any open ChangeSpec named `sase_fix_just_*` (status WIP/Draft/Ready/Mailed) exists, do nothing; else launch one agent that runs the `fix_just` xprompt workflow. |
| 2 | `gh_actions_fix` | `github_actions` | `15m` (+ `timeout: 120s`, `env: SASE_GHA_FIX_REPOS`) | Script → `<chez>/home/bin/executable_sase_chop_gh_actions_fix` | For each repo in `SASE_GHA_FIX_REPOS`, poll the latest GH Actions run; if it failed (and not already handled, and no open `sase_gha_fix_*` ChangeSpec), fetch failed-step logs and launch a fixer agent seeded with that log. |

Config: `<chez>/home/dot_config/sase/sase_athena.yml:75-77` (fix_just) and `:124-129` (gh_actions_fix).

### Agent chops (config `agent:` prompt strings, `sase_athena.yml`)

| # | Chop name | Lumberjack | Cadence | Kind | `agent:` prompt (what it does) |
|---|-----------|-----------|---------|------|-------------------------------|
| 3 | `sase_pylimit_split` | `run_every` | `60m` | Agent | `%n:sase_pylimit_split-@ #gh:sase %g:chop #!sase/pylimit_split %auto` — runs pylimit_split xprompt (splits over-long Python files). `:71-73` |
| 4 | `sase_recent_bug_audit` | `code_quality` | `60m` | Agent | `%n:sase_recent_bug_audit-@ #gh:sase %g:chop #!sase/audit_recent_bugs` `:81-84` |
| 5 | `sase_recent_improvement_audit` | `code_quality` | `60m` | Agent | `%n:sase_recent_improvement_audit-@ #gh:sase %g:chop #!sase/audit_recent_improvements` `:85-88` |
| 6 | `sase_refresh_docs` | `refresh_docs` | `3h` | Agent | `%n:sase_refresh_docs-@ #gh:sase-org/sase %g:chop #!sase/refresh_docs` (defaults: project=sase, threshold=100) `:92-95` |
| 7 | `sase_core_refresh_docs` | `refresh_docs` | `24h` | Agent | `…#!sase/refresh_docs(project=sase-core, gh_ref=sase-org/sase-core, threshold=25)` `:96-101` |
| 8 | `sase_github_refresh_docs` | `refresh_docs` | `24h` | Agent | `…#!sase/refresh_docs(project=sase-github, gh_ref=sase-org/sase-github, threshold=25)` `:102-107` |
| 9 | `sase_nvim_refresh_docs` | `refresh_docs` | `24h` | Agent | `…#!sase/refresh_docs(project=sase-nvim, gh_ref=sase-org/sase-nvim, threshold=25)` `:108-113` |
| 10 | `sase_telegram_refresh_docs` | `refresh_docs` | `24h` | Agent | `…#!sase/refresh_docs(project=sase-telegram, gh_ref=sase-org/sase-telegram, threshold=25)` `:114-119` |

### Related (builtin) chops configured in chezmoi — env only

`<chez>/home/dot_config/sase/sase.yml:96-111` configures two **builtin** script chops purely through `env:` (no `agent:`, no chezmoi script):

- `tg_inbound` / `tg_outbound`, lumberjack `telegram`, `interval: 5`, no `run_every` (every tick). Both carry the same credentials: `SASE_TELEGRAM_BOT_USERNAME: sase_athena_bot` and `SASE_TELEGRAM_BOT_CHAT_ID: "8990449281"`. Relevant to the credentials-in-config gap (§3c).

---

## 2. The agent-chop directive pattern, decoded

Canonical example (`sase_athena.yml:73`):
`"%n:sase_pylimit_split-@ #gh:sase %g:chop #!sase/pylimit_split %auto"`

| Token | Meaning |
|-------|---------|
| `%n:sase_pylimit_split-@` | Agent **name template**. `%n:` (= `%name:`) sets the launched agent's name; base is `sase_pylimit_split`, and the trailing `-@` is the template disambiguator that yields a stable unique name (same `-@` template mechanism documented in `<repo>/src/sase/xprompts/skills/sase_var.md:13,21,30`, e.g. `%name:build-@`). |
| `#gh:sase` | GitHub **VCS workflow block** — run the agent in a workspace/clone of the repo aliased `sase`. In the refresh_docs chops this is spelled `#gh:sase-org/sase` (full org/repo ref). |
| `%g:chop` | Sets the agent's **group** to `chop` (= `%group:chop`), so every chop-launched agent nests under the `chop` root entry on the ACE "Agents" tab. Appears in **every** chop agent string. |
| `#!sase/pylimit_split` | **Invoke the xprompt workflow** `pylimit_split` from the `sase` project's `xprompts/` dir. The `#!` form runs the multi-step `.yml` workflow (vs. `#foo` which inlines an xprompt part/snippet). |
| `%auto` | **Autonomous** mode (auto-approve; no human gating). Notably present only on `sase_pylimit_split`; the audit/refresh chop strings omit it, and the fix_just script's prompt omits it too — an inconsistency. |
| `(project=…, gh_ref=…, threshold=…)` | **xprompt input parameters** bound to the workflow's `input:` fields (`refresh_docs.yml:4-16` defines `project`, `gh_ref`, `threshold`). |

**What recurs / is hand-assembled in every agent string:** the same four-token scaffold `%n:<name>-@ #gh:<repo> %g:chop #!sase/<xprompt>`. The name is a manual restatement of the chop's own `name:`, the `#gh` repo is manually restated, and `%g:chop` is manually re-typed on every single chop even though the lumberjack already *knows* it is launching a chop agent. Only the last token (`#!sase/<xprompt>` and its params) actually varies meaningfully.

The **same scaffold is also hard-coded inside the two Python scripts**, not just the YAML:
- `executable_sase_chop_sase_fix_just:14` — `FIX_JUST_PROMPT = "%n:sase_fix_just-@ #gh:sase %g:chop #!sase/fix_just"`
- `executable_sase_chop_gh_actions_fix:380` — `f"#gh:{repo} %g:chop #pr({change_name}) %n:{run_agent_name}"`

And it recurs a **third** time inside the xprompt workflows themselves when they fan out child agents (e.g. `refresh_docs.yml:102-104` builds `%name:… #gh:{gh_ref} %g:chop #sase/docs`; `audit_recent_bugs.yml:114-115` builds `%name:… #gh:{gh_ref} %g:chop #pr({pr_name})`). So the `%g:chop` + `#gh` + name-template triple is hand-assembled at three layers: YAML config, wrapper scripts, and xprompt Python steps.

---

## 3. Boilerplate & capability gaps (what should arguably be first-class)

### (a) Per-project fan-out — the 5 near-identical `refresh_docs` chops
`sase_athena.yml:89-119` defines five chops that are **identical except three values**: `project`, `gh_ref`, and (for four of them) `threshold=25` + `run_every: 24h`. Concretely, the four non-default entries differ only in the substring `sase-core` / `sase-github` / `sase-nvim` / `sase-telegram`:

```yaml
agent: "%n:sase_core_refresh_docs-@ #gh:sase-org/sase %g:chop
        #!sase/refresh_docs(project=sase-core, gh_ref=sase-org/sase-core, threshold=25)"
```

This is a textbook matrix/fan-out: one template × N projects. There is no `matrix:`/`for_each:` construct in `ChopConfig` (`config.py:32-41`), so the user copy-pastes the whole chop five times. The same pattern is latent in the audit chops too: `audit_recent_bugs.yml` / `audit_recent_improvements.yml` accept `project`/`gh_ref`/`threshold` inputs, but the config only ever instantiates them once (project=sase), because adding more projects would mean more copy-paste. A first-class per-project fan-out would collapse all of §1 rows 6-10 (and enable multi-project audits) into one templated entry.

### (b) VCS / commit-workflow boilerplate repeated in every agent string
As shown in §2, `#gh:<repo> %g:chop` plus a `%n:<name>-@` name template is restated on every chop, in every wrapper script, and in every xprompt fan-out. `%g:chop` in particular is pure boilerplate — the chop runner already tags agents with a `chop_prompt_hash` (`<repo>/src/sase/axe/chop_agents.py:111`), so it clearly knows these are chop agents; the group could be injected automatically. Candidate first-class fields: a chop/lumberjack-level `repo:` (feeding `#gh`), automatic group assignment, and an automatic name derived from the chop `name` (removing the `%n:<name>-@` restatement).

### (c) Env / credentials handling done via raw `env:` maps
Credentials and target lists are inlined as plaintext env in config:
- `sase.yml:103-110` — the Telegram bot username `sase_athena_bot` and **chat ID `8990449281`** are duplicated verbatim across both `tg_inbound` and `tg_outbound` (no shared/lumberjack-level env, no secret reference).
- `sase_athena.yml:128-129` — `SASE_GHA_FIX_REPOS: "bbugyi200/dotfiles sase-org/sase"`: the fixer's **repo target list is a space-separated string smuggled through an env var**, then re-parsed in Python (`executable_sase_chop_gh_actions_fix:106-107`, `split_repos` on `[\s,]+`). This is really a list-of-repos config field masquerading as an env string, and it overlaps conceptually with the per-project fan-out that (a) wants — two different chops express "a set of repos" two different ways (env string vs. copy-pasted chops).

### (d) Gating conditions expressed imperatively instead of in config
Every custom chop reinvents its own idempotency/gating, none of it declarable:
- **Open-ChangeSpec guard** (don't re-launch while a repair PR is open): hand-coded identically in both scripts — `executable_sase_chop_sase_fix_just:59-90,142-149` and `executable_sase_chop_gh_actions_fix:155-186,514-521`, keyed on prefixes `sase_fix_just_` / `sase_gha_fix_` and status set `{"WIP","Draft","Ready","Mailed"}`. This is duplicated verbatim logic that reads `all_changespecs_file` from the chop context.
- **Commit-count threshold gate** (only run when ≥N new commits since a marker): reimplemented three times, near-identically, inside the xprompts — `refresh_docs.yml:19-83`, `audit_recent_bugs.yml:19-93`, `audit_recent_improvements.yml:19-93`. All three do the same marker read → `git rev-list --count` → `999`-force-on-first-run → `should_launch` dance, then a symmetric `update_*_marker` step (`refresh_docs.yml:123-141`, etc.). The `count >= threshold` "should I run?" decision is config-shaped but lives in Python.
- **Run-once dedupe by run/attempt**: `gh_actions_fix` keeps its own JSON state file `gh_actions_fix_seen.json` keyed `"{run_id}:attempt:{attempt}"` (`executable_sase_chop_gh_actions_fix:31,464-492`) — another bespoke idempotency store.
- **Conclusion filtering**: actionable vs. ignored GH conclusions are hard-coded sets in Python (`:17-28`), not config.

Net: three independent "should this chop fire this tick?" gate mechanisms (open-ChangeSpec-prefix, commit-count-marker, seen-run dedupe) all live in code because `run_every` is the *only* gating primitive config offers.

### (e) Naming templates hand-built in code
PR/agent names are constructed with ad-hoc slugify logic rather than a naming template:
- `executable_sase_chop_gh_actions_fix:344-354` — `repo_slug`, `pr_name` (`gha_fix_{slug}_{run_id}_a{attempt}`), `agent_name` (`gha-fix-{slug}-{run_id}-a{attempt}`).
- The xprompts each roll their own `re.sub(r"[^A-Za-z0-9_.]+","_", …)` slug + `name_prefix` / `pr_name` (`refresh_docs.yml:97-99`, `audit_recent_bugs.yml:108-111`, `audit_recent_improvements.yml:108-111`).

Every chop invents the same "slugify project/repo → build stable agent name + PR name" recipe.

---

## 4. What the two Python chop scripts do that config can't express

### `executable_sase_chop_sase_fix_just` (Python, 158 lines)
Purpose (docstring): "Launch the SASE fix_just workflow unless an open repair ChangeSpec exists."
- **Gating (the crux):** reads the chop context JSON, loads the `all_changespecs_file` snapshot, and blocks launch if any ChangeSpec named `sase_fix_just_*` is in an open status (`{WIP,Draft,Ready,Mailed}`) — `:59-90,135-149`. On a missing/unreadable snapshot it fails **safe** (skip, exit 0) rather than launching — `:136-141`.
- **Launch:** if unblocked, runs `sase run -d "%n:sase_fix_just-@ #gh:sase %g:chop #!sase/fix_just"` — `:111-123` with the prompt constant at `:14`.
- **"Config that became code":** the entire body is a conditional (open-ChangeSpec-prefix guard) wrapped around what is otherwise a plain agent chop. If config supported a declarative "don't relaunch while an open ChangeSpec with prefix X exists" guard, this whole script disappears and `sase_fix_just` becomes a one-line agent chop like `sase_pylimit_split`.

### `executable_sase_chop_gh_actions_fix` (Python, 551 lines)
Purpose: "Launch a SASE fixer agent for the latest failed GitHub Actions run."
- **Fan-out over repos:** parses `SASE_GHA_FIX_REPOS` (env string) into a repo list (`:106-107,528-529`) and loops (`:539-542`).
- **Polling:** `gh run list -R <repo> -L 1 --json …` for the latest run (`:235-278`).
- **Gating / thresholds (multiple layers):**
  - Same open-ChangeSpec guard as fix_just, prefix `sase_gha_fix_`, runs **before any `gh` call** (`:507-521`; the test `test_open_gha_changespec_blocks_before_gh_calls` asserts zero gh calls).
  - Status must be `completed` and conclusion must be in `ACTIONABLE_CONCLUSIONS = {action_required, failure, startup_failure, timed_out}`; `IGNORED_CONCLUSIONS` short-circuit (`:17-28,444-456`).
  - Per-run/attempt dedupe via `gh_actions_fix_seen.json` keyed `"{run_id}:attempt:{attempt}"`, persisted atomically (`:198-223,464-492`) — a new attempt relaunches (`:218-231` test).
- **Log harvesting:** `gh run view --log-failed`, falling back to `--verbose`, truncated to the last 60 KiB (`:287-341`).
- **Prompt assembly + launch:** builds a rich seeded prompt (`build_prompt`, `:364-407`) with `#gh:{repo} %g:chop #pr({change_name}) %n:{run_agent_name}` plus run metadata and a fenced log block, then `sase run -d <prompt>` (`:410-416`).
- **Observability:** structured per-repo outcomes and a `RunSummary` (`:41-91`) — effectively bespoke chop telemetry.
- **"Config that became code":** the parts that are essentially config are: the repo list (env string → should be a config list / matrix), the actionable/ignored conclusion sets, the `run_every`-adjacent dedupe policy, the open-ChangeSpec guard (duplicated from fix_just), and the timeout. The genuinely-imperative remainder that config *can't* express today is the `gh` polling + failed-log fetch/truncation + dynamic prompt seeding from live run output — i.e., "gather external state and inject it into the launch prompt," which no declarative agent chop currently supports.

---

## Key takeaways for the research report

1. **One scaffold, three copies.** `%n:<name>-@ #gh:<repo> %g:chop #!<xprompt>` is hand-assembled in YAML config, in the wrapper Python scripts, and again inside the xprompt fan-out steps. `%g:chop` and the name-template are pure boilerplate the chop runner could inject.
2. **`run_every` is the only declarative gate**, so three separate bespoke gating mechanisms exist in code: open-ChangeSpec-prefix guards (duplicated across both scripts), commit-count markers (triplicated across three xprompts), and per-run dedupe state. All are config-shaped.
3. **Fan-out is faked by copy-paste** (5 refresh_docs chops) or **by env-string list** (`SASE_GHA_FIX_REPOS`) — two inconsistent expressions of "run this across N repos/projects" that a first-class matrix field would unify.
4. **Credentials/targets are plaintext `env:`** duplicated across chops (Telegram chat ID; GHA repo list).
5. **The two scripts exist almost entirely to add a guard/poll layer** that config lacks: `sase_fix_just` is a one-guard wrapper around an ordinary agent chop; `gh_actions_fix` is a repo-fan-out + GH-poll + dedupe + prompt-seeding harness. The declarative residue (repo list, thresholds, conclusion filters, ChangeSpec guard) is the strongest candidate for promotion to first-class chop-config features; only the live-state harvesting in `gh_actions_fix` is inherently imperative.

No files were edited.

Builtin-scripts agent is back with rich detail (9-of-13 clone scaffold, 5 edit-sites to add a chop, six fragmented dedup stores, `pushgateway_cleanup` config-orphan). Now just waiting on the chezmoi custom-chops agent.

All three audit agents are back with detailed, corroborating findings. I have a complete picture from first-hand reading plus the three deep-dives. Let me create the `202607/` directory and write the research report.

Done. The research report is written to:

**`sase/repos/research/202607/improving_lumberjacks_chop_config.md`** (resolved via `sase sdd path research`, the `sase--research` linked repo).

I audited the `axe` engine, all 13 builtin chops, and — as you asked — your chezmoi-defined chops specifically (not just the builtins). Here's the gist:

**What chop config allows today (deliberately thin):** a chop declares only `name`, `description`, `agent`/`xprompt`, `run_every`, `timeout`, and a static `env`; a lumberjack adds `interval` and `chop_timeout`. Two chop kinds, switched by one field — script chops (`sase_chop_<name>` executables) and agent chops (a full `sase run` prompt). Gating is limited to `run_every` + a global maintenance marker + implicit singleton dedupe. No `enabled`, no conditional triggers, no dependencies, no fan-out, no retries/jitter, no schema validation (typos fail silently), and — a latent bug — `env:` is **silently dropped on agent chops**.

**The core finding:** config is a *thin launcher*. Every *when-to-actually-fire*, *what-to-run-it-across*, and *how-to-name-the-agent* decision has escaped into imperative code. Your chezmoi chops are the proof:
- **`gh_actions_fix`** = a 551-line program whose declarative residue (repo list, actionable-CI conclusions, dedupe-by-run, open-ChangeSpec guard, timeout) is all config-shaped; only its live-log harvesting is truly code.
- **`sase_fix_just`** = 158 lines that are *almost entirely one guard* around a one-line agent chop.
- **5 `*_refresh_docs` chops** = a matrix faked by copy-paste (differ only in `project`/`gh_ref`/`threshold`).
- The scaffold `%n:<name>-@ #gh:<repo> %g:chop #!sase/<xprompt>` is hand-assembled in **three layers** (YAML, wrapper scripts, xprompt fan-out); `%g:chop` and the name are pure boilerplate.
- Three separate bespoke gating mechanisms live in code because `run_every` is the only declarative gate.

**Top recommendations (ranked in the report):**
1. **Declarative guards/triggers** — `no_open_changespec:`, `commits_since_marker:`, `once_per:` — retires `sase_fix_just` entirely and un-triplicates the marker logic.
2. **`for_each:` matrix fan-out** — collapses the 5 refresh_docs rows and unifies with `SASE_GHA_FIX_REPOS`.
3. **Auto-injected agent scaffold** (`repo:` + auto group/name) so an agent chop is just `#!xprompt`.
4. **Env parity + shared/secret env** (fix the agent-chop drop; de-dup Telegram creds).
5. **Schema validation** + richer durations.

The report also flags what should *stay* imperative (gh live-state harvesting), notes the internal DX cost (9-of-13 builtins are clones; adding one takes 5 edit-sites), and observes that per the repo's Rust-core boundary rule, new gating/fan-out logic likely belongs in `sase-core`.

I did not commit — say the word if you'd like me to commit it to the research repo, or generate a companion infographic.
