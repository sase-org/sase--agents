# Chat History - ace-run

- **TIMESTAMP:** 2026-07-08 00:46:59 EDT
- **MODEL:** claude/opus
- **AGENT:** research.1.cld
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260708_003316.md`

## Prompt

%name:research.@.cld %m:@research_assist %g:research #gh:gh_sase-org__sase The sase doctor command is crucial for sase since there are so many required prerequisites that users need to fulfill in order to get the best experience out of sase. Can you do some research to help me improve this command? One thing you should definitely look for is new diagnostics that we can surface that genuinely reveal missing functionality in sase due to unfulfilled requirements. End your analysis with a ranked set of recommended improvements. Write this research to a new markdown file under the sdd/research/$(date +%Y%m)/ directory.


## Response

I'll research the `sase doctor` command to understand its current diagnostics and find opportunities for improvement. Let me start by exploring the codebase.

There's a substantial `doctor/` module. Let me explore its structure and the overall architecture.

Let me read the runner and understand the check architecture, plus the handler/parser.

Let me look at the diagnostics framework and understand the check spec structure.

This gives me a clear picture of the framework. Now let me read all the actual check implementations to inventory current coverage. Let me batch-read them.

Let me read the deep checks, plugins, workspace, and telemetry checks.

Let me read the remaining check files: workspace, project, beads, telemetry, tools, axe, agent_index.

Let me read the remaining check files: beads, telemetry, tools, axe, agent_index.

Let me read the axe, agent_index, and config checks.

Let me read the remaining config checks to complete the inventory.

I now have a full inventory of existing checks. Let me search for "silent degradation" patterns across the codebase — places where features get disabled when prerequisites are unmet — to find genuine gaps. Let me run several searches in parallel.

This reveals a rich set of silent-degradation points. Let me dispatch parallel investigation agents to deeply analyze the most promising gap areas — each will return concrete findings with evidence and severity.

I'll investigate this systematically. Let me start by exploring the relevant directories in parallel.

Let me read the provider modules and the subprocess launchers in parallel.

Now let me read qwen.py, agy.py, registry.py, and config.py.

I'll research the tmux and terminal capability usage across the codebase. Let me start with several parallel investigations.

Let me examine the core tmux files for launch/attach behavior.

Now let me look at the registry, config, and search for credential/auth/node references across the codebase.

I'll research the optional integrations and where they silently degrade. Let me start with parallel exploration.

Now let me examine the graphics viewer files and how agents are actually launched.

The node/npm matches look like tree-node false positives. Let me do more targeted searches for real node/npm prerequisite checks, credential detection, and how agent launch failures surface.

Let me launch two more investigation agents covering skills/deployment tooling and system-level resources.

Let me investigate agent launch requirements, terminal capability detection, and version checks.

sase_telegram isn't installed. Let me explore the notifications, doctor directories, and retry MCP grep case-insensitively.

Let me examine the agent launch path and the runtime checks to see what prerequisites are already validated.

No MCP in Python. Let me examine the doctor framework, notification senders, and telegram/plugin references.

Let me check the actual credential storage locations on this system and how provider invocation errors surface in the run/workflow path.

I'll research the `sase doctor` command and the various tools/systems mentioned. Let me start by reading the key files in parallel.

MCP is absent from this repo. Let me examine mobile_gateway, mobile_notifications, the store, and telegram references.

Let me read the remaining files mentioned in the task in parallel.

Let me confirm how agents are actually spawned (not via tmux) and examine what consumes the viewer warnings and truecolor context.

Strong evidence found. Let me verify opencode/qwen auth locations more precisely and examine how invocation errors surface to the user.

Now let me read the fzf usage sites and the doctor runner/registration structure.

Now let me examine telegram references, the plugin system, and config sections.

I'll research this systematically. Let me start by exploring the doctor module and the workspace provider in parallel.

Let me read the doctor runner and registry to understand how checks are registered, and look at how init planners are registered.

Let me examine the diagnostics framework, existing check patterns, and how tmux warnings surface to the user.

While those agents investigate, let me examine the research directory format and check for existing doctor documentation and any related prior research.

The axe subsystem already has a telegram doctor. Let me read it fully and see how it relates to `sase doctor`.

Let me explore the workspace creation, deep checks, telemetry, and key system dependencies in parallel.

There's prior doctor research and an epic. Let me read them to build on prior intent rather than duplicate it.

Now let me find where workspaces are actually materialized (git clone), and grep for inotify/watchdog/chezmoi usage.

Let me verify the opencode/antigravity credential paths precisely and check whether any provider hook exists for credential locations.

Telegram is already covered by `sase doctor` via `axe.chops`. Now let me examine the diagnostics framework, the config section, telemetry check (a model), and how notifications reach the gateway.

Key finding emerging: `check_config_init` runs all init planners including `plan_init_skills`. Let me verify what's surfaced where, and check fzf/clipboard/prettier references across doctor and the prompt-history doctor.

Let me examine the file-watching mechanism and the actual git-clone materialization plugin.

The prior research is the MVP design — now implemented. Notably its mockup showed a `plugins.telegram_env` check and the old `sase plugin doctor` covered "Telegram env" and `pass`, but the current `sase doctor` plugin checks only cover resources + github. Let me verify whether telegram/pass checks were dropped.

Let me examine the diagnostics models and trace how mobile_gateway/push/fcm is used across the codebase.

Let me read the pyproject dependencies, the startup watcher, and find the actual ArtifactWatcher/inotify implementation and the workspace clone materialization.

`fzf`/`clipboard` are surfaced only by a separate `sase prompt doctor` command, not `sase doctor`. Let me confirm that command and trace clipboard usage and the skills inventory.

Let me do a final check on env-var API key handling (a false-positive risk for credential-file checks) and confirm the codex `login status` precedent.

Let me read the fs_watcher implementation (errno handling) and find where ephemeral numbered workspaces are cloned.

Let me check how `config.init` is registered (default vs deep) and what binaries the runtime/deep checks already cover.

Telegram/`pass` checks live in `axe/chop_doctor.py` and ARE surfaced via the `axe.chops` doctor check — but only for configured chops. Good to know. Let me check whether the agent-launch path has a preflight that doctor could mirror, and read the remaining config checks.

Now let me read the ephemeral workspace clone logic in utils.py and check chezmoi usage and the doctor runner/mode configuration.

Let me examine notification delivery side-effects and whether push/telegram delivery is triggered, plus check for any config validation of mobile_gateway.

There's a `launch_validation.py` preflight — directly relevant to "what's required at launch." Let me read it and check on agent progress.

Let me examine the existing workspace and tools checks, chezmoi requirement, and any update/version remote self-check.

There's already a `SkillsInventory` with current/stale/missing status. Let me read the rest and find where it's consumed.

Let me check clipboard consumers and any tmux passthrough / TERM assumptions.

The launch validation is about name collisions, not prerequisites. Let me quickly complete my inventory of the two remaining config checks, then await the agents.

Let me check chezmoi as a config prerequisite, gh/GitHub network usage, update self-check, and any existing disk/ulimit checks.

I now have a complete inventory of existing checks. Let me check on the background agents' progress.

Let me check the existing tools check to see if the gateway binary is already covered and model a binary check.

Let me confirm the gh auth check (network) and whether dev_update pings a remote for version checks.

I have strong evidence. Let me verify a couple of specifics: the prettier usage in precommit hooks and agent prompt preprocessing, and the fzf editor flow.

I have a complete picture. Let me do a final confirmation on the mobile gateway CLI flags and confirm no MCP/auto-start exists.

I've completed my direct inventory of all existing `sase doctor` checks and the original design research. Five investigation agents are running in parallel to deeply probe the highest-value gap areas (provider auth, tmux/terminal, notifications/integrations, skills/tooling deployment, and system resources). I'll synthesize their findings into the ranked research report once they report back.

Let me wait for them to complete.

Let me measure the actual workspace size and confirm the inotify proc files are readable, plus check the polling fallback cadence.

The five investigation agents are running in the background. I'll continue once their findings arrive and synthesize everything into the ranked research report.

I have all the evidence I need. Here is my report.

---

# `sase doctor` — Feasibility of an offline provider-auth diagnostic (`llm.auth`)

## (a) Key findings, with citations

**The gap is real and deliberate.** The provider checks stat the CLI on PATH only and hard-code an "auth not verified" disclaimer:
- `src/sase/doctor/checks_providers.py:47-49` — `_AUTH_NOT_VERIFIED = "auth: not verified (doctor is read-only and does not call provider APIs)"`, injected into every `llm.default` result (`:163`, `:212`) and stamped into `data` as `"auth_status": "not_verified"` (`:177-178`, `:267-268`).
- The only real check is `_resolve_executable()` (PATH / `SASE_<PROVIDER>_PATH`) at `checks_providers.py:407-418`.

**Precedent for running a provider's own auth-status command already exists.** `checks_plugins.py:138-196` runs `gh auth status` with a 5s timeout and maps returncode→WARN. Note this *does* hit the network, so it is a precedent for auth-verification but not for the strict "offline" bar.

**How an unauthenticated-but-installed provider fails today (deep and late):**
1. Each provider builds `["claude"/"codex"/... , ...]` and runs it via `subprocess.Popen` — `claude.py:223-315`, `codex.py:342-468`, `opencode.py:170-279`, `qwen.py:165-278`, `agy.py:421-573`. The `FileNotFoundError` guards there only cover a *missing binary*, not a missing login.
2. An unauthenticated CLI runs, exits non-zero (auth error on stderr/stdout), and the provider raises `subprocess.CalledProcessError` (e.g. `claude.py:269-275`).
3. `invoke_agent()` catches it at `_invoke.py:282-305`, wraps the raw provider stderr into `LLMInvocationError`, and re-raises. The user sees the provider's own cryptic auth error inside a *failed agent run's* artifacts — not at `sase doctor` time. Invocation happens from the run/workflow path (`_invoke.py:232-243`, also `axe/runner_utils.py:285`, `commit_finalizer.py:227`).

**Confirmed credential locations on this live machine** (all `0600`, well-known, statable read-only):

| Provider | Credential file (confirmed) | Notes |
|---|---|---|
| claude | `~/.claude/.credentials.json` | JSON key `claudeAiOauth` (OAuth login). |
| codex | `~/.codex/auth.json` | keys `auth_mode`, `OPENAI_API_KEY`, `tokens`, `last_refresh`. Written by both OAuth and `--api-key` login. Codex provider even symlinks this into its shadow `CODEX_HOME` (`codex.py:159-180`), confirming it's the real cred store. |
| agy | `~/.gemini/oauth_creds.json` **and** `~/.gemini/antigravity-cli/antigravity-oauth-token` | agy's skill subpath is `.gemini/antigravity-cli` (`agy.py:311-312`). |
| opencode | `~/.local/share/opencode/auth.json` (XDG data) | Absent here (opencode not installed). Canonical opencode auth store; **not** `~/.config/opencode` (that only holds `skills/`). |
| qwen | `~/.qwen/oauth_creds.json` (OAuth) or `~/.qwen/settings.json` / env (API key) | oauth file absent here; user is API-key/env based. |

**Node/npm is a genuine, unchecked prerequisite.** 3 of 5 CLIs are npm-global and resolve under nvm: `claude`, `codex`, `qwen` all live in `~/.config/nvm/versions/node/v22.14.0/bin/`; `node`/`npm` are right beside them. The install hints hard-code `npm install -g ...` (`checks_providers.py:21,27,37`). But `agy` is a standalone binary (`~/.local/bin/agy`, installed via curl script — hint at `:42`) and `opencode` ships its own binary — so node is a prerequisite for claude/codex/qwen only, **not** universally. **Nothing in the repo checks for `node`/`npm`** — `checks_runtime.py` covers Python/git/core/paths but never node. A user who can't run `npm install -g` gets no signal.

## (b) Per-provider offline auth feasibility

Offline credential-file stat is **feasible for every provider** (each has a stable, documented cred file). Cheap offline *subcommands* are weaker/riskier:
- **claude** — stat `~/.claude/.credentials.json`; OR `ANTHROPIC_API_KEY` env set. No safe offline `auth status` subcommand.
- **codex** — stat `~/.codex/auth.json`; OR `OPENAI_API_KEY` env. (`codex login status` exists in recent builds but can touch network — avoid for the offline bar.)
- **opencode** — stat `~/.local/share/opencode/auth.json`. `opencode auth list` reads that file locally and is genuinely offline — the best "own-command" candidate if you prefer a subcommand.
- **qwen** — stat `~/.qwen/oauth_creds.json`; OR API-key in `~/.qwen/settings.json` / env. No clean offline status subcommand.
- **agy** — stat `~/.gemini/oauth_creds.json` and/or `~/.gemini/antigravity-cli/antigravity-oauth-token`. OAuth-only in practice.

**Recommendation:** prefer read-only `stat` of well-known files (truly offline, zero subprocess, uniform across runtimes — consistent with the `rust_core_backend_boundary` / "treat all runtimes uniformly" conventions). Env-var API keys (`ANTHROPIC_API_KEY`, `OPENAI_API_KEY`, etc.) must be treated as a valid alternative auth source to avoid false negatives.

## (c) Proposed diagnostics

**1. `llm.auth` (group `llm`)** — offline credential presence for the selected default provider (extendable to all installed providers).
- **Checks:** for the resolved default provider (reuse `get_default_provider_name()` + the existing `_provider_readiness` in `checks_providers.py`), test `credential_file_exists OR api_key_env_set`.
- **Status:**
  - `OK` — CLI on PATH and a credential file or API-key env var is present.
  - `WARN` (not ERROR) — CLI present but **no** credential evidence found. WARN is correct because (i) env-var API keys and non-standard `*_HOME` overrides can bypass the file, and (ii) a present file may be expired — file-stat can't prove validity without a network call. This mirrors `plugins.github`'s WARN handling.
  - `SKIP` — CLI not installed (the existing `llm.default` ERROR already covers that; don't double-report).
- **details:** `credential path: ~/.codex/auth.json (missing)` / `env OPENAI_API_KEY: unset`.
- **next_steps:** reuse the existing per-provider auth string from `_PROVIDER_SETUP_HINTS[name]["auth"]` (`checks_providers.py:19-45`), e.g. "run `codex login`", "run `opencode auth login`". These strings already exist and are unused for a real check today.
- **data:** replace the static `"auth_status": "not_verified"` with `{"auth_status": "credentials_present"|"no_credentials", "credential_path": ..., "api_key_env": ..., "auth_verified": false}` (keep `auth_verified=false` — presence ≠ validity).
- **Implementation note:** to stay generic (new providers self-describe, matching the registry pattern), add a hookspec method — e.g. `llm_offline_credential_paths() -> list[str]` and `llm_api_key_env_vars() -> list[str]` — to `_hookspec.py` (currently no auth/credential hook exists there). A pragmatic MVP can instead extend the existing `_PROVIDER_SETUP_HINTS` dict with `cred_paths`/`api_key_envs` keys, but the hook approach avoids hard-coding provider knowledge in doctor.

**2. `runtime.node` (group `runtime`, in `checks_runtime.py`)** — presence of `node`/`npm`.
- **Checks:** `shutil.which("node")` / `shutil.which("npm")`.
- **Status:** `OK` if both present; `WARN` if missing **and** at least one npm-based provider (claude/codex/qwen) is registered but its CLI isn't found — i.e. only nag when it would actually help. Otherwise `SKIP`.
- **next_steps:** "Install Node.js (which provides npm) before running `npm install -g @anthropic-ai/claude-code` (or the codex/qwen equivalents)."
- Gate it on the same npm-based provider set so opencode/agy-only users aren't warned.

## (d) Severity

**Unauthenticated-but-installed is a hard blocker for `sase run`.** Every `invoke_agent()` call routes through the provider subprocess (`_invoke.py:237`), and an unauthenticated CLI makes *all* agent invocations fail with `LLMInvocationError` (`_invoke.py:282-305`), surfacing only inside a failed run's artifacts. So the *runtime* impact is fatal.

**But the doctor check itself should be WARN, not ERROR**, because file-stat evidence is necessary-not-sufficient: env-var API keys, custom `CODEX_HOME`/`*_PATH` overrides, and expired-but-present tokens all create ambiguity a read-only offline probe cannot resolve. WARN with a precise next-step ("run `codex login`") converts today's silent, deep, late failure into an early, actionable signal — which is the whole point of the requested diagnostic — without risking false ERRORs that block correctly-configured env-key users.

**No existing auth/credential detection logic is reusable** beyond: the `gh auth status` pattern in `checks_plugins.py:138-196` (structural template), the unused per-provider `auth` hint strings in `_PROVIDER_SETUP_HINTS` (`checks_providers.py:19-45`), and the `~/.claude`/`~/.codex` path constants already referenced in `session_resolver.py:87` and `codex.py:134` (for the real cred dirs, not for auth checking).

Let me retry the size measurement (the previous output came back empty).

Agent 1 (provider auth) is in — a strong, evidence-backed result. Waiting on the remaining four (tmux/terminal, notifications, skills/tooling, system resources).

The monitor's completion detection isn't matching the transcript format — but I'm receiving reliable per-agent completion notifications directly. Let me stop the noisy monitor and rely on those.

Monitor stopped. Now relying on direct per-agent completion notifications. Agent 1 (provider auth) is complete; awaiting the other four.

I have all the evidence needed. Here is my report.

---

# `sase doctor` — Optional Integration Diagnostics: Findings & Proposals

## TL;DR
- **Telegram is already fully covered** by `sase doctor` (via the `axe.chops` check). No new work needed there beyond awareness.
- **Mobile gateway / push (FCM) is the real gap**: no doctor check exists; a misconfigured `push_provider: fcm` is passed through with zero Python-side validation, and the gateway binary is never pre-flighted.
- **MCP does not exist in this repo** — no Python or config references at all. Nothing to diagnose.
- Notifications are a single local JSONL inbox; there are no in-process per-channel credentials to validate. External delivery is delegated to (a) the Rust mobile gateway and (b) axe Telegram chops.

---

## 1. Notifications subsystem — how delivery works (and where it's silent)

SASE notifications are **not** a multi-channel push system in Python. `notify_*` senders (`src/sase/notifications/senders.py`) all just build a `Notification` and call `append_notification`, which writes a JSONL line through the Rust store:

- `src/sase/notifications/store.py:113-123` — `append_notification` writes via Rust, then `register_notification`, then invalidates cache.
- **Silent-swallow point**: `src/sase/notifications/store.py:117-122` — pending-action registration failure is caught and only `log.warning(...)`; the notification still "succeeds."
- Every sender unconditionally increments `NOTIFICATIONS_SENT.labels(..., status="ok")` (e.g. `senders.py:35, 73, 93`), so the metric can never reflect a delivery failure — it's an "enqueued" counter, not a "delivered" one.

There is **no per-channel credential config in host Python**. External surfacing happens two ways, and only these two can silently no-op:
1. **Mobile push** — the Rust `sase_gateway` bridges the inbox to FCM (section 3).
2. **Telegram** — axe "outbound" chop scripts read the inbox (section 2).

So "notification channel enabled but misconfigured = silent no-op" reduces to the **mobile gateway** and **Telegram** integrations below.

## 2. Telegram — ALREADY covered by `sase doctor`

`sase-telegram` is **not pip-installed** in this env (`ModuleNotFoundError: No module named 'sase_telegram'`), so the plugin ships as axe chop scripts + env config. The host repo already diagnoses this:

- `src/sase/axe/chop_doctor.py:169-239` — `_telegram_checks` runs whenever Telegram chop scripts are installed/configured (`_has_telegram_chop_scripts`, name match `tg_inbound`/`tg_outbound`/`telegram*`, line 259-260).
- Required config it validates:
  - Env vars `SASE_TELEGRAM_BOT_CHAT_ID`, `SASE_TELEGRAM_BOT_USERNAME` (`chop_doctor.py:27`) → `telegram_env` check, WARN if missing (`:181-192`).
  - Bot token from `SASE_TELEGRAM_BOT_TOKEN` env, `~/.sase/telegram_bot_token` (mode-600 enforced, `:289-310`), or `pass` (`:271-286`) → `telegram_bot_token` check.
  - **Outage escalation**: if `~/.sase/telegram_is_enabled` exists AND telegram chops are configured but no token source resolves, status escalates **WARN → ERROR** (`:206-228`, `_telegram_is_enabled` at `:313-317`).
- **Wired into top-level doctor**: `src/sase/doctor/checks_axe.py:35-87` (`axe.chops`) calls `build_chop_checks` (which includes `_telegram_checks`) and is registered in `src/sase/doctor/runner.py:74`.

**Manifestation of a missing token**: with Telegram enabled + configured → ERROR in `sase doctor`; otherwise WARN. This is the model to copy for the gateway. **Gap**: the check only fires if Telegram *chop scripts* are present; if a user set `telegram_is_enabled` and env vars but the chop scripts aren't installed, `_has_telegram_chop_scripts` returns False and the whole check is skipped (`chop_doctor.py:174-175`) — a minor blind spot worth noting.

## 3. Mobile gateway + FCM push — the primary GAP (no doctor check)

`src/sase/integrations/mobile_gateway.py`. Config section `mobile_gateway` (default_config.yml:20-33), fields on `_MobileGatewayConfig` (`:31-47`): `push_provider` (default `"disabled"`, choices `disabled|test|fcm`), `fcm_project_id`, `fcm_service_account_json`, `fcm_credential_env`, `fcm_dry_run`, `command`.

**What needs the binary**: `sase mobile gateway start` (`:211-218`, foreground command; parser `src/sase/main/parser_mobile.py:82-157`). Binary resolution: `shutil.which("sase_gateway")` then sibling `../sase-core/target/{debug,release}/sase_gateway` (`:273-286`).

**How misconfig manifests:**
- **Missing binary** → loud `_MobileGatewayError` "mobile gateway binary not found…" (`:134-140`), printed to stderr + exit 1 (`:215-217`). **But only when the user runs `start`** — there is *no daemon/auto-start* (confirmed: no other invocation of the gateway exists), and *no pre-flight doctor signal*. Push/mobile silently does nothing until someone notices the gateway isn't running.
- **`push_provider: fcm` with empty `fcm_project_id`/credentials** → **zero Python-side validation**. `_prepare_mobile_gateway_launch` (`:114-168`) simply *omits* empty flags: it appends `--push-provider fcm` (`:155-156`) but skips `--fcm-project-id` / `--fcm-service-account-json` / `--fcm-credential-env` when blank (`:157-162`). Coherence is fully delegated to the Rust gateway at runtime — so a user who selects FCM but forgets credentials gets **no doctor-time signal**; push silently fails to deliver (behavior determined inside `sase_gateway`, in the `../sase-core` linked repo, not inspectable here).
- `sase_gateway` is **not** in the doctor optional-tools list (`src/sase/doctor/checks_tools.py:25-43`), so even deep mode never mentions it.

## 4. MCP servers — not applicable

No MCP anywhere: `grep -rin -w mcp src/sase` (Python, yml, yaml, md, toml) returns **nothing**. Agents in this repo are not configured with MCP servers. **No diagnostic needed**; recommend explicitly noting "MCP not implemented" so future readers don't re-chase this.

## 5. Other config-gated integrations
- **Telemetry pushgateway** (distinct from mobile push) is already checked, including reachability, and correctly SKIPs when disabled: `src/sase/doctor/checks_telemetry.py:37-72` — a good status-semantics model.
- **axe lumberjack chops** already get configured/unconfigured/missing checks (`chop_doctor.py:125-166`).

---

## Proposed new doctor diagnostics

Framework recap: `CheckSpec(id, group, title, runner, deep)` → `DiagnosticCheck(id, group, status, title, summary, details, next_steps, data)`; `CheckStatus = Literal["OK","WARN","ERROR","SKIP"]` (`src/sase/diagnostics/models.py:13`). Add a new `checks_integrations.py` (suggest new group `"integrations"`, or reuse `"ops"`) and register it in `runner.py:build_doctor_registry`. All read-only: read merged config + `shutil.which` + file `stat`; no network, no gateway launch.

### D1 — `integrations.mobile_gateway_binary`
- **Checks (read-only)**: replicate `_resolve_gateway_command()` logic (config `mobile_gateway.command`, then `shutil.which("sase_gateway")`, then sibling `../sase-core/target/{debug,release}`).
- **Status**: `SKIP` if `push_provider == "disabled"` **and** no `command` override set (integration unused). `OK` if resolvable. `WARN` if push/gateway is configured-for-use but binary unresolvable (mobile push will silently not deliver).
- **next_steps**: "Build sase_gateway in ../sase-core or set `mobile_gateway.command` in sase.yml; run `sase mobile gateway start` to serve mobile clients."

### D2 — `integrations.mobile_push_config`
- **Checks (read-only)**: coherence of the `mobile_gateway` push config from `load_merged_config()`.
- **Status**:
  - `SKIP` when `push_provider == "disabled"` (default → intentionally off).
  - `OK` when `push_provider == "test"`, or `fcm_dry_run: true`, or (`push_provider == "fcm"` and `fcm_project_id` non-empty and (`fcm_service_account_json` exists as a file **or** `fcm_credential_env` names a set env var)).
  - `WARN`→ escalate to **`ERROR`** when `push_provider == "fcm"` but `fcm_project_id` is empty, or neither credential source resolves (`fcm_service_account_json` path missing / `fcm_credential_env` unset). This is the exact "enabled + misconfigured = silent no-op" case.
- **details**: which field is missing (`fcm_project_id empty`, `fcm_service_account_json <path> does not exist`, `fcm_credential_env <VAR> is unset`). Redaction already handles token-looking values (`models.py:186-199`), but pass only booleans/paths, never token contents.
- **next_steps**: "Set `mobile_gateway.fcm_project_id` and one of `fcm_service_account_json` / `fcm_credential_env`, or set `fcm_dry_run: true` for local testing, or `push_provider: disabled` to turn push off."

### D3 (optional) — `integrations.telegram_enabled_no_chops`
- Close the section-2 blind spot: if `~/.sase/telegram_is_enabled` exists but `_has_telegram_chop_scripts` is False, emit `WARN` ("Telegram marked enabled but no inbound/outbound chop scripts are installed/configured; messages will not be delivered"). Reuse helpers already in `chop_doctor.py:242-317`.

## Severity / impact

| Integration | Current doctor coverage | Silent-failure risk | Proposed | Severity |
|---|---|---|---|---|
| Telegram | **Covered** (`axe.chops`), ERROR on outage | Low (except D3 blind spot) | D3 (WARN) | Low |
| Mobile push (FCM) | **None** | **High** — `push_provider: fcm` + missing creds = no Python validation, delivery silently fails | D2 (ERROR) | **High** |
| Mobile gateway binary | **None** (not in optional tools) | Medium — no pre-flight; mobile bridge dead until start is run manually | D1 (WARN) | Medium |
| MCP | N/A | None (feature absent) | none | — |

**Key files**: `src/sase/integrations/mobile_gateway.py` (:31-47 config, :114-168 flag-omission, :134-140 binary error, :273-286 resolution), `src/sase/axe/chop_doctor.py:169-317` (Telegram model to copy), `src/sase/doctor/checks_axe.py` + `runner.py:53-83` (registration pattern), `src/sase/doctor/checks_telemetry.py:37-72` (SKIP-when-disabled model), `src/sase/doctor/checks_tools.py:25-43` (binary-presence model), `src/sase/diagnostics/models.py:13,36-65` (status/check contract), `src/sase/notifications/store.py:113-123` and `senders.py` (why in-process delivery gives no failure signal).

No files were modified.

Agent 3 (notifications/integrations) is in — mobile-push/FCM is the clear gap there, Telegram already covered, MCP not present. Three agents remain (tmux/terminal, skills/tooling, system resources).

I now have all the evidence needed. Here is my report.

---

# `sase doctor` — New Diagnostic Opportunities for Silently-Degrading Features

## Summary of how `sase doctor` is wired

- Default registry: `src/sase/doctor/runner.py:53-83`. Groups run by default; `deep=True` specs run only under `sase doctor --deep`.
- `config.init` (`src/sase/doctor/checks_config.py:30-35`) is a **default** (non-deep) check. It runs *every* registered init planner (`src/sase/doctor/checks_config_init.py:37-61`), and the init registry (`src/sase/main/init_registry.py:32-51`) includes **memory, sdd, and skills**. So `plan_init_skills` already runs inside doctor.
- `tools.optional` (`src/sase/doctor/checks_tools.py:46-57`) is **deep-only** and already lists `prettier` (`checks_tools.py:38-42`). It does **not** list `fzf`, `clipboard`, or the xprompt LSP.

---

## 1. Skills deployment — MOSTLY covered, with one real chezmoi gap

**How deploy targets are computed:** `src/sase/main/init_skills_handler.py:156-181`. Non-chezmoi → `~/<subpath>/skills/<name>/SKILL.md`; chezmoi → `CHEZMOI_HOME/dot_<subpath>/skills/<name>/SKILL.md` (the chezmoi *source* repo, not `~`).

**Drift/missing detection already exists** in two places:
- `_planned_skill_operation` (`init_skills_handler.py:416-431`) returns `create` (missing) / `overwrite` (stale) / `None` (current) by comparing rendered content to the on-disk file.
- `plan_init_skills` (`init_skills_handler.py:519-563`) turns those into `InitAction`s. Because `config.init` runs this planner with `provider=None` (`checks_config_init.py:19-30`), **skill drift and never-installed skills for ALL providers are already surfaced** by the default `config.init` check as "planned init action(s)".
- There is also a read-only `SkillsInventory` with explicit `current`/`stale`/`missing` status (`src/sase/skills/inventory.py:101-187`) exposed via `sase skill list` (`src/sase/skills/cli_list.py`). So a dedicated status model already exists — it is simply not consumed by `sase doctor`.

**Genuine gap (chezmoi-apply blind spot):** In chezmoi mode the targets point at `CHEZMOI_HOME` (`init_skills_handler.py:161-163`). `config.init` therefore compares against the chezmoi *source*. If the source is current but `chezmoi apply` was never run, the actual `~/.claude/skills/...` files are missing/stale, yet doctor reports "current". Nothing in doctor checks the applied `~` location in chezmoi mode.

**Severity:** Low–Medium. Base drift is covered; the chezmoi-apply gap is a genuine (if narrow) hole, and there is no doctor-native, provider-scoped skills summary.

---

## 2. prettier — covered (deep), but impact is understated and interacts badly with `config.init`

**Where it degrades:** `format_with_prettier` (`src/sase/file_references.py:467-511`) is a graceful no-op when prettier is absent (`file_references.py:483`). Callers are broad: generated skills (`init_skills_handler.py:266-285`), **agent prompt preprocessing wrap** (`src/sase/llm_provider/preprocessing.py:171`, using `AGENT_PROMPT_WRAP_WIDTH`), commit precommit plan formatting (`src/sase/workflows/commit/precommit_hooks.py:202-207`), plus plans, SDD, notifications, reword, memory notes.

**Understated in two concrete ways:**
1. `tools.optional` describes prettier only as "prompt and generated Markdown formatting" and is **deep-only** — a normal `sase doctor` run never mentions it.
2. **False-drift interaction:** when prettier is missing, `plan_init_skills` renders targets with `use_prettier=False` (`init_skills_handler.py:534, 600`), but previously-deployed skills on disk were prettier-formatted. `_planned_skill_operation` then reports `overwrite` for **potentially every skill**. So a missing prettier makes doctor's own `config.init` skill-drift signal noisy/unreliable, on top of the formatting degradation. `plan_init_skills` does emit `_PRETTIER_WARNING` in this case (`init_skills_handler.py:556`), which `config.init` surfaces as a WARN, but it does not explain the spurious overwrite actions.

**Severity:** Medium. Not a hard break, but silently changes prompt wrapping fed to agents and pollutes drift detection.

---

## 3. fzf — genuine gap (not in `sase doctor`)

**What breaks without fzf:**
- `sase prompt run --pick` interactive picker returns `None` and prints a fallback message (`src/sase/prompt/cli_run.py:127-133`).
- Editor-driven prompt-history selection hard-fails: "Error: fzf is not installed. Please install fzf to use prompt history." (`src/sase/main/query_handler/_editor.py:150-156`).

**Current coverage:** fzf status is computed **only** for the separate `sase prompt doctor` command (`src/sase/history/prompt_maintenance.py:213`, rendered at `src/sase/prompt/cli_maintenance.py:283`). It is **not** in `sase doctor` and **not** in `tools.optional` (confirmed — `checks_tools.py:25-43` has no fzf entry).

**Severity:** Medium. Fully disables the interactive prompt pickers; discoverable only if the user already knows to run `sase prompt doctor`.

---

## 4. clipboard — genuine gap (not in `sase doctor`)

**Selection logic:** `src/sase/core/clipboard.py:11-54` (`pbcopy` on macOS; `wl-copy`/`xclip`/`xsel` on Linux). `clipboard_available()` at `clipboard.py:52-54`.

**What breaks without any clipboard tool:** ~40 call sites of `copy_to_system_clipboard` across the ACE TUI (vim yank, copy-mode, artifact/plan/changespec/axe/notification copy) plus `sase prompt copy` (`src/sase/prompt/cli_copy.py:28-38`, exits nonzero with a fallback). Many TUI callers check the boolean and toast a failure, but some yank paths ignore the return and **fail silently** (e.g. `src/sase/ace/tui/widgets/_vim_visual_ops.py:20`, `src/sase/ace/tui/widgets/_vim_normal_operator_exec.py:60-164`).

**Current coverage:** Same as fzf — computed only for `sase prompt doctor` (`prompt_maintenance.py:214`, rendered `cli_maintenance.py:284-287`). No `clipboard` reference anywhere in `src/sase/doctor/` (confirmed by grep).

**Severity:** Medium. Silent failures in TUI yank are especially user-hostile.

---

## 5. xprompt LSP / editor integration — genuine gap (not checked anywhere in doctor)

**What it is:** `sase lsp` (`src/sase/main/parser_commands.py:174-192`) execs the Rust `sase-xprompt-lsp` binary that powers editor completion/diagnostics for xprompt tokens (`#` xprompts, `+` project/PR refs, `%model`) — the sase-nvim integration.

**Resolution order & failure** (`src/sase/integrations/xprompt_lsp.py:68-125`): env override `SASE_XPROMPT_LSP_CMD` → venv binary → PATH `sase-xprompt-lsp` → prebuilt `../sase-core/target/{debug,release}` → `cargo run` against `../sase-core/Cargo.toml`. If none resolve, it raises and `sase lsp` exits 1 (`xprompt_lsp.py:122-125`, `handle_xprompt_lsp_command` at `xprompt_lsp.py:35-48`). So without the binary AND without cargo+sibling core, editor xprompt intelligence is dead.

**Current coverage:** None. No doctor check references the LSP binary or cargo (grep of `src/sase/doctor/` for `xprompt_lsp|sase-xprompt-lsp|cargo` is empty).

**Severity:** Low–Medium. Editor-only; degrades sase-nvim UX but not core CLI/TUI flows.

---

## Which gaps are genuinely NOT already covered

| Area | Covered today? | Genuine gap |
|---|---|---|
| Skill drift / never-installed (any provider) | Yes — `config.init` via `plan_init_skills`; also `sase skill list` | Only the **chezmoi source-vs-applied** blind spot + no doctor-native skills summary |
| prettier | Yes — `tools.optional` (**deep-only**) + `config.init` warning | Understated impact (prompt-wrap, precommit) + **false skill-drift** when missing |
| fzf | **No** in `sase doctor` (only `sase prompt doctor`) | **Yes** |
| clipboard | **No** in `sase doctor` (only `sase prompt doctor`) | **Yes** |
| xprompt LSP | **No** anywhere in doctor | **Yes** |

---

## Proposed new doctor diagnostics (read-only)

All fit the existing `DiagnosticCheck(id, group, status ∈ OK/WARN/ERROR, title, summary, details, next_steps, data)` model.

1. **`tools.fzf`** (group `tools`, deep) — check `shutil.which("fzf")`. WARN if missing. `summary`: "fzf missing — interactive prompt pickers disabled". `next_steps`: "Install fzf to use `sase prompt run --pick` and editor prompt history."

2. **`tools.clipboard`** (group `tools`, deep) — reuse `clipboard.clipboard_available()` (platform-aware). WARN if no clipboard command resolves. `summary`: "no system clipboard command — copy actions will fail". `next_steps` (Linux): "Install wl-copy (Wayland) or xclip/xsel (X11)."; (macOS) note pbcopy expected. Prefer reusing `clipboard_available()` over re-listing commands so it stays platform-correct.

   - Note: adding fzf + clipboard to the `_OPTIONAL_TOOLS` tuple in `checks_tools.py:25-43` is the lowest-effort implementation (they already fit the `_ToolRequirement`/any-of shape), rather than net-new check modules.

3. **`tools.xprompt_lsp`** (group `tools`, deep) — read-only mirror of `_resolve_xprompt_lsp_command`'s discovery (venv bin / PATH `sase-xprompt-lsp` / `../sase-core/target` / cargo+manifest). Status OK if a binary resolves; WARN if only the cargo-build fallback is available (slow first run); WARN/INFO if nothing resolves. `summary`: "xprompt LSP binary not found — editor xprompt completion/diagnostics unavailable". `next_steps`: install `sase-xprompt-lsp`, or build sase-core, or set `SASE_XPROMPT_LSP_CMD`.

4. **`config.skills`** (group `config`, default) — consume the existing `build_skills_inventory()` (`src/sase/skills/inventory.py:101`) for a doctor-native, per-provider summary: `current/stale/missing` counts and `deploy_mode`. Status OK if all current; WARN on any stale/missing. This is largely redundant with `config.init` for non-chezmoi, but adds value by (a) reporting provider-scoped status explicitly and (b) exposing `prettier_available` so the **false-drift** case is labeled ("stale counts may be inflated: prettier missing"). `next_steps`: "Run `sase skill init` (or `sase skill list` for detail)."

5. **`config.skills.applied`** (group `config`, deep, chezmoi-only) — closes the chezmoi-apply blind spot: when `get_use_chezmoi()` is true, also stat the real `~/<subpath>/skills/<name>/SKILL.md` targets (non-chezmoi path form) and WARN if the chezmoi source is current but `~` copies are missing/older. `next_steps`: "Run `chezmoi apply`." (This is the only skill gap not already covered by `config.init`.)

6. **Enrich `prettier` detail in `tools.optional`** (`checks_tools.py:38-42`) — broaden the feature string beyond "prompt and generated Markdown formatting" to note agent-prompt wrap width (`preprocessing.py:171`) and the spurious `config.init` skill-overwrite noise, so the deep report explains the real blast radius.

---

### Key file references
- `src/sase/doctor/runner.py:53-83` (registry), `src/sase/doctor/checks_config.py:30-35` + `src/sase/doctor/checks_config_init.py:17-94` (init planners run in doctor), `src/sase/main/init_registry.py:32-51` (skills is a registered planner).
- `src/sase/doctor/checks_tools.py:25-57` (optional tools; deep; prettier present, fzf/clipboard/LSP absent).
- `src/sase/main/init_skills_handler.py:156-181, 416-431, 519-563` (deploy paths, drift op, planner + prettier warning).
- `src/sase/skills/inventory.py:101-187` + `src/sase/skills/cli_list.py` (existing current/stale/missing model).
- `src/sase/file_references.py:467-511`, `src/sase/llm_provider/preprocessing.py:171`, `src/sase/workflows/commit/precommit_hooks.py:202-207` (prettier blast radius).
- `src/sase/prompt/cli_run.py:127-133`, `src/sase/main/query_handler/_editor.py:150-156` (fzf-dependent features).
- `src/sase/core/clipboard.py:11-54`, `src/sase/prompt/cli_copy.py:28-38`, `src/sase/ace/tui/widgets/_vim_visual_ops.py:20` (clipboard).
- `src/sase/integrations/xprompt_lsp.py:68-125`, `src/sase/main/parser_commands.py:174-192` (xprompt LSP).
- `src/sase/history/prompt_maintenance.py:213-214`, `src/sase/prompt/cli_maintenance.py:283-287` (fzf+clipboard currently reported only by the separate `sase prompt doctor`).

No files were modified.

Let me confirm whether the doctor already checks chezmoi anywhere and the `use_chezmoi` default.

Agent 4 (skills/tooling) is in — fzf, clipboard, and xprompt-LSP are genuine uncovered gaps; prettier's impact is understated and even corrupts the existing skill-drift signal. Two agents remain (tmux/terminal, system resources).

I have gathered comprehensive evidence. Here is my report.

---

# `sase doctor` — tmux & terminal-capability diagnostics research

## 1. The real role of tmux

**Launching / running agents does NOT require tmux.** Agents are spawned as plain child processes via `subprocess.Popen` in `src/sase/axe/_process_start.py:99` (and the orchestrator at `src/sase/axe/orchestrator.py:83`). No tmux is involved in agent execution. This is the single most important finding: tmux is a UX/navigation enabler, not an agent-runtime dependency.

Where tmux actually matters, by path:

- **`sase ace --tmux` scripting launcher — HARD FAILURE.** `src/sase/main/ace_handler.py:100-102` routes to `launch_ace_in_tmux`. `src/sase/main/ace_tmux.py:49-51` (`_require_tmux_binary`) raises, and `ace_tmux.py:42-44` prints to stderr and `sys.exit(2)` if tmux is absent. This is the path scripting agents use to spawn a TUI window they can drive via `send-keys`/`capture-pane`. It respects `$TMUX` (reuses current session) vs. creating the dedicated `sase_ace_agents` session (`ace_tmux.py:54-98`).

- **`t` open-workspace-window keymap — graceful.** `src/sase/ace/tui/actions/agents/_panel_tmux.py:214-245` (`_open_tmux_window_for_directory`) runs `tmux list-windows` / `new-window` with `check=False` and catches `FileNotFoundError` to notify `"tmux command not found"` (error severity, line 243-244). This opens a shell in the agent's workspace dir — it is NOT "attaching to the agent process" (agents run headless; output goes to logs). Non-fatal.

- **Inline artifact side-pane — requires running *inside* tmux, else graceful full-screen fallback.** `src/sase/ace/tui/actions/agents/_panel_artifacts.py:415-441` and `461-487` branch on `is_tmux_session()`. Inside tmux → `view_artifact_files_in_tmux_pane` opens a right-side split (`src/sase/ace/tui/graphics/_viewer_tmux.py:61-139`). Outside tmux → it suspends the TUI and shows the viewer full-screen via `suspend_for_external_tool`. **Zoom is tmux-only** (`_panel_artifacts.py:435-438`: "Zoom open is only available inside tmux").
  - `is_tmux_session()` = `$TMUX or $TMUX_PANE` (`src/sase/ace/tui/graphics/_viewer_tmux_common.py:19-22`) — i.e. it keys on being *inside* tmux, not on the binary existing.
  - `_viewer_tmux.py:72-78` emits `not_in_tmux` warning; `_viewer_tmux.py:79-85` emits `missing_tmux` if the binary is gone.

- **ChangeSpec workspace checkout-open — silent no-op.** `src/sase/ace/tui/actions/workspace.py:100-120` runs tmux with `check=False`; missing tmux silently does nothing.

**Verdict on centrality:** tmux is a hard requirement only for the `--tmux` scripting launcher (used to spawn agent-driven TUIs). For interactive use it is a significant UX enhancer (workspace windows, inline artifact panes, zoom) that degrades gracefully. The current "optional deep tool" framing understates this.

## 2. Minimum tmux version requirement

**None exists anywhere in the repo.** Grep for `tmux -V`, `tmux_version`, version parsing, `#{version}` returned nothing. There is no version gating.

Note (evidence-based caveat, not in code): rendering images inside tmux via `kitten icat` (kitty graphics protocol) in practice requires tmux ≥ 3.3 with `allow-passthrough on`. The code neither checks the version nor sets `allow-passthrough` — so inline image/markdown/pdf artifacts inside an old/misconfigured tmux will fail at runtime as a `kitten_failed` warning (`src/sase/ace/tui/graphics/_viewer_launch.py:204-206`). This is a genuine silent-degradation gap worth a diagnostic.

## 3. Terminal capabilities

- **Truecolor (24-bit).** `src/sase/ace/tui/graphics/capability.py:18-23` (`has_truecolor`): true when `COLORTERM ∈ {truecolor, 24bit}` or `truecolor` in `TERM`. Consumed only by the Pillow-backed inline image previews — `renderable.py:62-76`, `cell.py:_rich_color` (`graphics/cell.py:299-301`), and callers `file_panel/_display.py:468` and `notification_modal_attachments.py:101`. **Silent degradation:** without truecolor, inline image previews fall back to a 256-color/standard approximation (`cell.py`), looking noticeably worse. The rest of the Textual TUI is unaffected (Textual does its own color handling).

- **kitty graphics protocol (`kitten`).** `src/sase/ace/tui/graphics/_viewer_render.py:139-144` — `kitten` is required for `image`, `markdown`, and `pdf` artifact modes; `_viewer_loop_terminal.py:120-125` builds the `kitten icat` command. Without `kitten`, those artifact modes hard-skip with a `missing_kitten` warning (graceful, no crash). Also requires a terminal that actually implements the protocol (kitty/WezTerm/Ghostty/etc.); an unsupported terminal yields a runtime `kitten_failed` warning. Already listed as optional tool `kitten` (`checks_tools.py:28`).

- **Other artifact deps** (`_viewer_render.py:147-179`): `mpv` (video), `pdftoppm` (pdf/markdown paging), `pandoc` + a PDF engine (markdown→pdf). All already in `_OPTIONAL_TOOLS` (`checks_tools.py:29-42`); all degrade to warnings.

- **Clipboard.** `src/sase/core/clipboard.py:11-54`: platform-aware — `pbcopy` (macOS); `wl-copy` (Wayland via `$WAYLAND_DISPLAY`), `xclip`/`xsel` (X11 via `$DISPLAY`) on Linux. `clipboard_available()` (line 52) already exists. **Silent degradation:** with no backend, `copy_to_system_clipboard` returns `False`. ~40 call sites copy to clipboard; some notify `"Failed to copy to clipboard"` (e.g. `actions/clipboard/_changespec.py:35-36`) but vim-style yanks silently no-op (`widgets/_vim_visual_ops.py:20`, `_vim_normal_operator_exec.py:60-67`). **Precedent:** `sase prompt maintenance` already surfaces `clipboard_available` (`src/sase/prompt/cli_maintenance.py:239,286`) — doctor has none.

## 4. Environment assumptions

- **Inside vs. outside tmux (`$TMUX`/`$TMUX_PANE`).** `is_tmux_session()` (`_viewer_tmux_common.py:19-22`) gates the inline artifact side-pane and zoom. `ace_tmux.py:54-69` behaves differently inside tmux (reuses session) vs. outside (creates `sase_ace_agents`). So "installed" is not sufficient — the TUI must be *run inside* tmux for the premium artifact UX.
- **SSH sessions.** No `SSH_CONNECTION`/`SSH_TTY`/`SSH_CLIENT` handling anywhere (grep empty). Over SSH, clipboard tools and kitty graphics frequently fail — a relevant blind spot but not something the code adapts to.
- No `COLORTERM`/`TERM` is forced for the TUI; `TERM=dumb` is only used to disable color in non-TUI Rich output (`main/parser.py:234`) and for agent subprocess env (`llm_provider/agy.py:550`).

## 5. Verdict: promote tmux out of "optional deep tool"?

**Yes — partially.** tmux should be promoted to a **default-mode check with WARN severity (not ERROR)**, because:
- It is a **hard requirement** for the `sase ace --tmux` agent-scripting launcher (`ace_tmux.py:50-51`, `sys.exit(2)`).
- It enables first-class interactive features (`t` workspace windows, inline artifact side-panes, zoom).
- But the core TUI and all agent execution work without it (agents = `subprocess.Popen`, artifact viewing degrades to full-screen), so ERROR would be wrong.

It should NOT stay buried behind `--deep` (only `--deep` runs `tools.optional`, per `runner.py:95` / `registry.py:56-60`), since a first-run user with no tmux gets zero signal in the default `sase doctor` run.

## 6. Proposed new diagnostics

Framework note: statuses are `OK|WARN|ERROR|SKIP` (`src/sase/diagnostics/models.py:13`); there is no INFO. `CheckSpec(deep=False)` runs by default; `deep=True` runs only under `--deep` (`registry.py:23,56-60`).

| id | group | deep? | checks | status semantics | next_steps | severity |
|---|---|---|---|---|---|---|
| `tools.tmux` | `tools` | **no (promote to default)** | `shutil.which("tmux")` | OK if present; **WARN** if absent | "Install tmux (`apt install tmux` / `brew install tmux`) to enable `sase ace --tmux`, agent workspace windows (`t`), and inline artifact panes." | **Medium** — hard-blocks the `--tmux` launcher; degrades interactive UX; core TUI + agents unaffected |
| `tools.tmux_version` | `tools` | yes | parse `tmux -V`, compare to **3.3** | OK ≥3.3; WARN <3.3 or unparseable | "Upgrade tmux to ≥3.3 and set `set -g allow-passthrough on` so inline image/PDF artifacts render via the kitty graphics protocol inside tmux." | **Low** — only affects in-tmux image artifacts; fills the "no version gate exists" gap |
| `env.tmux_session` | `env` | yes | `$TMUX or $TMUX_PANE` | OK if inside tmux; **SKIP** (with note) otherwise | "Run the ACE TUI inside tmux to get inline artifact side-panes and zoom; outside tmux the viewer opens full-screen." | **Low** — informational; explains graceful degradation |
| `terminal.truecolor` | `terminal` | yes | reuse `has_truecolor()` (`capability.py:18`) | OK if advertised; WARN otherwise | "Use a truecolor terminal or export `COLORTERM=truecolor` for accurate inline image previews." | **Low** — only inline Pillow image previews degrade to 256-color |
| `tools.clipboard` | `tools` | **no (default)** | reuse `clipboard_available()` (`clipboard.py:52`) | OK if a backend on PATH; **WARN** otherwise | Linux/X11: "install `xclip` or `xsel`"; Wayland: "install `wl-clipboard`"; macOS uses `pbcopy`. | **Medium** — many copy keymaps silently no-op (e.g. vim yank) with no user feedback |
| `terminal.kitty_graphics` | `terminal` | yes | `shutil.which("kitten")` + heuristic `TERM`/`TERM_PROGRAM` for a protocol-capable terminal (kitty/WezTerm/Ghostty) | OK if kitten present and terminal likely supports protocol; WARN if kitten present but terminal unknown; SKIP/WARN if kitten missing | "Install the `kitten` binary and use a kitty-graphics-capable terminal to preview image/PDF/Markdown artifacts inline." | **Medium** — gates all image/markdown/pdf artifact rendering (`_viewer_render.py:139`); today only a deep `tools.optional` line item |

Additional recommendation: keep the existing `tools.optional` deep group for `bat/mpv/pdftoppm/pandoc/pdf_engine/prettier`, but **split `tmux`, `kitten`, and clipboard out** into the promoted/dedicated checks above so their central role is visible in the default run rather than hidden behind `--deep`.

### Key files
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/doctor/checks_tools.py` (current optional-tool list; where `tmux` at line 26 would be promoted out)
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/main/ace_tmux.py` (hard `sys.exit(2)` on missing tmux, lines 42-51)
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/actions/agents/_panel_tmux.py` (`t` keymap, lines 214-245)
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/graphics/_viewer_tmux.py` (`not_in_tmux`/`missing_tmux` warnings, lines 72-85)
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/graphics/_viewer_tmux_common.py` (`is_tmux_session`, lines 19-22)
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/graphics/_viewer_render.py` (kitten/mpv/pdftoppm/pandoc gating, lines 133-180)
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/ace/tui/graphics/capability.py` (truecolor detection, lines 18-34)
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/core/clipboard.py` (clipboard backends + `clipboard_available`, lines 11-54)
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/axe/_process_start.py` (agents spawned via `Popen`, line 99 — proves tmux is not an agent-runtime dep)
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/doctor/checks_runtime.py` (pattern to copy for new default checks: status/summary/next_steps/data shape)
- `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_14/src/sase/diagnostics/models.py` and `registry.py` (`CheckStatus`, `CheckSpec.deep` gating)

No files were modified.

Agent 2 (tmux/terminal) is in — agents run via `subprocess.Popen` (not tmux), so tmux is a hard requirement only for `sase ace --tmux` and a UX enhancer otherwise; it, clipboard, and `kitten` should be promoted out of deep-only. One agent remains (system resources).

I have enough to write the report. Let me verify the `DiagnosticCheck`/`CheckStatus` model quickly to ground the proposed status semantics.

# `sase doctor` — New System-Prerequisite Diagnostics: Research Findings

## How the system works today (evidence)

**Ephemeral workspaces are real, full `git clone`s.** `ensure_workspace_checkout()` resolves a target dir and calls `_ensure_git_clone_at()`, which runs `git clone <primary> <target>` for any `workspace_num > 1`:
- `src/sase/workspace_provider/utils.py:252-265` — the actual `git clone`.
- `src/sase/workspace_provider/utils.py:266-280` — on failure it raises `RuntimeError(f"git clone failed (exit code …): {stderr}")`. **A full disk during clone surfaces here as a hard agent-launch failure**, not a graceful degrade.
- Entry point `ensure_workspace_checkout()` at `utils.py:304-339`; root resolution in `store.py:210-247` (`xdg-state` default → `~/.local/state/sase/workspaces/<project_key>`), default state root at `store.py:177-201`.
- Default retention `cleanup_ttl_days = 14` (`store.py:282`) — stale workspaces accumulate for two weeks.

**Measured cost per workspace (this machine, sase_14):** total `1.4G`; `.git` `512M`; working-tree-plus-untracked (excl `.git`) `892M`; `.venv` `390M`; 8753 tracked files. A local clone hardlinks `.git/objects` on the same filesystem, so the *incremental* cost of a fresh clone is roughly the checked-out tracked tree, but each workspace then grows a real `~390M` `.venv` after `just install`, plus divergent objects. Realistically **hundreds of MB to ~1GB+ per live workspace.** With `max_agent_runners: 3` (see below) and a 14-day TTL, disk pressure is a genuine, recurring failure mode.

**Current `state.paths` check does NOT look at free space** — it only tests existence/writability via `os.access` (`src/sase/doctor/checks_runtime.py:222-267`, helper `_directory_target` at `:389-417`). No `shutil.disk_usage`, `statvfs`, or `RLIMIT` usage exists anywhere in `src/sase` (confirmed by grep).

**File watching is real inotify via ctypes, with a silent polling fallback.**
- `src/sase/ace/tui/util/fs_watcher.py:76-108` loads `libc` inotify symbols; `:146-181` `start()`: if `inotify_init1` fails it logs a warning and returns `False`; `:232-255` `_add_watch_path`: if `inotify_add_watch` returns `<0` (e.g. `ENOSPC` = `max_user_watches` exhausted) it logs at **debug** and counts 0. If nothing installs, `start()` returns `False` → caller silently drops to polling (`_startup_watchers.py:29-70`, docstring "Falls back silently … the auto-refresh timer remains the polling safety net").
- Per-instance ceiling `MAX_INOTIFY_WATCHES = 4096` (`fs_watcher.py:65`), and there are up to **two** watcher instances (artifacts + prompt-source, `_startup_watchers.py:83-104`) → up to ~8192 watches. On distros that still ship `fs.inotify.max_user_watches = 8192`, a busy ACE session can hit the ceiling.
- Degradation is graceful, not a hang: the safety-net reconcile is `FULL_SANITY_REFRESH_SECONDS = 60.0` (`event_refresh/_constants.py`). So exhaustion turns ~50ms live refresh into **up to 60s-stale UI** — silent, but not fatal.
- **Read-only checkable:** `/proc/sys/fs/inotify/{max_user_watches,max_user_instances,max_queued_events}` are world-readable (verified: `505837 / 128 / 16384` on this host).

**Concurrency & ulimits.** `axe.max_hook_runners = 3`, `max_agent_runners = 3` by default (`src/sase/axe/config.py:63-65`, `src/sase/default_config.yml:243-245`); each runner spawns real subprocess agents (`src/sase/axe/_process_start.py`, `orchestrator.py`, etc.). `checks_deep.py:_check_axe_state` (`:244-315`) already surfaces these two numbers in its `data` but does **not** compare them to OS `RLIMIT_NOFILE`/`RLIMIT_NPROC`. Nothing reads `resource.getrlimit`. On this host limits are huge (`ulimit -n = 524288`, `-u = 256076`), but stock Linux soft `NOFILE` is often `1024`; a TUI holding inotify fds + file panels + N concurrent agent subprocesses can plausibly starve at a low soft limit.

**Network reachability — mostly already covered; no general update ping exists.**
- Telemetry pushgateway/exposition reachability is checked: `src/sase/doctor/checks_telemetry.py:37-72` (default) and `:75-119` (deep). **Do not duplicate.**
- GitHub connectivity+auth is already checked when the GitHub plugin is installed: `checks_plugins.py:112-196` runs `gh auth status` (which exercises github.com + token).
- Provider CLIs are probed by `--version` in deep mode (`checks_deep.py:100-154`) — sase does not proxy provider API calls; the CLIs own their own network.
- The only "update self-check" is `dev_update`, which does a `git fetch` against the editable checkout's **git upstream** (`src/sase/dev_update/detect.py:46-57`) — it runs on explicit `sase` update commands, not as a background ping, and there is **no PyPI/HTTP self-update ping** to health-check. → A new generic "internet reachability" diagnostic would be low-value and partly redundant. **Recommend not adding one.**

**Chezmoi is an optional, conditional prerequisite.**
- `use_chezmoi` defaults to **`false`** (`src/sase/default_config.yml:2`; `config/core.py:86-89`).
- When enabled, config writes are remapped to the chezmoi source tree `~/.local/share/chezmoi/home` (`config/targets.py:22-53`; `CHEZMOI_HOME` at `config/core.py:25`) and applied via `chezmoi apply --force` (`_init_chezmoi_deploy.py:283-299`; also `config/targets.py:108`). If the `chezmoi` binary is missing, `deploy_to_chezmoi` prints "chezmoi not found on PATH" and returns an error only when `chezmoi_missing_is_error` is set — otherwise it's swallowed, so **config edits can silently no-op**. No doctor check references chezmoi today (grep confirmed).

---

## Proposed new diagnostics

Status model is `Literal["OK","WARN","ERROR","SKIP"]`; specs support `deep: bool` (`diagnostics/models.py:13`, `registry.py:16-23`). Suggested new group id: `"resources"`.

### 1. `resources.disk_free` — **RECOMMEND, default mode** (highest value)
- **Checks:** `shutil.disk_usage()` free bytes on (a) the resolved workspace `root_dir` (`WorkspaceStore(...).root_dir`, same source `state.paths` already resolves at `checks_runtime.py:230-233`) and (b) `sase_home`. Report per-path free/total.
- **Status semantics:** `ERROR` if free < ~1 GB on the workspace root (can't materialize even one clone → `git clone` `RuntimeError`); `WARN` if free < ~3 GB (headroom for a couple of workspaces + `.venv`); else `OK`. `SKIP` if the path can't be resolved.
- **next_steps:** "Free disk space or run `sase workspace cleanup`; each ephemeral workspace needs ~0.5–1 GB." Reference the `cleanup_ttl_days` retention.
- **Severity/impact: HIGH.** Directly maps to a hard, user-visible failure (agent launch aborts). Cheap, read-only, no subprocess.

### 2. `resources.chezmoi` — **RECOMMEND, deep mode** (conditional, but real silent breakage)
- **Checks:** only when `get_use_chezmoi()` is true **or** `CHEZMOI_HOME` exists: verify `shutil.which("chezmoi")` and that `CHEZMOI_HOME` is a dir inside a git repo. If `use_chezmoi` is false and no source dir, `SKIP`.
- **Status semantics:** `ERROR` when `use_chezmoi=true` but `chezmoi` missing (config edits/`sase init` deploys will fail/no-op); `WARN` when source dir exists but binary missing; `OK` otherwise.
- **next_steps:** "Install `chezmoi` (config write remapping / `sase init` deploy is enabled) or set `use_chezmoi: false`."
- **Severity/impact: MEDIUM.** Silent config-write failures are hard to diagnose; but only bites users who opted into chezmoi. Read-only (`which` + path stat).

### 3. `resources.ulimits` — **RECOMMEND (optional), deep mode**
- **Checks:** `resource.getrlimit(RLIMIT_NOFILE)` and `RLIMIT_NPROC` (POSIX only; `SKIP` on Windows). Compare soft `NOFILE` against a floor derived from `max_agent_runners + max_hook_runners` (from `load_axe_config()`, already imported in `checks_deep.py`) — e.g. floor `max(4096, 256 × total_runners)`.
- **Status semantics:** `WARN` if soft `NOFILE` below floor or soft `NPROC` below ~2× total runners; `OK` otherwise. Never `ERROR` (raising the soft limit is a user action, and the real ceiling is the hard limit).
- **next_steps:** "Raise `ulimit -n` (open files) / `ulimit -u`; running N concurrent agents plus the TUI's inotify fds and file panels can exhaust a low soft limit."
- **Severity/impact: LOW–MEDIUM.** Only bites on constrained/default systems; on well-configured hosts it's a no-op `OK`. Read-only.

### 4. `resources.inotify` — **OPTIONAL, deep mode, informational**
- **Checks:** read `/proc/sys/fs/inotify/max_user_watches` and `max_user_instances`; compare against the code's own ceilings (`MAX_INOTIFY_WATCHES = 4096` × up to 2 instances). `SKIP` on non-Linux (matches the watcher's own platform gate at `fs_watcher.py:81`).
- **Status semantics:** `WARN` if `max_user_watches < ~8192` or `max_user_instances < ~16` (ACE's live refresh may silently drop to 60s polling); else `OK`.
- **next_steps:** "Raise `fs.inotify.max_user_watches` / `max_user_instances` (via sysctl) to keep ACE live-refresh responsive; otherwise the TUI falls back to ~60s polling."
- **Severity/impact: LOW.** Degradation is graceful (polling safety net exists), and modern systems set generous limits (this host: 505837/128). Include it as a courtesy heads-up, not a gate. This is the most "theoretical" of the four — include only if the maintainers want completeness.

---

## Bottom line / prioritization

- **Add `resources.disk_free` (default mode).** This is the one prerequisite whose absence causes an unambiguous, silent-to-the-user hard failure (`git clone` → `RuntimeError` in `workspace_provider/utils.py:266-280`) that is currently invisible to `sase doctor`. Highest ROI, trivially read-only.
- **Add `resources.chezmoi` (deep, conditional).** Genuine silent config-write breakage for the opt-in chezmoi cohort; guarded so it's a no-op `SKIP` for everyone else.
- **Add `resources.ulimits` (deep).** Reasonable, cheap, but usually `OK`.
- **`resources.inotify` (deep, informational) — optional.** Real but self-healing via polling; lowest severity.
- **Do NOT add a generic network/PyPI reachability check.** Telemetry endpoints (`checks_telemetry.py`), GitHub (`gh auth status` in `checks_plugins.py`), and provider CLIs (`checks_deep.py`) already cover the endpoints sase actually depends on; there is no background update ping to health-check.

No files were modified.

All five agents are back with strong, evidence-backed findings. Before writing the report, let me spot-verify the most consequential/surprising claims directly so the recommendations rest on confirmed facts.

All key claims verified against source:
- Agents spawn via `subprocess.Popen` (`_process_start.py:99`) — tmux is **not** an agent-runtime dependency; but `sase ace --tmux` hard-exits (2) without it.
- `git clone` failure (e.g. full disk) raises `RuntimeError` at agent-launch time (`workspace_provider/utils.py`).
- FCM flags are appended only when non-empty — **no validation** of `push_provider: fcm` coherence.
- `fzf` missing hard-fails editor prompt-history; `CODEX_HOME`/credential handling confirms the offline credential-store approach.

Now I'll write the research report.

Research complete. I wrote it to `sdd/research/202607/sase_doctor_command_improvements.md` (no `just check` needed — it's an sdd/research markdown file).

## What I did

I read the full `src/sase/doctor/` module (20 check files + the shared `diagnostics/` framework), recovered the original MVP design constraints from the 202606 consolidated note, then ran five parallel code-exploration passes over the highest-value gap areas and **spot-verified the consequential claims against source** before writing.

## Key framing

The current `sase doctor` is genuinely strong — it already catches subtle silent-degradation cases (model-alias reroutes, Telegram token absence via `axe.chops`). So the value is in a specific class of gap: **requirements whose absence loses a capability silently, or hard-fails late inside a run instead of at doctor time.** I found several the command is blind to.

## Top findings (the ranked list)

**Phase 1 — highest ROI, default-mode, cheap:**
1. **`llm.auth`** — the biggest gap. `llm.default` verifies the provider CLI is on PATH but *explicitly never checks auth* (`checks_providers.py:47`). Installed-but-logged-out = **every `sase run` fails late and cryptically** (agents spawn the CLI via `Popen`). Every provider has an offline credential file to `stat` (`~/.claude/.credentials.json`, `~/.codex/auth.json`, …) — feasible read-only, WARN semantics.
2. **`resources.disk_free`** — ephemeral workspaces are real `git clone`s (~1 GB each); a full disk raises `RuntimeError` at launch (`workspace_provider/utils.py:266`), invisible today. `state.paths` checks writability but not free space.
3. **Promote `tools.tmux` + `tools.clipboard` out of deep-only** — tmux isn't an agent-runtime dep (agents use `Popen`), but `sase ace --tmux` hard-exits `2` without it, and vim-yank silently no-ops with no clipboard backend. Both are buried behind `--deep` today.
4. **`runtime.node`** — 3 of 5 provider CLIs install via `npm`, but node/npm is never checked.

**Phase 2/3 (opt-in cohorts + deep completeness):** FCM push config (`push_provider: fcm` + missing creds gets *zero* validation → silent no-op), `tools.fzf`, mobile-gateway binary, chezmoi enabled-but-missing, kitty-graphics/tmux-version, xprompt-LSP, ulimits/inotify.

**Also flagged:** a reliability bug — missing `prettier` makes `config.init` report spurious skill "overwrite" drift, corrupting doctor's own signal. And two things I explicitly recommend **not** adding (generic network ping; MCP — feature doesn't exist here).

The report ends with a 12-row ranked table (mode / what it reveals / status / effort / severity), a 3-phase sequencing plan, and a verification appendix.

I made this change in this session (the research report), so I'll commit it using my commit skill.

I'll record the skill use, then examine and commit the change.

The change is mine — the research report I created this session. It's an untracked file, and `$SASE_COMMIT_METHOD` is unset (defaults to `create_commit`). Let me write the commit message and commit.

The command reported success despite an index.lock message. Let me verify the repository state.

The working tree is clean and `master` is in sync with `origin/master` — the commit landed and pushed successfully. The `index.lock` message was transient noise from the concurrent precommit step; the commit completed. Let me confirm the commit exists.

Committed and pushed.

## Summary

The finalizer flagged the research report I created this session (`sdd/research/202607/sase_doctor_command_improvements.md`). I committed it via the `sase_git_commit` skill:

- **Commit:** `858a21bd2 docs: add research on sase doctor diagnostic improvements`
- **Tag:** `docs` (documentation-only, sdd/research markdown — no `just check` needed per the repo's stated exceptions)
- **State:** working tree clean, `master` in sync with `origin/master` (pushed successfully)

The transient `index.lock` message during the run came from the concurrent `just fix` precommit step; the commit itself completed and pushed cleanly, as confirmed by `git status` and `git log`.
