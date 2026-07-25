# Chat History - ace-run

- **TIMESTAMP:** 2026-07-06 23:40:04 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** 05

## Prompt

#gh:gh_sase-org__sase sase currently has an Android repo that I haven't touched in a long time and I never even tested it to see if it ran. I've been intrigued by the idea of a dedicated sase mobile app for a while now to break free of the limitations of using Telegram to interact with sase. Can you do some research to help motivate the creation of a dedicated sase mobile app? In particular my goal would be to replicate as much functionality from the TUI in a mobile native way.

Write this research to a new markdown file under the sdd/research/$(date +%Y%m)/ directory.
 %m:claude/claude-fable-5

## Response

I'll research this from several angles: the current TUI's feature surface, the Telegram integration's limitations, the state of the old Android repo, the Rust core's readiness as a mobile backend, and the broader landscape/tech options. Let me start by locating the Android repo and opening the linked repos I'll need.

I'll explore this repo thoroughly, starting with the overall structure and the TUI code location.

This is a large codebase. Let me map the TUI directory structure and get scale metrics.

I'll explore the sase-telegram plugin repository thoroughly. Let me start by understanding the structure.

Let me read the core documentation and source files in parallel.

Large codebase: ~178k lines in ace, ~150k in tui alone across 690 files. Let me read the full tree and examine the app entry point and directory structure.

I'll explore this Rust workspace thoroughly. Let me start with the high-level structure and several parallel searches.

I'll explore the repo systematically, starting with git history, structure, and key config files.

Excellent, the docs are thorough. Now let me examine the source code for technical details, limitations, and workarounds. Let me read the main modules and check code sizes.

Now let me read the core structural files: tab definitions, main app, and the tab bar widget.

Four crates. Let me read the main README and explore each crate's structure.

The build directory is huge. Let me list only source files, excluding build artifacts.

Now let me examine the main app, data providers (backend communication), and search for Rust bindings (sase_core_rs).

Let me read the key formatting and client modules that contain the medium-fighting workarounds.

Now let me read the key config files, README, and gateway API client in parallel.

Excellent, the README is very informative. Now let me explore the source tree of each crate and get LOC counts.

Let me examine the credentials/auth model, callback encoding, rate limiting, and the inbound command dispatch.

Let me examine the architecture: the core Rust facades, data providers, and skim the config for the action vocabulary.

Now let me read the core networking, app graph, and navigation files, plus grep for TODOs and hardcoded endpoints.

Substantial codebase (~74k LOC). Let me read the key module maps and binding surfaces.

Let me examine the daemon architecture, factory/settings, and search for daemon/server/telegram concepts.

Let me read the slash command list, text dispatch, and callback handler sections.

This gateway is essentially a purpose-built mobile backend already. Let me enumerate the PyO3 binding surface and the gateway internals, plus search for uniffi/wasm/mobile mentions.

Let me look at the callback dispatch, agent-launch backend integration, and the main entry loop.

Good, no real TODOs/stubs found — just UI placeholder text. Let me read the SSE client, session/pairing, MainActivity, manifest, and check the beads issue tracker for planned/incomplete work.

There's a whole `integrations/` directory with mobile gateway, mobile notifications, mobile agents, and chat install. This is highly relevant. Let me explore it fully.

Good landscape data — Codex mobile (May 2026) and Claude Code Remote Control (Feb 2026) are strong precedents. Let me dig into the third-party mobile-client ecosystem and the cross-platform tech-stack question.

Let me check the beads issue tracker for planned/incomplete work, the FCM push service, and total code size.

Let me read the main entry loop, the enabled gate, and check the CHANGELOG for feature evolution and limitations.

Now let me examine the gateway internals, storage model, and search for uniffi/wasm/mobile/ffi mentions across the repo.

Major finding: there's a `sase mobile gateway` Rust HTTP server (`sase_gateway`) with pairing, FCM push, and agent/helper bridges. Let me examine the mobile agent/notification bridges and chat install.

Let me check the API contract snapshot version, the keystore token vault (auth), and grep for any hardcoded URLs/endpoints.

Let me look at the agent launch backend wiring, code-marker reconstruction, and the planning/tale docs for limitation discussion.

Let me read the mobile notification actions, helpers, and chat install to complete the remote-access picture.

Let me check the code-marker reconstruction, bead plain-text-to-markdown conversion, and the chop scheduling config.

Core has both pure functions and filesystem/sqlite-backed operations, with a notable pure/IO split (`*_from_content`, `*_from_lines`, `*_from_bytes`). Let me examine the host_bridge abstraction and gateway server/storage model.

Now let me pivot to the TUI action vocabulary. Let me examine the config keymap and the key detail widgets.

Let me confirm the git branch/remote status and that all commits are same-day.

Let me read the config sections: mobile_gateway, ace (with keymaps), and axe.

Let me read the axe config section and examine the key detail widgets to understand what each panel shows.

The gateway uses HostBridge traits that shell out to the Python `sase` CLI. Let me confirm the subprocess coupling and daemon/storage model.

Let me read the code-marker reconstruction workaround and how responses are written back to the sase backend.

Let me examine the agent prompt/chat panel, notification modal, approval modals, and where state lives (~/.sase paths).

Let me verify the auth model — whether inbound validates the sender or accepts any user's messages.

Let me round out with the gateway CLI/bind policy, the contract snapshot shape, and the core's sqlite/event-stream storage details.

While the codebase agents finish, let me check the research directory conventions and any prior notes about mobile/Telegram in the sdd docs.

Let me examine the storage layout (~/.sase subdirs), the core facades, the AXE daemon, and the refresh/watcher model.

Let me examine the AXE daemon, the refresh/watcher model, and the CLI subcommand surface.

Let me confirm the bead sqlite/event-sourcing storage model and the notifications mobile mapping to complete the picture.

Let me map the CLI subcommand surface and the notifications module.

Let me read the help modal bindings (curated per-tab action lists) and the command catalog for a complete action inventory.

I have a comprehensive picture of the repository. Here is the structured research summary.

---

# SASE Android — Repo Exploration Report

Repo path: `/home/bryan/projects/github/sase-org/sase-android`
Remote: `git@github.com:sase-org/sase-android.git` (branch `master`, tracks `origin/master`, pushed — not just local)

## 1. Git History

- **Total commits:** 26 (`git rev-list --count HEAD` = 26)
- **First commit:** `966cc48` 2026-05-06 "feat: First commit"
- **Last commit:** `484d308` 2026-05-06 "feat: detect typed xprompt colon hints"
- **Date range:** All 26 commits landed on a **single day, 2026-05-06**, all authored by "Bryan Bugyi". Working tree is clean and in sync with origin.
- Commit messages reference an external epic/issue scheme (`sase-26.5.1`, `sase-26.6.3`, `sase-26.6.5`, "Epic 6", "Epic 7") that lives in other repos (`sase-core`, `sase_100`), not here. This is consistent with the whole app being generated in one burst by the SASE agent tool.
- The in-repo beads tracker is empty/unused: `sdd/beads/issues.jsonl` is 0 lines and `sdd/beads/config.json` has `next_counter: 1`.

## 2. Tech Stack

Kotlin + Jetpack Compose single-module Android app. Gradle Kotlin DSL with a version catalog.

- **Language:** Kotlin `2.1.10`, JVM bytecode target 17 (`compileOptions` + `jvmTarget = JVM_17`)
- **UI:** Jetpack Compose (Material 3), Compose BOM `2025.02.00`, Navigation-Compose `2.8.8`
- **Build:** Android Gradle Plugin `8.8.2`, Gradle wrapper `8.11.1` (`gradle/wrapper/gradle-wrapper.properties`)
- **SDK levels (`app/build.gradle.kts`):** `compileSdk = 35`, `targetSdk = 35`, `minSdk = 26`, `versionCode = 1`, `versionName = "0.1.0"`, `namespace`/`applicationId = org.sase.mobile`
- **Key deps (`gradle/libs.versions.toml`):** OkHttp `4.12.0` (+ mockwebserver), kotlinx-serialization-json `1.8.0`, kotlinx-coroutines `1.10.1`, AndroidX DataStore-preferences `1.1.2`, CameraX `1.4.1`, ML Kit barcode-scanning `17.3.0` (QR pairing), Firebase BOM `33.10.0` + firebase-messaging (FCM), Google Services plugin `4.4.2`
- **Test:** JUnit4 `4.13.2`, Truth `1.4.4`, coroutines-test, MockWebServer; Compose UI test + Espresso for instrumentation
- **CI (`.github/workflows/android.yml`):** GitHub Actions on push-to-master/PR, JDK 21 (Temurin), installs `platforms;android-35` + `build-tools;35.0.0`, runs `./gradlew testDebugUnitTest lintDebug assembleDebug`
- **Size:** ~11.8k lines of main Kotlin, ~6.1k lines of test Kotlin
- Lint is strict: `warningsAsErrors = true`, `abortOnError = true`, but it explicitly disables `AndroidGradlePluginVersion` and `GradleDependency` checks (i.e., stale-dependency warnings were pre-suppressed).

## 3. What Was Actually Implemented

This is a **surprisingly complete client**, not a skeleton. It is a read/act client for a **host-side "SASE mobile gateway" over HTTP REST + SSE** (not ssh, not telegram). The phone runs no agents; the gateway is authoritative (`README.md` lines 3-5, 92-106). Transport specifics:

- **REST + Bearer token auth over HTTP/HTTPS.** Base path `/api/v1`. Cleartext HTTP allowed (`usesCleartextTraffic="true"`) for LAN/Tailscale/loopback hosts.
- **SSE** for live push of `agents_changed`/`helpers_changed`/`notifications_changed`/`heartbeat`/`resync_required` events.
- **FCM** (optional) for background push *hints* only; app always re-fetches authoritative state from the gateway after a push.

### Entry point / app shell
- `app/src/main/java/org/sase/mobile/MainActivity.kt` — single `ComponentActivity`, sets Compose content, handles `sase://mobile` deep-link intents.
- `app/src/main/java/org/sase/mobile/SaseAppGraph.kt` — hand-rolled DI singleton wiring all repositories/controllers (no Hilt/Dagger).
- `app/src/main/java/org/sase/mobile/ui/SaseMobileApp.kt` — Compose `Scaffold` + `NavHost`; bottom nav (Inbox, Launch, Agents, Settings) plus routes for NotificationDetail, Update, Helpers. Defines the `SaseDestination` sealed nav graph.
- `app/src/main/java/org/sase/mobile/ui/theme/Theme.kt` — Material 3 theme.

### Networking layer (`data/api/`)
- `GatewayApiClient.kt` (758 lines) — hand-written OkHttp client covering the entire `mobile_api_v1` contract: `health`, pairing start/finish, `session`, push-subscription register/list/delete, notifications list/detail/mark-read/dismiss, plan/HITL/question action submission, agents list/resume-options/launch/launch-image/kill/retry, changespec-tags, xprompt catalog, beads list/detail, update start/status, attachment download. Includes `normalizeBaseUrl` (enforces http/https, empty or `/api/v1` path, no query/fragment), redirect-disabled client, structured error decoding, IOException→transport-error mapping.
- `GatewaySseClient.kt` — SSE event stream reader with `Last-Event-ID` resume, plus `SseReconnectPolicy` (exponential backoff + jitter).
- `GatewayApiError.kt`, `AndroidNetworkAvailability.kt`, and DTOs under `data/api/dto/` (`GatewayWire.kt`, `AgentWire.kt`, `ActionWire.kt`, `HelperWire.kt`, `NotificationWire.kt`, `GatewayJson.kt`).

### Session / pairing / auth (`data/session/`)
- `SessionRepository.kt` — pairing (manual + QR), session refresh, forget-host, auth-expiry handling; `SessionController` interface.
- `QrPairingPayloadParser.kt` — parses both JSON and `sase://pair?...` URI pairing payloads; strictly rejects unexpected fields (data-only, no command/path injection).
- `AndroidKeystoreTokenVault.kt` — bearer token encrypted with an AndroidKeyStore AES/GCM key, stored in SharedPreferences.
- `SessionStorage.kt`, `HostSessionModels.kt`, `AndroidSessionRepositoryFactory.kt` — DataStore-backed paired-host persistence.

### Feature repositories (`data/`)
- `data/notifications/` — `NotificationRepository.kt` (SSE-driven inbox + refresh state machine), `NotificationCache.kt`, push subpackage (`PushRegistrationManager.kt`, `PushMessageHandler.kt`, `PushHintPayload.kt`), local-notification subpackage (channels, deep-link targets, permission state, hint renderer), and `foreground/` connected-mode controller/store.
- `data/agents/` — `AgentRepository.kt` (list, resume/wait, text launch, image launch, kill, retry, `agents_changed` refresh).
- `data/actions/` — `ActionRepository.kt` + `NotificationActionModels.kt` + `ActionDraftStore.kt` (plan-approval / HITL / user-question action controls with draft/custom-answer preservation).
- `data/helpers/` — `HelperRepository.kt` (ChangeSpec tags, xprompt catalog, bead lookup) and `UpdateRepository.kt` + `UpdateJobCache.kt` (SASE self-update start/poll with remembered jobs).

### Screens (`ui/`)
`InboxScreen.kt`, `NotificationDetailScreen.kt` (789 lines), `LaunchScreen.kt` (918 lines, with `XpromptArgHints.kt` + `ImageAttachmentReader.kt` for image launch), `AgentsScreen.kt` (649), `HelpersScreen.kt` (769), `SettingsScreen.kt` (506, host pairing/management + push/foreground toggles), `UpdateScreen.kt`, plus `settings/QrScanner.kt` (CameraX + ML Kit) and `NotificationUiFixtures.kt`.

### Android services (`service/`)
- `ForegroundConnectedService.kt` — foreground service (type `remoteMessaging`) that keeps REST/SSE alive in background ("connected mode").
- `SaseFirebaseMessagingService.kt` — FCM token registration + data-message hint handling.

### Tests
Extensive: ~30 unit test files (repository/API/SSE/push/pairing) using MockWebServer + a route-based `FakeGateway.kt` harness, plus 9 Compose instrumentation tests (`androidTest/`), plus JSON contract fixtures under `app/src/test/resources/fixtures/gateway/` and a checked contract snapshot `app/src/test/resources/contracts/mobile_api_v1.json`.

## 4. What's Stubbed / Missing

- **No genuine `TODO`/`FIXME`/`STUB`/"not implemented" markers** exist in main source. The only `placeholder` hits are legitimate Compose `TextField` placeholder strings (`NotificationActionModels.kt`, `NotificationDetailScreen.kt`).
- **No hardcoded endpoints/IPs baked into the app.** Base URL is always user-supplied via pairing (manual entry or QR). The only host examples (`127.0.0.1:7629`, `10.0.2.2`) live in `README.md` docs, not code.
- **Auth is implemented** (Keystore-encrypted bearer token, `Authorization: Bearer`), not missing.
- Genuine gaps / deferred items (mostly documented as intentional in `README.md` "Known Limitations", lines 269-283):
  - **Never tested against a real gateway.** All 26 commits are same-day; there is no evidence any real host/gateway ran. The counterpart `sase-core` gateway and `sase_100/docs/mobile_mvp_runbook.md` are referenced but not present in this repo, so the contract it targets is unverifiable here.
  - **FCM push is non-functional out of the box:** requires a local, git-ignored `app/google-services.json` (absent) and matching host push-provider config. The Google Services plugin is only applied if that file exists (`app/build.gradle.kts` lines 136-138).
  - **Release build is unsigned/unminified by default:** signing only activates if `SASE_ANDROID_RELEASE_*` secrets are provided; `isMinifyEnabled = false` (`proguard-rules.pro` effectively unused). README notes minification is deliberately deferred for private distribution.
  - **API client is hand-written against a snapshot contract**, no codegen; drift from the real gateway is possible ("generated client adoption is intentionally deferred", README line 281-282).
  - Attachment handling is metadata/scoped-download only; no arbitrary host file browsing (by design).
  - In-repo issue tracker (`sdd/beads`) is empty — no roadmap/backlog captured locally.

## 5. Does It Plausibly Build Today (mid-2026)?

**Probably yes, but with a stale toolchain** — everything is internally consistent and pinned to early-2025 versions (~12-18 months old as of 2026-07):

| Component | Pinned version | Era | Mid-2026 note |
|---|---|---|---|
| Gradle wrapper | 8.11.1 | Nov 2024 | ~1.5 yr old; wrapper self-downloads so it still runs |
| Android Gradle Plugin | 8.8.2 | early 2025 | stale but functional; well behind 8.13+/9.x |
| Kotlin | 2.1.10 | Jan 2025 | behind 2.2.x line |
| Compose BOM | 2025.02.00 | Feb 2025 | stale |
| compileSdk / targetSdk | 35 (Android 15) | — | Android 16 (SDK 36) is current; Play targetSdk floor moves toward 36 mid/late-2026 |
| minSdk | 26 (Android 8.0) | — | fine |
| JDK (CI / bytecode) | 21 / 17 | — | fine |

Build risk factors:
- Requires exactly `platforms;android-35` + `build-tools;35.0.0` and JDK 21 present (CI installs them; a fresh mid-2026 machine may default to newer SDKs).
- `lint { warningsAsErrors = true; abortOnError = true }` makes `lintDebug` brittle — but the two checks that would flag outdated Gradle/AGP/deps are explicitly disabled, so the authors anticipated the staleness.
- Nothing is *badly* outdated (no AGP 4.x/Kotlin 1.x territory); it is a coherent early-2025 stack that would compile with its pinned wrapper, just not against the latest Android 16 tooling without version bumps.

## 6. README / Docs Stating Intent

`README.md` (283 lines) is thorough and the primary intent document. Key statements:
- **Purpose (lines 3-5):** "Android client foundation for the SASE mobile MVP … a Kotlin/Jetpack Compose client for the host-side SASE mobile gateway; it does not run agents or embed SASE core logic on the phone."
- **Scope (lines 7-33):** Compose M3 shell with inbox/detail/launch/agents/helpers/update/settings; keystore bearer-token storage; QR + manual pairing; native agent management (list/resume/launch/kill/retry); helper surfaces (ChangeSpec tags, xprompt catalog, beads); SASE update start/status; fake-gateway smoke harness; "Epic 7 adds notification permission UX, local hint rendering, foreground connected mode, FCM push hints, private APK packaging, remote-access docs, and the MVP threat model."
- **Pairing QR payload spec** (lines 35-58): JSON + `sase://pair?...` URI forms; "Payloads are data only; the app rejects arbitrary command, path, query, and fragment fields."
- **Contract source of truth (lines 92-106):** develops against `../sase-core/crates/sase_gateway/contracts/api_v1/mobile_api_v1.json`; "treat the gateway as authoritative and keep local state limited to session continuity and offline display."
- **FCM setup** (lines 108-138), **packaging/signing** (lines 141-173), **fake-gateway smoke** (176-211), a detailed **17-step manual real-host smoke checklist** (213-267) — which reads as a test plan that was written but, given the single-day history and the owner's note, evidently **never executed against a live host**.
- **Known Limitations** (269-283): private/internal APK only (not Play production), FCM needs local config, foreground mode subject to Android limits, attachments metadata-only, hand-written API client.
- Other docs: `.github/workflows/android.yml` (CI). No CHANGELOG/CONTRIBUTING/ADRs. Cross-repo runbook (`../sase_100/docs/mobile_mvp_runbook.md`) is referenced but not in this repo.

Let me examine the AXE tab bindings, the Admin/Config Center (tabs 1-6), and the ChangeSpec detail sections.

Let me confirm the agent detail panel modes, workflow display, and gather final scale metrics.

I now have a comprehensive picture. Let me do two final targeted reads to confirm the ChangeSpec detail sections and the agent chat/workflow panel content.

All external research and the Android audit are done. Three codebase agents (TUI feature inventory, Telegram plugin limitations, sase-core gateway readiness) are still running in the background — once they report back, I'll synthesize everything into the research doc under `sdd/research/202607/`.

Key findings so far:
- The mobile foundation already exists and is far more complete than "an untouched Android repo" suggests: a Rust `sase_gateway` crate with pairing/bearer auth/SSE/push, Python bridge facades, a Tailscale Serve runbook with threat model, and a ~12k-line Kotlin/Compose Android client covering inbox, notification actions (plan/HITL/question), agent launch/kill/retry, xprompt catalog, beads, and self-update — all landed 2026-05-06 and never smoke-tested against a live gateway.
- The market has since validated the product shape: Anthropic shipped Claude Code Remote Control (Feb 2026), OpenAI shipped Codex in the ChatGPT mobile app (May 2026), and an ecosystem of third-party clients (Happy, Happier, etc.) exists — mobile supervision of coding agents is now table stakes.

I have a comprehensive picture. Here is the research data.

---

# sase-core readiness assessment for a native mobile frontend

Repo: `/home/bryan/.local/state/sase/workspaces/sase-org/sase-core/sase-core_13` (workspace version `0.3.3`, edition 2021, Rust 1.78+).

**Headline finding:** the repo already contains a purpose-built mobile backend. A dedicated crate, `sase_gateway`, is described verbatim as "the local workstation HTTP gateway for future SASE mobile clients" and ships an HTTP + SSE wire contract with pairing, bearer auth, push notifications, and agent/notification/bead/changespec routes. Mobile is not hypothetical here — it is a partially-built MVP.

## 1. Crate layout & domain logic

Workspace members (`/…/Cargo.toml`), 4 crates:

| Crate | Role | src LOC |
|---|---|---|
| `crates/sase_core` | Pure-Rust core domain logic (no PyO3) | ~47,400 |
| `crates/sase_core_py` | PyO3 extension → Python module `sase_core_rs` | ~4,200 |
| `crates/sase_gateway` | Local-host HTTP/SSE gateway for mobile clients | ~12,200 |
| `crates/sase_xprompt_lsp` | LSP server for xprompt editing (a second non-Python consumer of the core) | ~4,300 |

`sase_core` module map (`crates/sase_core/src/lib.rs`) — domain logic present:
- **ChangeSpecs**: `parser.rs`, `wire.rs`, `sections.rs`, `suffix.rs` — full-file ChangeSpec parser + wire types (`ChangeSpecWire`, `CommitWire`, `HookWire`, `CommentWire`, `MentorWire`, `DeltaWire`, `TimestampWire`).
- **Agents**: `agent_scan/` (filesystem artifact scanner + sqlite index), `agent_archive/`, `agent_group_archive/`, `agent_cleanup/` (kill/dismiss planner + execution), `agent_launch/` (workspace claim/allocation + launch prep), `agent_family.rs`, `agent_name_template.rs`.
- **Beads (issue tracker)**: `bead/` — `schema.rs` (SQLite schema), `read.rs`, `mutation.rs`, `search.rs`, `work.rs`, `jsonl.rs`, `events.rs` (event-sourced streams), `cli.rs`, `config.rs`. Full CRUD + query + doctor.
- **Notifications**: `notifications/` — `store.rs` (JSONL store), `mobile.rs` (mobile notification cards / action detail / attachment manifests), `pending_actions.rs` (plan/HITL/question action responses), `wire.rs`.
- **Query engine**: `query/` — tokenizer, parser, evaluator, matchers, compiled `QueryProgram`.
- **Status state machine**: `status/` — transition validation, planner, field updates.
- **VCS**: `git_query/` — parsers for git name-status, branch name, conflicted files, local changes, workspace-name derivation. (No git execution in-core; it parses git CLI output handed in as strings.)
- **Config**: `config/` — inventory, validate, plan-edit, provenance, merge.
- **Editor/LSP support**: `editor/` — completion, definition, diagnostics, hover, frontmatter, directives (feeds `sase_xprompt_lsp`).
- **Plans / prompt stash / project specs / effort / xprompt catalog**: `plan/`, `prompt_stash/`, `project_spec.rs`, `effort.rs`, `xprompt_catalog.rs`.
- **`host_bridge.rs`**: a trait-based abstraction ("Shared host helper bridge plumbing for non-Python frontends") with mobile-shaped request/response wire types (`MobileBeadListRequestWire`, `MobileXpromptCatalogRequestWire`, etc.).

Not present in-core: chats/transcripts and workflow *orchestration* engine. "Workflows" appear only as artifact/state data structures (`WorkflowStateWire`, `WorkflowStepStateWire` under `agent_scan/`), not as an execution engine — actual agent launching is delegated to the Python `sase` CLI (see §3/§4).

## 2. Python binding surface (`sase_core_py` → `sase_core_rs`)

`crates/sase_core_py/src/lib.rs` (single 4,184-line file). Built as `crate-type = ["cdylib", "rlib"]`, PyO3 0.22 with `abi3-py312` (one stable-ABI wheel covers CPython 3.12–3.14). The pure `sase_core` crate deliberately has **no** PyO3 dependency.

The README's "one function" description is stale — the binding now exports **~130 `#[pyfunction]`s** registered via `m.add_function(wrap_pyfunction!(…))` (module init around lines 3399–3573). Representative surface, grouped:
- ChangeSpec/query: `py_parse_project_bytes`, `py_tokenize_query`, `py_parse_query`, `py_canonicalize_query`, `py_compile_query`, `py_compile_corpus`, `py_evaluate_query_many`.
- Agent artifacts/index: `py_scan_agent_artifacts`, `py_scan_agent_artifact_dirs`, `py_rebuild_agent_artifact_index`, `py_upsert_agent_artifact_index_row`, `py_query_agent_artifact_index`, `py_agent_artifact_index_status`, path helpers.
- Agent archive / dismissed groups / cleanup: `py_query_agent_archive`, `py_agent_archive_facet_counts`, `py_save_dismissed_agent_group`, `py_plan_agent_cleanup`, `py_mark_hook_agents_as_killed`, `py_delete_agent_artifacts`.
- Status/VCS: `py_is_valid_status_transition`, `py_plan_status_transition`, `py_apply_status_update`, `py_parse_git_name_status_z`, `py_parse_git_branch_name`, `py_parse_git_local_changes`.
- Beads (full): `py_bead_read_store`, `py_bead_list`, `py_bead_search`, `py_bead_create`, `py_bead_update`, `py_bead_close`, `py_bead_dep_add`, `py_bead_ready`, `py_bead_stats`, `py_bead_cli_execute`, `py_bead_export_jsonl`, etc.
- Notifications / prompt stash / config / project / launch: `py_read_notifications_snapshot`, `py_apply_notification_state_update`, `py_read_prompt_stash_snapshot`, `py_config_validate`, `py_list_project_records`, `py_prepare_agent_launch`, `py_spawn_prepared_agent_process`, `py_plan_agent_launch_fanout`.

Boundary style: functions take/return plain Python `dict`/`list`/`str`/`int`/`bool`/`None` mirroring the `*Wire` JSON shapes (no PyO3 classes leak across, except a couple of opaque handles like `PyQueryProgramHandle`). Rust errors surface as Python `ValueError`. `sase` now declares `sase-core-rs` a **hard runtime dependency** (README §"Packaging decision" note); install is `uv tool install sase` pulling a prebuilt wheel.

## 3. Wire/API layer for remote frontends — `sase_gateway`

This is the "Rust wire/API" the project docs mention. It is pure Rust (depends on `sase_core`, not on `sase_core_py`). Stack: `axum` 0.7 (HTTP), SSE via axum, `jsonwebtoken` (bearer tokens), `reqwest`+rustls (FCM push), `tokio`.

Files: `routes.rs` (~4,000+ LOC, all endpoints + SSE), `server.rs` (serve + bind policy), `daemon.rs` (daemon config/run root/socket), `storage.rs` (device/token/audit stores), `push.rs` (FCM/test push dispatcher), `wire.rs` (~1,000 LOC of DTOs), `contract.rs` (contract snapshot generator), `host_bridge.rs` (subprocess bridge to Python CLI), `main.rs` (CLI).

API (`crates/sase_gateway/README.md`), base path `/api/v1`, JSON records with `schema_version` first field, single `ApiErrorWire` error type:
- **Pairing/auth**: `POST /session/pair/start`, `POST /session/pair/finish` (one-time code → bearer token), `GET /session`. Tokens stored as SHA-256 hashes in `devices.json`; audit to `audit.jsonl`.
- **Event stream**: `GET /api/v1/events` — authenticated **SSE** stream of `EventRecordWire`, monotonic heartbeat IDs, `Last-Event-ID` reconnect replay from an in-memory ring buffer, `resync_required` on overflow (`routes.rs` SSE machinery ~lines 780–800, 2075–2113).
- **Notifications**: list/detail/mark-read/dismiss; detail mints short-lived attachment tokens; `GET /attachments/{token}` streams bytes with path/size/symlink/TTL guards.
- **Actions**: `POST /actions/plan/{prefix}/approve|run|reject|epic|legend|feedback`, `/actions/hitl/{prefix}/accept|reject|feedback`, `/actions/question/{prefix}/answer|custom` — write the same `*_response.json` files the TUI/Telegram flows use.
- **Agents**: list, resume-options, launch, launch-image (base64 upload), kill, retry.
- **Workflow helpers**: `changespec-tags`, `xprompts/catalog`, `beads`, `beads/{id}`, `update/start`, `update/{job_id}`.
- **Push subscriptions**: list/register/delete (hint-only; FCM or test provider; disabled by default).

Committed machine-readable contract snapshot: `crates/sase_gateway/contracts/api_v1/mobile_api_v1.json` (~30 KB) — records auth scheme, route list, wire field names, example pairing payloads (note the example device `"platform": "android"`). Regenerable via `--contract-out`.

## 4. Storage model & filesystem coupling (the crux for mobile)

State is **local files under `<sase_home>`** plus **SQLite**, not a network DB:
- **SQLite**: bead store schema `bead/schema.rs` (`BEAD_SQLITE_SCHEMA`, `issues`/`dependencies` tables + migrations); agent-artifact index `agent_scan/index.rs`; notifications mobile helpers. `rusqlite` is bundled.
- **JSONL/JSON files**: notifications `notifications/store.rs` → `notifications.jsonl`; bead event streams `bead/events.rs`; prompt stash; project specs; gateway `storage.rs` → `devices.json`, `push_subscriptions.json`, `audit.jsonl`; gateway mobile state under `<sase_home>/mobile_gateway/` (`agent_launch_contexts.jsonl`, `agent_kill_contexts/`, `uploads/images/…`).
- **Bead backend** shows a migration path: legacy JSONL → SQLite → event-sourced streams (`import_issues_to_event_streams`, `reduce_event_streams`).

The core **does assume local filesystem access** for its I/O operations — ~22 modules under `sase_core/src` use `std::fs`. However there is a deliberate **pure/IO split**: many operations have a pure variant that takes content and returns a plan/outcome (`parse_project_bytes`, `read_status_from_lines`, `apply_status_update` on lines, `release_workspace_from_content`, `plan_claim_workspace_from_content`, `read_project_lifecycle_from_content`, `status_plan_from_json_value`). Pure logic is separable from disk.

**Consequence for mobile (directly answers the question):** a phone cannot share the workstation's filesystem or SQLite files, and the gateway additionally **shells out to the Python `sase` CLI** for the heavy operations. `sase_gateway/src/host_bridge.rs` builds a subprocess (`Command::new(program)`, default program `vec!["sase"]`, calling `sase mobile helper-bridge <operation>`); agent launch/kill/retry go through "the fixed Python bridge." So the gateway is a thin, filesystem- and CLI-coupled server, not a self-contained portable engine.

Therefore the architecture the repo has committed to is **server-side execution + remote protocol**: the gateway runs on the workstation (defaults to binding `127.0.0.1:7629`; `server.rs::validate_bind_policy` rejects non-loopback binds unless `--allow-non-loopback`), and the phone reaches it remotely — the README/runbook point to Tailscale Serve for private remote access (runbook at `../sase_100/docs/mobile_mvp_runbook.md`, outside this repo). Compiling the core *for* the phone via UniFFI is only viable for the pure, filesystem-free subset (parser/query/status/wire); the stateful bead/notification/agent operations are inherently host-bound. UniFFI is named only as aspirational (see §5), with no UniFFI code present.

## 5. Existing thoughts on other frontends

- **UniFFI / WASM / server** are called out repeatedly as the *reason* `sase_core` is kept PyO3-free, but only as future intent — no `uniffi`/`wasm`/`tonic`/`grpc` deps or code exist. Mentions: `README.md:19`, `crates/sase_core_py/Cargo.toml:12`, `crates/sase_core/src/lib.rs:9`, `git_query/mod.rs:6`, `status/mod.rs:6`, `agent_scan/mod.rs:6`.
- **Mobile / Android**: extensively real in `sase_gateway` (pairing device metadata `platform: "android"`, FCM push in `push.rs`, contract examples). No iOS-specific code, but the wire contract is platform-neutral (`platform` is a free string field).
- **HTTP/SSE/server**: fully implemented in `sase_gateway` (axum + SSE). No gRPC/protobuf/websocket/JSON-RPC — the wire is REST + Server-Sent Events with JSON DTOs.
- **LSP**: `sase_xprompt_lsp` is an existing second non-Python frontend proving the pure-core reuse model works.

## 6. Rough scale

- 4 crates; 113 `.rs` files; ~74,500 total lines of Rust (src + inline tests).
- src LOC: `sase_core` 47,443 · `sase_gateway` 12,199 · `sase_xprompt_lsp` 4,325 · `sase_core_py` 4,184.
- Separate integration tests: `sase_core/tests` ~5,442 LOC (parity suites: `python_wire_parity.rs`, `golden_corpus_parity.rs`, `bead_storage_parity.rs`, `agent_scan_parity.rs`); `sase_xprompt_lsp/tests` ~674.
- `Cargo.lock` committed (~67 KB); release managed by release-plz; work tracked as phased plans (Phase 1A–1F, 3B/3C) referencing `sase_100/plans/202604/rust_backend_phase*.md`.

## Bottom line for the report

The Rust core is well-positioned to back a native mobile app, and the project has already started building exactly that: `sase_gateway` is a working HTTP+SSE+auth+push mobile backend with a committed versioned wire contract, reusing the same `sase_core` domain logic the Python TUI uses via `sase_core_rs`. The intended deployment is **server-side on the workstation with the phone connecting remotely** (loopback bind + Tailscale), not a phone-local core — because the core and the gateway both depend on the local filesystem/SQLite and on shelling out to the Python `sase` CLI for launch/helper operations. UniFFI-for-mobile remains an explicitly-stated but unimplemented aspiration, and would only cover the pure (parser/query/status/wire) subset; anything touching beads, notifications, agents, or launch needs the host. Key gap to note: the gateway still delegates real work to the Python `sase` binary via subprocess, so "Rust-only backend" is not yet true — the Rust layer today is a wire/API + parsing/query/index layer over a Python execution core.

Key files to cite: `crates/sase_core/src/lib.rs`, `crates/sase_core_py/src/lib.rs`, `crates/sase_gateway/README.md`, `crates/sase_gateway/src/{routes,server,daemon,storage,host_bridge,push,wire,contract}.rs`, `crates/sase_gateway/contracts/api_v1/mobile_api_v1.json`, `crates/sase_core/src/host_bridge.rs`, `crates/sase_core/src/bead/schema.rs`, `crates/sase_core/src/notifications/{store,mobile}.rs`, root `README.md`.

I have gathered comprehensive material. Here is my research summary.

---

# Research: `sase-telegram` plugin — capabilities, mechanics, and limitations

Repo: `/home/bryan/.local/state/sase/workspaces/sase-org/sase-telegram/sase-telegram_13`
Version `0.2.3` (see `pyproject.toml`). A SASE plugin ("chop") providing two-way Telegram integration.

## Scale of the codebase

- **Source: ~6,900 LOC** across 16 Python files (`find src -name '*.py' | xargs wc -l` → `6892 total`).
  - Dominated by two entry-point scripts: `src/sase_telegram/scripts/sase_tg_inbound.py` (**3,223 LOC**) and `sase_tg_outbound.py` (532 LOC).
  - Core logic modules: `formatting.py` (878), `inbound.py` (739, pure logic), `question_flow.py` (401), `telegram_client.py` (318), `bead_format.py` (290), `credentials.py` (122), `outbound.py` (105), `rate_limit.py` (82), `pending_actions.py` (80), `callback_data.py` (47), `pdf_convert.py` (24), `enabled.py` (12).
- **Tests: ~8,500 LOC** (13 files; `test_inbound.py` alone is 4,245 LOC). Heavily tested.
- **Docs: 764 LOC** — `README.md` (244), `docs/inbound.md` (141), `docs/outbound.md` (77), `docs/architecture.md` (75), plus `CHANGELOG.md` (227).
- Small, mature, single-purpose plugin. Depends only on `sase>=0.1.0` and `python-telegram-bot>=21.0` (`pyproject.toml`).

---

## 1. Full feature surface (what a user can do from Telegram)

### Outbound (SASE → Telegram) — 8 notification types
Formatting in `src/sase_telegram/formatting.py` (`format_notification`, line 321). Table also in `README.md` lines 63-72 and `docs/outbound.md` lines 54-63:

| Notification | Body | Inline buttons |
|---|---|---|
| **Plan Approval** (`_format_plan_approval`, L372) | plan text + model/agent label + runtime | 📖 Tale, ✅ Approve, 📋 Epic, 🗺️ Legend, ❌ Reject, 💬 Feedback |
| **Launch Approval** (`_format_launch_approval`, L479) | slot count, source, request id, preview | ✅ Approve, ❌ Reject, 💬 Feedback |
| **HITL Request** (`_format_hitl`, L552) | request notes | ✅ Accept, ❌ Reject, 💬 Feedback |
| **User Question** (`_format_user_question`, L728; `render_question_message`, L613) | question text + options; supports multi-select checkboxes + sequential questions | one button per option, ✅ Submit (multi), 💬 Custom |
| **Workflow Complete** (`_format_workflow_complete`, L768) | summary, PR URL, prompt snippet, attachments | 🍴 Fork (copy-text) |
| **Agent Launched** | provider/model, workspace #, prompt snippet | Fork, Wait (copy-text), Kill, Retry (callback) |
| **Agent Killed** | termination confirmation | 🔄 Redo (copy-text) |
| **Error Digest** (`_format_error_digest`, L853) | error summary | — (digest files attached) |
| **Image Generated** (`_format_image_generated`, L862) | model name | image sent inline |

Attachments: plan PDFs (Markdown rendered to PDF), diffs/commit messages embedded into a response PDF, static images as photos, GIFs as animations, videos as videos, PDFs as documents (`sase_tg_outbound.py`, `docs/outbound.md` L69-76).

### Inbound (Telegram → SASE) — user actions
- **Reply to agent questions / plan approvals / HITL** by tapping inline buttons, or via two-step feedback ("💬 Feedback"/"💬 Custom" button → type a text reply). Handled in `sase_tg_inbound.py` `_handle_callback` (L1307), `_handle_question_callback` (L1007).
- **Approve/reject plans, accept HITL, select question options** — direct callbacks write response JSON files SASE polls.
- **Launch a new agent** — send any free-form text; it becomes the agent prompt (`_handle_text_message` L2934 → `_launch_agents_with_notifications` L1635). Supports xprompt expansion (`#mentor`), multi-model fan-out (`%{%m:opus | %m:sonnet}`), auto-naming.
- **Launch agents from images** — send a photo, image document, or a Telegram album; images are downloaded to `~/.sase/telegram/images/` and referenced in the prompt (`_handle_photo_message` L1949, `_handle_document_image` L1981, media-group staging).
- **Kill / retry agents** — via buttons or `/kill`.

### Bot slash commands (7 total)
Defined in `_SLASH_COMMANDS` (`sase_tg_inbound.py` L2992-3000), dispatched in `_handle_command` (L2015), registered via `set_my_commands` so they appear in Telegram's command menu:

- `/list` — running agents with provider/model + prompt snippet
- `/kill [<name>]` — inline keyboard of agents, or kill named agent
- `/fork` — copy-text fork buttons for named agents
- `/changes [project]` — active ChangeSpec workflow tags as copy buttons (excludes Submitted/Archived/Reverted)
- `/xprompts` — builds the xprompts catalog PDF, reports its path
- `/bead [<id>]` / `/beads` — active beads as picker buttons, or renders `sase bead show <id>`
- `/update` — starts a detached SASE self-update worker, replies with log path

Unknown commands (`/start`, etc.) are **silently ignored** (L2035).

### What a user CANNOT do
No way to browse/scroll a chat transcript, view a rendered diff, navigate the agent tree/DAG, inspect a ChangeSpec interactively, view syntax-highlighted code, see live streaming agent output, or view any of SASE's TUI (ACE) concepts. Everything is a discrete push notification or a single command reply. There is no stateful UI or navigation.

---

## 2. How it works technically

- **Two CLI chops**, not a long-running service (`pyproject.toml` `[project.scripts]`):
  - `sase_chop_tg_outbound = sase_telegram.scripts:outbound_main`
  - `sase_chop_tg_inbound = sase_telegram.scripts:inbound_main`
  - Both invoked periodically by SASE's chop scheduler. Comment at `sase_tg_inbound.py` L3034 confirms the inbound chop runs "on every tick (every 5 seconds)."
- **Polling, NOT webhooks.** Inbound calls `telegram_client.get_updates(offset=offset, timeout=0)` (`sase_tg_inbound.py` L3120). `timeout=0` means short-poll (immediate return), not even long-polling — it relies entirely on the external 5-second scheduler tick. Offset persisted in `~/.sase/telegram/update_offset.txt`; saved *before* processing for at-most-once delivery (L3131-3135).
- **Bot API library:** `python-telegram-bot >= 21.0` (async), wrapped synchronously. `telegram_client.py` wraps every async call in `asyncio.run()` (`_run_async`, L25) — a fresh `Bot` instance per call because the event loop is closed each time (workaround note at L132-134). Retry/backoff decorator `_with_retry` (L30) handles `RetryAfter`, `TimedOut`, `NetworkError` (3 retries).
- **Backend connection is filesystem-based, co-located, not a network API.** The plugin runs on the *same machine* as SASE and shares `~/.sase/`:
  - Outbound reads notifications via `from sase.notifications.store import load_notifications`.
  - Inbound writes response JSON files (`plan_response.json`, `hitl_response.json`, `launch_response.json`, question responses) into each notification's `response_dir` for SASE to pick up (`inbound.py` `ResponseAction`/`response_path`, `_write_response` at `sase_tg_inbound.py` L743).
  - Deep in-process imports of SASE internals: `sase.agent.launcher.launch_agents_from_cwd`, `sase.agent.running.kill_named_agent/list_running_agents`, `sase.xprompt.*`, `sase.notifications.pending_actions`, `sase.attachments.markdown_pdf`, `sase.llm_provider.registry`, `sase.integrations.chat_install`, etc. (full list: `grep 'from sase'` shows ~40 distinct internal imports). The plugin is tightly coupled to SASE's Python internals, not a stable API.
- **State files** all under `~/.sase/telegram/` (`README.md` L184-199): `pending_actions.json`, `rate_limit.json`, `update_offset.txt`, `awaiting_feedback.json`, `media_groups.json`, `last_sent_ts`, `outbound.lock`, `commands_registered_ts`, `images/`.
- **Message formatting:** SASE Markdown → Telegram **MarkdownV2** via `markdown_to_telegram_v2` (`formatting.py` L143). Also uses `parse_mode="HTML"` for `/list` output (`sase_tg_inbound.py` L2309) — mixed formatting modes.
- **Machine enable gate:** both chops are no-ops unless `~/.sase/telegram_is_enabled` exists (`enabled.py`; checked before heavy imports, `scripts/__init__.py`).
- **Concurrency controls:** outbound takes an exclusive `outbound.lock`; high-water-mark timestamp (`last_sent_ts`) tracks last-sent notification (`outbound.py`); sliding-window rate limiter (`rate_limit.py`, default 8 msgs / 15 s).

---

## 3. Concrete limitations visible in code/docs

**Message length / truncation (the medium's hard ceiling):**
- Telegram's **4096-char** message limit (`MAX_MESSAGE_LENGTH`, `formatting.py` L18). Long messages are split (`telegram_client._split_message`, L81).
- Plans/notes truncated at **3500 chars** (`NOTES_TRUNCATION_THRESHOLD`, L21). Truncation appends literal `"... (see TUI for full output)"` (`_format_notes_text`, L314) and `"... (truncated, see attached)"` (L424, L518) — the code *explicitly tells the user to go look at the TUI or an attached PDF* because it cannot show the content.
- Prompt display capped at 1000 chars (`PROMPT_DISPLAY_MAX`, L27, workflow-complete) with `…` ellipsis.
- Plan-approval truncation uses a heuristic guess-and-check loop ("Use 0.75 factor as a conservative estimate, then refine in a safety loop", L419-437) because blockquote `>`-per-line overhead makes exact length unpredictable.

**MarkdownV2 escaping fragility:**
- Entire escaping machinery: `escape_markdown_v2` (L83) escapes 18 special chars `_*[]()~\`>#+-=|{}.!`; separate `_escape_code_entity` (L88) and `_escape_link_url` (L96) for different escaping contexts; a hand-written inline-markdown regex parser (`_convert_inline`, L104; `_INLINE_PATTERN`, L36).
- **Parse-mode fallback**: if MarkdownV2 rendering fails (malformed escaping), the client silently re-sends as **plain text**, losing all formatting (`_send_single_message` L125-142, `edit_message_text` L280-295; `docs/architecture.md` L72-73). README L92 lists this as a "feature."

**No rich UI / can't render TUI concepts:**
- **Tables are dumped into monospace code blocks** — `markdown_to_telegram_v2` collects table rows and renders them as ``` ``` ``` fenced code (L199-211). No real tables.
- **No diffs/syntax highlighting** — diffs are converted to PDF attachments (`pdf_convert.py`, embedded into a response PDF) rather than shown; there is no in-chat diff view. `/xprompts` and the bead/plan content likewise fall back to attached PDFs.
- **Horizontal rules** become a literal line of `━` box-drawing chars (L194).
- Agent trees / DAGs / ChangeSpec relationships: not renderable. `/changes` reduces a ChangeSpec to a single copy-text tag (e.g. `#hg:foobar`). `bead_format.py` flattens `sase bead show`'s tree (Parent/Children/Depends On/Blocks) into flat Markdown bullets via regex parsing (L14-56) — lossy vs. the TUI.

**Callback-data 64-byte limit:**
- `callback_data.py` (`MAX_CALLBACK_BYTES = 64`, Telegram API constraint). Forces the encoding hack of using only an **8-char notification-ID prefix** (`_notif_prefix`, `formatting.py` L367) instead of full IDs, with format `{action_type}:{notif_id_prefix}:{choice}`. `encode()` raises if it exceeds 64 bytes.

**Auth model — weak / no per-user authorization:**
- Bot token from env / `~/.sase/telegram_bot_token` (must be mode 600, checked at `credentials.py` L62) / `pass` (L77).
- Outbound sends to a **single** `SASE_TELEGRAM_BOT_CHAT_ID` (`get_chat_id`, L109). One chat only.
- **No sender allowlist / `from_user` verification anywhere.** Grep for `from_user`/`authorized`/`allowlist` finds nothing. `main()` processes *every* incoming update regardless of who sent it (`sase_tg_inbound.py` L3137-3179). Security relies entirely on bot-handle secrecy — anyone who messages the bot can launch/kill agents (mitigated only by the optional `SASE_TELEGRAM_LAUNCH_AGENTS_DISABLED` env flag, `README.md` L131).

**Single-machine / single-chat constraints:**
- Enable-flag is per-machine; token/chat-id are single global values. No multi-user, multi-device, or multi-chat model.

**Rate limits:**
- Self-imposed sliding-window limiter (8/15s default, `rate_limit.py`) plus Telegram's own flood limits (`RetryAfter` handling). Outbound sends can be throttled/deferred.

**Polling latency:** up to ~5 s inbound latency (scheduler tick) + `timeout=0` short-poll; no real-time streaming.

---

## 4. Workarounds that show the medium is being fought

1. **Expandable blockquotes as a scrolling substitute** — content 500-3500 chars is wrapped in Bot-API-7.4 expandable blockquotes (`_wrap_expandable_blockquote`, `formatting.py` L259; `EXPANDABLE_THRESHOLD = 500`). Includes hacks: empty lines replaced with **zero-width spaces** (`\u200b`) so Telegram doesn't split into separate blockquotes (L266-281), and closing `||` moved to its own line when the last line ends in ``` ``` ``` (L294-296).
2. **Code blocks converted to per-line inline code** — `_code_blocks_to_inline` (L244) exists solely because "Telegram's MarkdownV2 parser splits expandable blockquotes when they contain ``` code blocks" (L247-249). Rich code blocks are downgraded to per-line single-backtick spans.
3. **Message chunking** — `_split_message` (`telegram_client.py` L81) splits on newline → space → hard-split; only the *last* chunk keeps the inline keyboard (L162-164) so buttons don't duplicate.
4. **Backtick reconstruction** — Telegram strips backticks from user input and delivers them as separate `MessageEntity` objects; `reconstruct_code_markers` (`inbound.py` L83) re-inserts `` ` `` / ``` ``` ``` markers from entity offsets so xprompt/code handling works. Fighting the platform's own message model.
5. **Copy-text buttons as a menu/clipboard substitute** — Fork/Wait/Retry/Redo/plan/ChangeSpec buttons use `CopyTextButton` to shove pre-filled command text onto the user's clipboard (e.g. `#fork:<name> `, `formatting.py` L830-847) instead of executing an action, because there's no richer command surface.
6. **Inline keyboards as poor menus** — dynamic per-option question buttons, checkbox emojis (`☑️`/`⬜`) simulate multi-select (`render_question_message` L636), picker keyboards for `/kill` and `/bead` (up to 80/limited buttons).
7. **PDF conversion as the escape hatch for anything rich** — plans, diffs, commit messages, bead output, xprompt catalogs all get rendered to PDF attachments (`pdf_convert.py` + SASE's shared renderer) because they can't be shown inline. `_format_notes_text` literally directs users to "see TUI for full output" / "see attached."
8. **Semantic button-label remapping** — the visible "✅ Approve" button maps to the internal `run` payload (not `approve`) for compatibility (`docs/outbound.md` L65-66; `formatting.py` L453). UI labels diverge from backend semantics to fit the button constraints.
9. **Media-group staging** — Telegram delivers albums as separate updates; the code stages them in `media_groups.json` and waits a "quiet window" to reassemble one prompt (`docs/inbound.md` L82-91).

---

## Key file references
- Feature formatting & buttons: `src/sase_telegram/formatting.py`
- Inbound dispatch, slash commands, agent launching: `src/sase_telegram/scripts/sase_tg_inbound.py` (esp. `_handle_command` L2015, `_handle_text_message` L2934, `_SLASH_COMMANDS` L2992, `main` L3100)
- Outbound pipeline: `src/sase_telegram/scripts/sase_tg_outbound.py`, `src/sase_telegram/outbound.py`
- Bot API wrapper (polling, splitting, retry, parse fallback): `src/sase_telegram/telegram_client.py`
- Escaping/blockquote/truncation workarounds: `formatting.py` L83-318, L412-437
- Callback 64-byte limit: `src/sase_telegram/callback_data.py`
- Auth/creds (single chat, no sender check): `src/sase_telegram/credentials.py`
- Rate limiting: `src/sase_telegram/rate_limit.py`
- Backtick reconstruction: `src/sase_telegram/inbound.py` L83
- Bead tree flattening: `src/sase_telegram/bead_format.py`
- Docs: `README.md`, `docs/architecture.md`, `docs/outbound.md`, `docs/inbound.md`
- Design context (idle-gate removal, showing filesystem coupling): `sdd/tales/202607/remove_idle_tracking.md`

**Bottom line for the report:** Telegram gives SASE a competent *notify-and-tap-to-respond* remote control — push notifications, button-based plan/HITL/question responses, and text/photo agent launches — but every rich SASE concept (diffs, tables, code, agent trees, ChangeSpecs, chat transcripts, live output) is either truncated, flattened to plain text, dumped into a monospace block, or exported to a PDF attachment. The integration is a single-chat, no-per-user-auth, 5-second-poll, filesystem-coupled bridge whose codebase is substantially (well over half) escaping hacks, length-budget juggling, and platform-workaround plumbing — strong evidence that a dedicated mobile app with native rendering, navigation, real auth, and streaming would replace and far exceed it.

The sase-core assessment confirms the architecture story: `sase_gateway` (~12k lines of Rust, axum + SSE + pairing + FCM push, with a committed versioned API contract) is a real mobile backend that reuses the same `sase_core` domain logic backing the TUI — but it delegates heavy operations (launch/kill/helpers) to the Python `sase` CLI via fixed bridge commands, and the whole design is server-side execution with the phone as a remote client (loopback bind + Tailscale Serve), not an on-device core.

Still waiting on the TUI feature inventory and the Telegram plugin analysis — those two give me the parity gap analysis, which is the heart of the motivation document. I'll synthesize the full research file once they report.

The Telegram analysis is in, and it's damning in a useful way: the plugin is ~6,900 lines of which well over half is escaping hacks, length-budget juggling, and platform workarounds (zero-width-space blockquote tricks, 64-byte callback encoding, PDF attachments as the escape hatch for anything rich, truncation messages that literally say "see TUI for full output"). It also surfaced a real security gap — inbound processing has no sender verification at all, so anyone who finds the bot can launch or kill agents.

One agent left: the TUI feature inventory, which defines the parity target. Once it reports, I'll write the full research document.

I have gathered comprehensive data. Here is the complete feature inventory.

---

# `sase ace` TUI — Complete Feature Inventory (for mobile app replication assessment)

## 0. Scale (rough)

| Metric | Count |
|---|---|
| `src/sase/ace/**` Python | ~178,168 LOC across 821 files (excl. `__pycache__`) |
| `src/sase/ace/tui/**` Python | ~150,115 LOC across 690 files |
| `widgets/` + `modals/` combined | ~76,087 LOC |
| Widget modules | 138 files (`tui/widgets/*.py`) |
| Modal modules | 137 files; **79 `ModalScreen` subclasses** |
| Action mixin modules | 219 files (`tui/actions/**`) |
| Top-level tabs | **3** (Agents, PRs/ChangeSpecs, AXE) |
| Admin Center sub-tabs | **6** (Config, Logs, Projects, Tasks, Updates, XPrompts) |
| Mobile integration layer | ~5,290 LOC across 35 files (`src/sase/integrations/`) |

Framework: **Textual** (Python TUI). Entry: `AceApp(App[None])` in `src/sase/ace/tui/app.py`; a single-window app composed of 3 side-by-side view containers toggled by `hidden` CSS class (not Textual `TabbedContent`). Launched via `sase ace` (`src/sase/main/ace_handler.py`).

---

## 1. Tabs / Screens / Panels

### Top-level tabs (source of truth: `src/sase/ace/tui/tab_order.py:12-16`, labels in `widgets/tab_bar.py:19-23`)
`TAB_ORDER = ("agents", "changespecs", "axe")`. Startup default is **agents**. Display labels: agents→"Agents", changespecs→**"PRs"**, axe→"AXE". Cycle with `tab`/`shift+tab`; clickable tab strip.

Top bar (`app.py:281-288`) also hosts status indicators: `TaskIndicator`, `UpdatesAvailableIndicator`, `LLMOverrideIndicator`, `AliasOverridesIndicator`, `StashedPromptsIndicator`, `NotificationIndicator`. Bottom: `KeybindingFooter` (conditional keymaps).

#### A. Agents tab (`app.py:304-315`) — default
- `AgentInfoPanel` (top bar): metrics — position/total, unread, asking, starting, running, waiting, failed, read counts; grouping mode; search query; auto-refresh countdown (`widgets/agent_info_panel.py`).
- `AgentList` (left, an `OptionList`): grouped/foldable list of agents, workflow steps, attempt-history child rows, group banner rows. Grouping modes cycle project→date→status (`widgets/agent_list.py`, `models/agent_groups/`). Row glyphs documented in `modals/help_modal/agents_bindings.py:266-282` (×N steps, ◆ bead-linked, ↺ reverted, ↻N attempts, ≡ workflow, ❑ changespec, ⚡ auto-approve, etc.).
- `AgentDetail` (right, `widgets/agent_detail.py`) — combined widget, 3-state panel-mode cycle `AUTO→TOOLS→INFO` (`widgets/_agent_detail_panels.py:22-27`):
  - `AgentPromptPanel` (`widgets/prompt_panel/`): the **chat transcript / agent output** view. Sub-renderers for: chat content + thinking (`_agent_display*`, `thinking/`), tool uses (`tools_panel.py`), skill uses (`_agent_skill_uses`), memory reads (`_agent_memory_reads`), xprompts used (`_agent_xprompts`), commits (`_agent_commits`), deltas (`_agent_deltas`), context members (`_agent_context`), opened workspaces (`_agent_opened_workspaces`), slow-tool progress (`_agent_slow_tools`), artifacts (`_agent_artifacts`), and **workflow step display** (`_workflow_display`, `_workflow_steps`, `_workflow_render`).
  - `AgentFilePanel` (`widgets/file_panel/`): "diffs, markdown, etc." — live diffs, static file reads, linked-repo deltas, file list cycling, trimming.
  - `AgentToolsPanel`: tool call list.
- Tag-driven side panels cycle with `J`/`K` (`focus_next/prev_agent_panel`).

#### B. PRs / ChangeSpecs tab (`app.py:290-303`)
- `ChangeSpecInfoPanel` (metrics/countdown), `ChangeSpecList` (left `OptionList`, grouped), `AncestorsChildrenPanel` (tree neighbors).
- `SearchQueryPanel` + `ChangeSpecDetail` (right, scrollable). Detail is composed of foldable sections via `widgets/section_builders.py`: **commits, hooks, comments, mentors, timestamps, deltas** (each independently fold/cycle-able — see fold_mode keymap).
- `TabQuickStart` onboarding panel.

#### C. AXE tab (`app.py:316-321`)
- `BgCmdList` (left sidebar): background commands / lumberjacks / chop runs.
- `AxeInfoPanel` + `AxeDashboard` (`widgets/axe_dashboard.py`): status of the **axe daemon** — lumberjack status, chop runs, runtimes, uptime, output sections (`widgets/_axe_dashboard_*`).

### Modal screens (79 `ModalScreen` subclasses; highlights)
- **Approvals/HITL**: `plan_approval_modal.py`, `launch_approval_modal.py`, `user_question_modal.py` (renders Claude Code `AskUserQuestion` two-pane w/ selectable options), `workflow_hitl_modal.py`, `approve_options_modal.py`, `auto_approve_modal.py`, `confirm_*` family.
- **Notifications**: `notification_modal.py` (+ `_actions/_attachments/_options/_tags`) — inbox with tag tabs, mark read/dismiss/mute/snooze, image previews.
- **Agent lifecycle**: `agent_name_modal`, `agent_tag_modal`, `agent_cleanup_*`, `confirm_kill_modal`, `confirm_rerun_modal`, `confirm_revert_agent_modal`, `revive_agent_modal`, `save_agent_group_modal`, `saved_agent_group_revival_modal`, `agent_run_log_modal`, `agent_artifacts_modal`, `agent_neighbor_modal`, `agent_workspace_tmux_modal`, `wait_modal`, `snooze_duration_modal`.
- **Prompt/launch**: `prompt_submit_choice_modal`, `prompt_history_modal`, `stashed_prompts_modal`, `model_picker_modal`, `custom_model_input_modal`, `mentor_profile_select_modal`, `parent_select_modal`, `project_select_modal`, `workflow_select_modal`, `duration_choice_modal`, `command_input_modal`, `command_history_modal`, `command_palette_modal`.
- **XPrompts**: `xprompt_browser_*` (browser pane, preview, filter), `add_xprompt_modal`, `xprompt_config_modal`, `xprompt_item_modal`, `xprompt_select_modal`, save-target/location/filename/name modals, `snippet_*`.
- **Admin Center** (`config_center_modal.py`): full-screen tabbed modal with 6 panes — **Config** (`config_pane.py`, schema-driven live-preview editor), **Logs** (`logs_pane.py`), **Projects** (`projects_pane.py`, lifecycle/claims), **Tasks** (`tasks_pane.py`, bg-task monitor), **Updates** (`plugins_browser_pane.py`, SASE core + plugin updates w/ incoming-commit preview), **XPrompts** (`xprompt_browser_pane.py`). Opened with `#`; `1`-`6` jump, `[`/`]` cycle.
- **Other**: `help_modal/` (per-tab binding help), `tab_guide_modal.py` (onboarding), `models_panel.py` (model aliases), `runners_modal.py`, `rename_cl_modal.py`, `reword`/`mail` handlers, `zoom_panel_modal.py`, `preview_panel_modal.py`, `quit_options_modal.py`, `recursive_finder_modal.py`, `hook_history_modal.py`, `mentor_review_modal.py`, `revive_agent_modal.py`.

---

## 2. Key user actions (grouped; vocabulary from `src/sase/default_config.yml:60-237` + `help_modal/*_bindings.py`)

**Launching agents**: `start_custom_agent` (`+`), `start_agent_home` (`space`), `start_agent_from_changespec` (`ctrl+@`), repeat-last selection, quick-launch/bulk/multi-model/multi-prompt/repeat launches (`tui/actions/agent_workflow/_launch_*`), leader `,h`/`,space` run-agent, prompt-bar submit with xprompt/snippet/directive expansion.

**Responding to agents / approvals**: `accept_proposal` (`A`) = open auto-approve menu / answer HITL; plan approval modal; launch approval modal; user-question modal; workflow HITL modal. Handlers in `tui/actions/agents/_notification_*`, `_approve.py`, `_workflow_hitl.py`; backend response writers `src/sase/plan_approval_actions.py`, `launch_approval_actions.py`.

**Agent management**: `kill_agent` (`x`), `open_agent_cleanup_panel` (`X`), `run_workflow`/retry (`r`), `rename_cl`/name agent (`n`), fork chat as agent (`f`), revive dismissed (`R`), wait-for-agent (`W`), edit wait deps (`w`), save/dismiss marked (`s`), mark/unmark (`m`), toggle unread (`U`), tag agent (`N`), revert agent + linked repos (`,r`), toggle attempt-history view (`D`).

**Viewing**: chat transcripts (prompt panel), diffs (`show_diff` `d` on PRs; file panel live diff on agents), agent run log (`V`, `,A`), artifacts pane (`a`), tools/metadata panel cycle (`]`/`[`), zoom panel (`z`), edit chat/panel in editor (`e`/`E`), thinking panel toggle.

**ChangeSpecs / PRs / commits**: change status (`s`), bulk status (`S`), mail PR (`M`), accept/spec-only/mail (`A`/`!`/`@`), rebase (`b`), checkout to workspace 1-9 (`C`/`c1..c9`), rewind to prev commit (`R`), edit hooks (`f`), reword (`w`), add tag (`W`), sync workspace (`Y`), edit spec (`e`), view files (`v`), fold/cycle sections (fold_mode `z`). Commit path is `sase commit` (git-based).

**Workflows**: `run_workflow` (`r`), workflow select modal, CRS/fix-hook workflows run by AXE daemon, mentor review (`,C`), kill mentors (`,M`).

**ChangeSpec/mentor context**: comments clear (`,c`), review mentor comments (`,C`).

**XPrompts**: browse/preview (Admin Center tab 6 + `xprompt_browser_*`), save draft as xprompt, local xprompt conversion, snippet management, edit last VCS xprompt (`ctrl+g`), xprompt arg-assist and completion in prompt bar.

**Notifications**: `show_notifications` (`i`), jump-to-notification (`,n`), mark all read, dismiss/mute/snooze, tag tabs. Backend: `src/sase/notifications/` (store/senders/catalog/priority/pending_actions).

**Prompt history / stash**: `restore_prompt_stash` (`@`), prompt history (`,.`), edit-first (`,ctrl+g`), cancelled history (`,>`), stack editor.

**Queries / navigation**: `edit_query` (`/`), saved queries `0-9`, prev/next query (`^`/`_`), jump modes (`'`, `` ` ``, `ctrl+o/k`), ancestor/child/sibling modes (`<`/`>`/`~`), grouping cycle (`o`/`O`).

**AXE control**: start/stop axe (`,! x` / bang `!x` / `x` on AXE tab), run chop / re-run bgcmd (`r`), clear output (`X`), run background command (`,!`/`!!`), runners info (`,R`).

**App/system**: quit (`q`), quit/restart menu (`Q`), refresh (`y`), full-history refresh (`,y`), Admin Center (`#`), command palette (`:`/`;`), help (`?`), tab guide (`,?`), update sase/core/plugins (`,U`), models panel (`,m`), capture repro bundle (`,B`), copy mode (`%` — copy chat path/prompt/name/snapshot/diff), leader/bang modes.

---

## 3. Architecture — how the TUI talks to the backend

**No client/server or daemon for TUI reads.** The TUI is a direct-read process over the on-disk state tree plus a Rust extension:

- **Rust bindings**: `sase_core_rs` is a **hard runtime dependency** (compiled extension wheel). Loaded strictly via `src/sase/core/rust.py` (`require_rust_extension` / `require_rust_binding`; no Python fallback). 25 modules import it. Facades in `src/sase/core/`: `parser_facade`, `query_facade`, `status_facade`, `git_query_facade`, `agent_scan_facade`, `notification_store_facade`, `prompt_stash_facade`, `project_lifecycle_facade`, `agent_cleanup_facade`, `wire_conversion`, etc. (`core/__init__.py:1-24`). ChangeSpec parsing, query eval, status transitions, agent scan run in Rust; TUI passes wire records.
- **Data providers**: `tui/data_providers/` defines an `AgentsDataProvider` protocol with a `DirectAgentsDataProvider` and a scaffolded-but-**disabled daemon path** — `_settings.py: agents_daemon_reads_enabled() -> False`; `_factory.py` always returns the direct provider. Snapshot types (`_types.py`) include `used_daemon`, `AgentsViewport` (start_row/visible_rows/prefetch_rows), and daemon delta-apply plumbing (`AgentEventApplyResult`) — i.e., a daemon read model is designed but not yet turned on.
- **State on disk** (`src/sase/core/paths.py`): root `~/.sase/` (override `SASE_HOME`). Subdirs include `projects/`, `notifications/`, `axe/` (daemon state, `axe/lumberjacks/`, `axe/shared/`), `comments/`, `reverted/`, `user_question/`, `telegram/`, `commit_state/`, `logs/`, `home/`, `repos/`, `spec_writer/`, `images/`, `archived/`, `chat_install/`, plus top-level `prompt_stash.jsonl`. High-volume dirs are **YYYYMM-sharded**. Agent artifacts live under per-agent `artifacts/` dirs. ChangeSpecs are `.sase` project files.
- **SQLite** used narrowly: dismissed-agent bundle index (`ace/dismissed_bundle_index/_schema.py`), beads DB (`bead/db.py`), agent-artifact index (`core/agent_artifact_index_lifecycle.py`). Most state is JSON/JSONL files, not a central DB.
- **Refresh / event model**: **inotify filesystem watcher** (`tui/actions/event_refresh/_watcher.py`, `util/fs_watcher.py`) coalesces `~/.sase` changes and maps changed paths → dirty surfaces (changespecs/agents/axe/notifications), gated by a nav-gate (defers during j/k bursts) and prompt-input defer. Plus periodic auto-refresh (`refresh_interval` default 10s, `app.py:206`). Debounced per-tab display refresh. No push/socket; it's file-watch + poll.
- **AXE daemon** (`src/sase/axe/`): a **separate background scheduler process** ("lumberjacks" running "chops") that advances hooks, mentors, CRS/fix-hook workflows, wait deps, comment checks, cleanup, and an hourly error digest (config `default_config.yml:239-289`). The TUI can auto-start/stop/restart it (`axe/process.py`) and monitors its file state (`axe/state.py`); communication is via disk state, not RPC.

---

## 4. Remote access / non-terminal frontends — YES, a full mobile stack exists

This is the most relevant finding for a mobile app: **the mobile backend is already built.**

- **`sase mobile gateway`** (`src/sase/integrations/mobile_gateway.py`, parser `src/sase/main/parser_mobile.py`, config `default_config.yml:20-33`): launches a **Rust HTTP server binary `sase_gateway`**. Binds `127.0.0.1:7629` by default (loopback-only unless `--allow-non-loopback` for LAN/tailnet). Exposes a JSON REST API: `GET /api/v1/health`, `POST /api/v1/session/pair/start` — device **pairing flow** (pairing code + pairing_id + expiry printed on start). Base URL `http://host:port`.
- **Push notifications**: `push_provider` = `disabled | test | **fcm**` (Firebase Cloud Messaging HTTP v1). Config: `fcm_project_id`, `fcm_service_account_json`, `fcm_credential_env`, `fcm_dry_run`, push timeout/retry (`mobile_gateway.py:40-47`, config `:26-32`). So mobile clients get **remote push**.
- **Agent bridge** (`sase mobile agent-bridge`, `integrations/mobile_agents.py`) — JSON stdin/stdout ops the gateway shells out to: **list-agents, resume-options, launch-text, launch-image, kill-agent, retry-agent**. Supports image uploads, project context, model directives, retry lineage. i.e., a phone can **launch/kill/retry agents and see agent lists**.
- **Notification bridge** (`integrations/mobile_notifications.py` + `_mobile_notification_actions.py`): read a notification snapshot (`read_mobile_notification_snapshot`: unread_only/newer_than/limit filtering) and **execute actions remotely**: `execute_mobile_plan_action` (approve/reject/feedback + commit_plan/run_coder/coder_prompt/coder_model), `execute_mobile_launch_action`, `execute_mobile_hitl_action` (accept/reject/feedback), `execute_mobile_question_action` (answer/custom). Writes the same response JSON files the TUI writes (`plan_approval_actions.py`/`launch_approval_actions.py`), with attachment manifests (`_mobile_notification_attachments.py`). So a phone can **respond to agent questions, approve plans/launches, answer HITL** — full parity with the TUI approval flow.
- **Helper bridge** (`sase mobile helper-bridge`, `integrations/mobile_helpers.py`): **changespec-tags, xprompt-catalog, beads-list, beads-show, update-start, update-status** — catalog/beads browsing + triggering SASE self-update from mobile.
- **Chat install worker** (`integrations/chat_install.py`, `sase chat` subcommand, config `chat_install:`): detached background installer/updater that also restarts the axe daemon — supports remote "update SASE" from chat/mobile.
- Notification `action` types (`notifications/senders.py`, `models.py:18`): `HITL`, `UserQuestion`, `PlanApproval`, `LaunchApproval`, `JumpToChangeSpec`, `JumpToMentorReview`, `ViewErrorReport`, `memory_review`, `Tmux`. These are what push notifications/mobile actions map to.

No web UI / no Telegram code in this tree (there is a `~/.sase/telegram/` state dir referenced and historical `sase_plan_telegram_*.md` design docs at repo root, but no live telegram module under `src/sase/`). The live non-terminal frontend is the **mobile gateway + native mobile client** consuming the REST API + FCM push.

---

## 5. Key file references

- App shell / layout: `src/sase/ace/tui/app.py` (compose `:273-322`, tab switching `:341-425`).
- Tabs: `src/sase/ace/tui/tab_order.py`, `widgets/tab_bar.py`, `commands/_tabs.py`.
- Action vocabulary / keymaps: `src/sase/default_config.yml:60-237`; per-tab curated lists in `src/sase/ace/tui/modals/help_modal/{agents,changespecs,axe}_bindings.py`.
- Detail panels: `widgets/agent_detail.py`, `widgets/prompt_panel/**`, `widgets/file_panel/**`, `widgets/changespec_detail.py`, `widgets/section_builders.py`, `widgets/axe_dashboard.py`.
- Admin Center: `modals/config_center_modal.py:1-24` (6 sub-tabs).
- Rust backend: `src/sase/core/rust.py`, `src/sase/core/__init__.py`, `src/sase/core/*_facade.py`.
- Data provider (daemon scaffolding, currently direct): `tui/data_providers/{_factory,_settings,_types,_direct}.py`.
- Refresh model: `tui/actions/event_refresh/_watcher.py`, `util/fs_watcher.py`.
- Storage layout: `src/sase/core/paths.py`.
- AXE daemon: `src/sase/axe/process.py`, `axe/state.py`, config `default_config.yml:239-289`.
- **Mobile stack** (primary for the mobile-app question): `src/sase/integrations/mobile_gateway.py`, `mobile_agents.py`, `mobile_notifications.py`, `_mobile_notification_actions.py`, `mobile_helpers.py`, `chat_install.py`; parser `src/sase/main/parser_mobile.py`; config `default_config.yml:20-33`.
- Notifications backend: `src/sase/notifications/{senders,models,store,catalog,pending_actions,priority}.py`.
- Approval response writers (shared TUI+mobile): `src/sase/plan_approval_actions.py`, `launch_approval_actions.py`, `plan_approval_choices.py`.

**Bottom line for mobile replication**: the TUI is a wide feature surface (3 tabs + 6-pane Admin Center + ~79 modals + ~130 keybound actions across launch/approve/review/manage/commit/xprompt/workflow/notification domains, ~150k LOC), but a **mobile-oriented backend already exists** — a loopback Rust HTTP gateway with device pairing, FCM push, and JSON bridges that cover the highest-value subset: list/launch/kill/retry agents, read notifications, and approve plans / approve launches / answer HITL / answer questions, plus xprompt/bead catalogs and self-update. A mobile app would reuse that gateway rather than re-implement the file-watch/Rust-facade reads directly.

All four research streams are complete. Now I'll synthesize everything into the research document.

Research written to `sdd/research/202607/sase_mobile_app_motivation.md`. Since the only change is a markdown file under `sdd/research/`, no `just check` run is needed.

The headline finding reframes the whole question: **you don't need to motivate building a mobile app — you already built one and never turned it on.** The May 2026 mobile MVP epic (all landed 2026-05-06) produced a complete vertical slice across three repos:

- **`sase_gateway`** in sase-core (~12.2k LOC Rust): axum REST + SSE server with QR/code pairing, bearer auth, audit log, FCM push, and a committed versioned API contract covering notifications, plan/HITL/question actions, agent launch/kill/retry, image launch, xprompts, beads, and self-update.
- **Python bridge facades** in this repo, whose mobile actions write the exact same response files the TUI writes.
- **`sase-android`** (~11.8k LOC Kotlin/Compose + 6.1k test LOC): a complete client for that contract — Inbox/Launch/Agents/Settings screens, Keystore token vault, SSE reconnect, CameraX QR pairing, foreground connected mode. No stubs, no TODOs. What never happened is the 17-step manual smoke checklist in its README — it has never talked to a live gateway.

The rest of the document builds the case around that:

- **Telegram is structurally maxed out.** Over half of the ~6.9k-LOC plugin is workaround code — MarkdownV2 escaping, 4096-char splitting, 64-byte callback hacks, zero-width-space blockquote tricks, PDFs as the escape hatch — and truncation messages literally say "see TUI for full output." It also found a real security gap: inbound Telegram handling does **no sender verification**, so anyone who discovers the bot can launch/kill agents.
- **The market validated the exact shape SASE built**: [Claude Code Remote Control](https://venturebeat.com/orchestration/anthropic-just-released-a-mobile-version-of-claude-code-called-remote) (Feb 2026), [Codex in the ChatGPT mobile app](https://openai.com/index/work-with-codex-from-anywhere/) (May 2026), and OSS clients like [Happy](https://github.com/slopus/happy) — all "phone supervises, workstation executes," which is precisely the gateway's architecture. SASE's differentiators are self-hosted/tailnet-private transport and its domain objects (ChangeSpecs, beads, xprompts).
- **TUI parity is tiered, not 1:1.** Tier 0 (approvals, launch, kill, notifications) is already implemented. The Tier 1 gaps that would make it a real supervision workbench are chat transcripts, native diff rendering, and ChangeSpec list/detail — all backed by logic already in `sase_core`, and all surfaces where mobile beats both Telegram and TUI-over-SSH. Admin Center and the keyboard-first long tail are explicitly out of scope.
- **Recommended path**: Phase 0 is just resurrecting the existing MVP — build the gateway, run the smoke checklist, expose via Tailscale Serve from athena (the runbook for this is already written, threat model included). Then extend the gateway with the Tier 1 read endpoints as a single shared contract that both the Android app and the future web client (per your April `sase_web_client_research.md`) consume. Keep Kotlin/Compose; skip Flutter/KMP and on-device UniFFI for now.

One caveat worth knowing: the Android toolchain is pinned to an early-2025 stack (AGP 8.8.2, SDK 35) — coherent and buildable, but due a routine bump before serious new work.

The research file I created needs to be committed. I'll use the commit skill as instructed.

Only the one new research file. Writing the commit message and committing.

Committed the research doc. The finalizer-flagged file `sdd/research/202607/sase_mobile_app_motivation.md` was mine from this session, so I committed it via the `sase_git_commit` skill as `docs: add research motivating a dedicated sase mobile app`, staging only that file. The commit pushed successfully and the working tree is now clean and in sync with `origin/master`. No `just check` run was needed since the only change was a markdown file under `sdd/research/`.
