# Chat History - ace-run

- **TIMESTAMP:** 2026-07-06 10:58:04 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** refresh_docs.sase.75e4470f2eea.update

## Prompt

%name:refresh_docs.sase.75e4470f2eea.update
#gh:gh_sase-org__sase %g:chop Can you help me review the documentation in the README.md file and in the markdown files contained in the docs/
directory? Namely:

- Ensure that all documentation is up to date and accurate.
- Look for gaps in the documentation. For example, should we add a new section to the README.md file? Should new docs/
  markdown files be created?
- Review git commits since the last documentation update to identify any important changes worth documenting.

When you have completed the review, please improve the documentation as needed.
 %m:claude/claude-fable-5

## Response

I'll review the README and docs/ for accuracy and gaps. Let me start by scoping the documentation and recent git history.

I'll start by investigating the two docs commits and the overall structure in parallel.

I'll start by gathering the relevant commits and exploring the code structure in parallel.

Let me read the research doc and inspect the code commits in parallel.

The research file path differs. Let me find it and read it.

Let me examine the core alias files and the relevant docs in parallel.

Now let me look at the docs, default_config.yml, the schema, doctor checks, and the models panel TUI code.

I'll start by exploring the doc and the relevant source files in parallel.

The research doc is comprehensive and self-documents the epics. Now let me verify current documentation coverage and key code facts. Let me run parallel searches.

Let me read the rest of the doc and examine the key commits in parallel.

I'll start by exploring the repo structure and reading the key documentation files and relevant commits in parallel.

Let me read the models panel TUI code, the top-bar indicator, and the doctor checks.

Let me read the documentation files and the mode_switch module in parallel.

v1 is well covered in docs/xprompt.md; v2 appears undocumented. Let me verify precise v2 code facts in parallel.

Now let me read the mode_switch module code, other docs, and config files in parallel.

Let me read the full commit details and the rest of the doc.

I'll start by exploring the repository structure and gathering information about the relevant commits and files in parallel.

Dependencies installed. While the five audit agents work, let me get a baseline strict docs build to catch any existing breakage.

Let me read the doctor alias check, default_config.yml alias section, the schema, and the models panel rendering/edit helpers.

Now let me read the repos module (dev checkout layout), config files, and remaining docs.

Now let me verify the CLI parsers and schema block.

Let me read the default_config.yml alias section, the config schema, and check how @alias is used in prompts (%m/%model directive).

Let me examine the init CLI surface, the xprompt commits, and read the relevant docs in parallel.

Baseline docs build passes. The five audit agents are still researching — I'll compile their findings into doc edits as they complete.

Now let me read the remaining docs and examine the plugin update keybindings (commit c095d438d) and the Updates tab code.

Let me read the full doc sections for the alias content in llms.md, configuration.md, and ace.md.

Let me verify the YAML validation rules, the /sase_run skill, and remaining doc coverage.

Now let me read plugins.md and examine the plugin update keybinding rework commit.

Let me read the current parser state, the CLI docs, beads docs, xprompt docs, and mkdocs nav in parallel.

Let me verify the discovery search paths and confirm exactly what docs/xprompt.md already covers.

The llms.md content looks fairly current. Let me check the commit dates and which files each doc-related commit touched, to understand the true doc state.

Let me examine the Updates tab keybindings/mode-switch, pyproject.toml, the restart-after-plugin-change commit, and grep docs for related terms.

Let me confirm the display-label field names and check for any existing agent_families doc reference.

Now let me run targeted greps against the doc and verify keybindings in default_config.yml.

Let me examine the CLI docs, xprompt docs, index, the CLI parser, and run the stale-reference greps in parallel.

This reveals something important. There IS a docs commit (37b8257d2) for sase-5e.5, and two 2026-07-03 commits that touched docs. Let me verify the actual branch history and ancestry to understand the true current doc state.

Let me run the stale-reference greps, enumerate the CLI subcommands, and read index.md in parallel.

Let me grep the docs comprehensively for mode-switch, dev_root, restart, and version terms to confirm what is and isn't documented.

Let me verify the tab guide leader binding context, the info-strip source, plugin-update keybindings, and configuration.md.

Let me check the `launch` parser, read index.md, the sdd.md research context, and verify the idle removal commit.

Let me broaden the search across all docs and confirm the mode-switch is undocumented everywhere, plus check for stale Updates-tab keymaps and dev layout.

Let me verify the info-panel render format and the plugins keymap section in default_config.yml.

Now I understand the history: docs WERE updated (5d.5 `a27b4572e`, 5e.5 `37b8257d2`) and later `72c62642a`/`8b0ff2c9f` (2026-07-03) further changed the alias config. All are ancestors of HEAD. Let me verify the current docs against current code carefully. Let me read the full ace.md Models Panel section and configuration.md alias section.

Let me confirm the dev-layout change in 672c3cea8 and the CLI mode-switch workflow (confirmation/restart) in the update handler.

Let me confirm the onboarding/vim/slow-tool-call coverage gaps in the doc.

Let me read the mode-switch handler portion to confirm the confirmation prompt and restart behavior.

Let me check the `launch` command in cli.md, enumerate all docs markdown files for nav orphans, and read the launch parser.

I have all the facts I need. Here is my report.

---

# Documentation Coverage Audit: Dynamic Agent Families (sase-5f / sase-5g)

## Summary

The two "docs" commits did **not** touch `docs/`. `f424add87` added a PNG infographic and `b9d91d616` added a research note — both under `sdd/research/202607/`, which is the internal SDD research corpus, **not** the published MkDocs site. The only user-facing doc that was actually updated for this epic is `docs/xprompt.md` (updated by `a660d9227`, sase-5f.5), and it covers the **v1** surface only. The entire **v2** surface (sase-5g) is undocumented in `docs/`.

## Task 1 — The research artifacts

- **Research note:** `sdd/research/202607/dynamic_agent_families_user_manual_research.md` (488 lines) — a near-complete user-manual design doc. Its own §5 "Documentation Status and Gaps" and §4 "Usage Recipes" are effectively a doc-author's outline. It documents both epics: v1 (user-initiated `%n(parent, suffix)` family extension, queueing, `#with_feedback`/`#with_q_and_a`) and v2 (plan-approval choice registry, the `standard_plan_chain` evaluator, `role_completed` seam, `kind: agent_family` YAML custom roles, approval-gate member toggles + sticky defaults, `LaunchApproval` + `/sase_run`, custom-role display labels).
- **Infographic:** `sdd/research/202607/dynamic_agent_families_user_manual_research_infographic.png` (1.2 MB binary; a companion visual to the note).

I verified the note's technical claims against the current tree (its line anchors drift, but the facts hold). Details below are re-confirmed from source, not just copied from the note.

## Task 2 + 3 — User-facing features, verified facts, and current doc coverage

### A. `%n(parent, suffix)` family attach (v1 — user-initiated) — DOCUMENTED
- **Where triggered:** an xprompt directive typed in any prompt (CLI `sase run`, TUI prompt bar, Telegram/mobile). Parsing: `src/sase/agent/family_attach.py`; separator `AGENT_FAMILY_SEPARATOR = "--"` in `src/sase/plan_chain.py`.
- **Forms:** `%n(parent, suffix)` → `<base>--<suffix>`; `%n(parent, @)` → next free numeric feedback slot.
- **Coverage:** `docs/xprompt.md:1028-1031` (quick ref) and `docs/xprompt.md:1090-1108` (full section: parent resolution, `<family-base>--<suffix>` naming, bare-token rule, collision → `%n(parent, @)`).

### B. Queueing behind running parents / WAITING child rows (v1) — DOCUMENTED
- **User meaning:** if the parent is still running, the child launches immediately and renders as a **WAITING** family-member child row folded under the running parent; it starts when the exact parent artifact completes successfully, and is cancelled to **STOPPED** (with a notification) if the parent fails/kills/stops.
- **Coverage:** `docs/xprompt.md:1100-1104`. TUI child-row rendering also touched by `docs/ace.md` family sections (`docs/ace.md:1278, 1316, 1524`), though those predate this epic and don't call out WAITING child rows specifically.

### C. `#with_feedback` / `#with_q_and_a` follow-up xprompts (v1) — DOCUMENTED
- **User meaning:** pure prompt-assembly xprompts (they build text; `%n` does the launching). `#with_feedback` infers `parent=` from a co-occurring `%n(parent, suffix)`; `#with_q_and_a` takes a `qa_file` JSON.
- **Coverage:** `docs/xprompt.md:868-895` (table, examples, `qa_file` shape, `parent` inference). Source: `src/sase/xprompts/with_feedback.yml`, `with_q_and_a.yml`, `src/sase/main/feedback_prompt.py`, `src/sase/main/qa_prompt.py`.

### D. Glossary caveat (`--` families vs `.` hoods) — PARTIALLY DOCUMENTED
- `docs/xprompt.md:897-900` carries a *proposed* rewording note but the actual glossary rewrite hasn't landed. The task's premise ("families are `<name>--<role>` groups in the ACE Agents tab") matches the `--` model.

---

### E. `kind: agent_family` YAML custom roles (v2) — **UNDOCUMENTED**
Nothing in `docs/`. Verified facts a doc author needs (all from `src/sase/agent_family/custom_definitions/validation.py`):

- A YAML file is recognized as a family definition only if top-level `kind: agent_family` is present.
- **Top-level fields** (`validation.py:68-80`): `kind: agent_family`; `schema_version: 1` (must equal 1, else `"schema_version must be 1"`); `id` (required, regex `^[A-Za-z][A-Za-z0-9_]*$`); `version` (required positive int); `extends` (optional; only `standard_plan_chain` accepted, and it's the default); `roles` (required non-empty mapping).
- **Per-role keys** (`_ROLE_KEYS`, `validation.py:36-51`; unknown keys → load error):
  - `suffix` (`validation.py:294-314`) — default `--<role_id>`; must match `^--[A-Za-z0-9_]+$`; `.`/single-`-` spellings rejected; must not collide with reserved suffixes `--plan --q --code --epic --legend --commit`.
  - `prompt_template` (required) — an xprompt reference; validated against the catalog (`validation.py:330-347`). Format placeholders available: `plan_file`, `source_artifacts`, `artifacts_ref`, `outcome`, `source_role`, `role`.
  - `placement` (required mapping with required `after: <role>`, `validation.py:317-327`) — `after: plan` binds to the plan gate; `after: code` (etc.) binds to the `role_completed` seam.
  - `on_done` (required) — one of `re_review | continue | terminate` (`validation.py:186-190`).
  - `on_failure` (required) — one of `notify_and_continue | notify_and_stop` (`validation.py:191-195`).
  - `auto` (**required, no default** — this is the guard against "testers that never run") — `run | skip` (`validation.py:196-200`).
  - `default` (optional bool, default `false`, `validation.py:201-204`).
  - `max_visits` (optional positive int, default `3`, `validation.py:205-208`).
  - `label` / `done_label` (optional; ≤ 24 chars; regex `^[A-Za-z0-9][A-Za-z0-9 _/-]*$`; `validation.py:275-291`, `_DISPLAY_LABEL_MAX_LEN = 24`).
  - `delegated_budget` / `delegated_budgets` — reserved, accepted+snapshotted but not interpreted.
- **Discovery precedence** (`src/sase/agent_family/custom_definitions/discovery.py:27-73`, later overrides earlier by `id`):
  1. bundled package xprompts dir;
  2. plugin `sase_xprompts` resources;
  3. `~/.config/sase/xprompts/<project>/` (`discovery.py:140`);
  4. workspace `<workspace>/.xprompts/` and `<workspace>/xprompts/` (`discovery.py:157`);
  5. general xprompt search paths.
- **Bundled examples are inactive** (deliberately outside the search path): `src/sase/xprompts/examples/agent_families/improve_plan.yml` and `tester.yml` (I read both — exact contents match the note's §3.4 listings). To enable, copy into an active xprompts dir. Their prompt templates: `src/sase/xprompts/agent_family_improve_plan.md`, `agent_family_tester.md`.
- **Listing:** definitions appear in `sase xprompt list` JSON with `"type": "agent_family"` / `"kind": "agent_family"` (`src/sase/main/xprompt_handler.py:184-185`); `sase xprompt explain` does not cover them.

### F. Plan-approval member selection (v2) — **UNDOCUMENTED**
- **CLI** (`src/sase/main/parser_plan.py:86-103`): `sase plan approve <SELECTOR> [-w/--with ROLE] [-W/--without ROLE]` — both repeatable (`action="append"`, dests `with_members`/`without_members`). Example in the parser epilog (`parser_plan.py:53`): `sase plan approve abcdef12 --with tester`. `docs/cli.md:89` lists `sase plan approve` but documents only `--kind`; no `--with`/`--without`.
- **TUI:** the existing `c` (custom) path on the plan-approval modal renders an "Also run:" section; digit keys `1`-`9` toggle members (`ApproveOptionsModal`, `src/sase/ace/tui/modals/approve_options_modal.py`). `docs/ace.md:1572` documents the `c` custom approval dialog but not the "Also run" member toggles.
- **Remote:** Telegram/mobile get no toggles; the notification preview appends `Also run: <ids>` and applies sticky defaults.

### G. Sticky project defaults config (v2) — **UNDOCUMENTED**
- **Key:** `agent_family.plan_approval.default_members` — a mapping of role id → bool. Schema: `src/sase/config/sase.schema.json:113-134` (`additionalProperties: {type: boolean}`, `additionalProperties: false` at each level). Default: `src/sase/default_config.yml:6-11` (`default_members: {}`). Precedence: explicit gate selection > this project config > the role's own `default`.
- `docs/configuration.md` has **no** `agent_family` section (confirmed: zero matches).

### H. `role_completed` after-code seam + evaluator (v2) — **UNDOCUMENTED**
- Under-the-hood: `src/sase/agent_family/standard_plan_chain*.py` (facade + `_definition.py`, `_models.py`, `_evaluator.py`). New additive `agent_meta.json` fields (`agent_family_config_id/version/hash`, `active_gate_id`, `active_gate_renderer`, `family_state`, `agent_family_custom_role`). Not user-facing CLI, but needed for an "under the hood" manual section.

### I. Custom-role display labels (v2) — **UNDOCUMENTED**
- `Agent.custom_role_label` / `custom_role_done_label` (`src/sase/ace/tui/models/agent.py:273-274`) surface via display-only `Agent.display_status` (`agent.py:414-419`): shows `label` when semantic status is RUNNING, `done_label` when DONE. Buckets/colors/actions key off the unchanged semantic status. Not mentioned in `docs/ace.md`.

### J. Agent-initiated launches: `LaunchApproval` + `/sase_run` (v2) — **UNDOCUMENTED**
- **Gating rule:** when a *running agent* (`SASE_AGENT` set) invokes `sase run`, it is diverted to a `LaunchApproval` request instead of spawning (`src/sase/main/query_handler/_launch.py`). User-typed surfaces (including user-typed `%n`) stay ungated.
- **CLI** (`src/sase/main/parser_launch.py`): 
  - `sase launch request [PAYLOAD | @PATH] [-p/--prompt] [-r/--reason] [-a/--approval required] [-f/--file PATH] [-m/--max-slots N] [-o/--output text|json] [-s/--source LABEL]` (`parser_launch.py:47-101`).
  - `sase launch approve <selector>` (`parser_launch.py:22-30`).
  - `sase launch reject <selector> [-f/--feedback FEEDBACK]` (`parser_launch.py:32-45`). `<selector>` = request id, notification id, or unique notification prefix.
- **Request JSON schema (version 1):** `schema_version: 1`, `prompt` (required), `reason` (optional), `approval: "required"` (only value accepted — no auto-approve), `max_slots` (default 1), optional `family_type`. Files land in `~/.sase/launch_requests/<request_id>/` (`launch-<uuid>`): `launch_request.json` + `launch_preview.md`.
- **Resolution:** TUI `LaunchApprovalModal` (`a` approve / `r` reject / `q`|esc cancel; `src/sase/ace/tui/modals/launch_approval_modal.py`); `launch_response.json` is write-once; on approve the request is revalidated and re-dispatched (`dispatch_status: "launched"`, `launched_count`).
- **Shipped guidance:** the generated skill `src/sase/xprompts/skills/sase_run.md` (deployed via `sase skill init`) — I read it; it teaches the request JSON, `sase launch request -f launch_request.json -o json`, embedding `%n(parent, suffix)` in the requested prompt, and polling `response_file`. `docs/cli.md` has **no** `sase launch` entry at all (confirmed: zero matches).

### K. The `run` (remote Approve) plan-archive behavior change (v2) — **UNDOCUMENTED**
- The `run` choice (Telegram/mobile "Approve"/"Run") now archives the plan into `sdd/tales/YYYYMM/` like interactive Approve (`src/sase/plan_approval_choices.py`, `approval_choice_archives_plan`). Worth a changelog/manual callout.

## Task 3 summary — coverage matrix

| Feature | Documented? | Location / gap |
|---|---|---|
| `%n(parent, suffix)` / `@` attach | Yes | `docs/xprompt.md:1028-1031, 1090-1108` |
| Queueing / WAITING child rows | Yes | `docs/xprompt.md:1100-1104` |
| `#with_feedback` / `#with_q_and_a` | Yes | `docs/xprompt.md:868-895` |
| Glossary `--` vs `.` note | Proposed only | `docs/xprompt.md:897-900` |
| `kind: agent_family` YAML schema + discovery | **No** | — |
| `sase plan approve --with/--without` | **No** | `docs/cli.md:89` shows only `--kind` |
| "Also run" TUI member toggles | **No** | `docs/ace.md:1572` covers `c` but not toggles |
| `agent_family.plan_approval.default_members` | **No** | absent from `docs/configuration.md` |
| `sase launch request/approve/reject` + LaunchApproval | **No** | no `sase launch` entry in `docs/cli.md` |
| Custom-role display labels | **No** | absent from `docs/ace.md` |
| `role_completed` / evaluator (under the hood) | **No** | — |
| `run`-choice archive behavior change | **No** | — |

## Task 4 — Recommendation

**Create a new page: `docs/agent_families.md`.** Justification:
- The undocumented surface is large and cross-cutting (a YAML config format, a config key, two new CLI command groups, TUI modals, an agent-facing skill, and an architecture story). Scattering it across `xprompt.md` / `cli.md` / `configuration.md` / `ace.md` would fragment a coherent feature and bury it.
- There is a ready-made structure and an infographic in `sdd/research/202607/`. The research note's §4 (recipes) and §5/§6 map almost 1:1 onto page sections.
- No `docs/agent_families.md` exists today and "family/dynamic/launch approval" appear nowhere in `mkdocs.yml` nav (confirmed).

**Suggested page outline** (from the research note §5): (a) concept — families, roles, static chain vs dynamic extension; (b) extending by hand (`%n`, follow-up xprompts, queueing) — can largely cross-link to `docs/xprompt.md`; (c) custom lifecycle roles (`kind: agent_family` YAML how-to + the two flagship examples + discovery precedence); (d) choosing members at the plan gate (TUI toggles / `--with`/`--without` / `default_members` config / remote / `%auto`); (e) agent-initiated launches (`/sase_run` + `sase launch`); (f) reference tables (grammar, YAML fields, choice registry, error messages); (g) under the hood.

**Plus targeted additions to existing pages** (so reference readers find them in context, each cross-linking to the new page):
- `docs/cli.md` — add a `sase launch request/approve/reject` command group, and add `--with`/`--without`/`-m`/`-p` to the `sase plan approve` row.
- `docs/configuration.md` — add an `agent_family.plan_approval.default_members` config section.
- `docs/ace.md` — note the "Also run" member toggles in the `c` custom-approval modal, the `LaunchApprovalModal`, and custom-role display labels.

**mkdocs.yml nav placement:** add under **"Beyond the Basics"** (which already groups Workflows, Workspaces, Mentors), e.g. immediately after `Workflows: workflow_spec.md`:

```yaml
  - Beyond the Basics:
      - Architecture: architecture.md
      - ChangeSpecs: change_spec.md
      - Beads: beads.md
      - Workflows: workflow_spec.md
      - Agent Families: agent_families.md      # <-- new
      - Workspaces: workspace.md
      - Mentors: mentors.md
```
An acceptable alternative is **"The Basics"** right after `XPrompts: xprompt.md`, since `%n` and the follow-up xprompts are xprompt directives — but the v2 weight (config, CLI, approvals) makes "Beyond the Basics" the better fit. Note `mkdocs.yml` has `strict: true`, so the nav entry and file must both exist or the build fails.

This research note is essentially a ready-made manual. Let me check the existing doc style before drafting the new `docs/agent_families.md` page.

The docs look surprisingly current. Let me dig for genuine discrepancies. Let me read the rest of llms.md (role aliases + temporary overrides), check git status, and investigate the `<provider>_coder` fallback behavior which looks potentially mismatched.

I have the style and the source material. Let me quickly verify the key CLI surfaces directly (the venv is installed) before writing them into the new page.

Let me verify the skills `--check` mode behavior for precise fix facts, and confirm `sase launch` and `sase agent index` doc status.

Let me verify the `<provider>_coder` fallback semantics by reading the alias resolution tests, which will settle whether it routes through `@coder`.

That help output doesn't match the source — likely the wrong `sase` on PATH. Let me use the venv binary explicitly.

I have gathered all the evidence needed. Here is my audit report.

---

# Audit: docs/ace.md vs. recent TUI changes

Repo: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_10`. All doc paths are `docs/ace.md` unless noted. Ordered by severity.

## WRONG STATEMENTS (contradict current behavior)

### 1. Tab order is stale everywhere (commit 2404af6d2, BREAKING) — HIGH
Source of truth: `src/sase/ace/tui/tab_order.py:16` — `TAB_ORDER = ("agents", "changespecs", "axe")`. The visible top-bar renders `Agents | PRs | AXE`, and `Tab`/`Shift+Tab` cycle `agents → changespecs → axe → agents`. The doc still lists PRs first in multiple places:

- `docs/ace.md:49-55` — "Tab System" table lists rows in order **PRs, Agents, Axe**. Should be **Agents, PRs, Axe**. The intro at line 49 ("cycled with `Tab` and `Shift+Tab`") makes the table double as the cycle-order claim, so this is factually wrong now.
- `docs/ace.md:884` — Global keybindings row: "Switch between **PRs, Agents, and Axe** tabs". Should read "Agents, PRs, and Axe".
- `docs/ace.md:1202` — Tab Bar Display: "The tab bar renders plain tab labels (`PRs`, `Agents`, `AXE`)." Should be (`Agents`, `PRs`, `AXE`).
- `docs/ace.md:1162` — Jump All Modal: "displays all entries across **PRs, Agents, and Axe** tabs".
- `docs/ace.md:1174` — Jump All Modal: "The modal groups entries by tab (**PRs, Agents, Axe**)".
- `docs/ace.md:924` — Command Palette title-bar badge listed as "(`PRs`, `Agents`, or `AXE`)" — order should lead with Agents (minor).
- `docs/ace.md:29` — `-t/--tab` choices listed `changespecs, agents, axe` (cosmetic; the stated default `agents` is still correct per the commit).

Fix facts: visible/cycle order is `Agents, PRs, AXE` (internal names `agents, changespecs, axe`); startup default tab remains `agents`. Consider also reordering the doc's own section blocks ("Keybindings: PRs Tab" at line 57 currently precedes "Keybindings: Agents Tab" at line 269) for consistency — cosmetic, not a factual error.

Corroborating: commit 282fc6ccf fixed the same PRs-first ordering bug in the in-app onboarding "Know where you are" card, confirming the intended visible order is Agents → PRs → AXE.

### 2. Agents info strip no longer prints the "Agents" label (commit 937278ecb) — MEDIUM
- `docs/ace.md:550` states the metric strip renders "in the form `N Agents [S stopped · R running · W waiting · F failed · U unread · D done]`".
- Actual: the " Agents" label was dropped from the non-loading render path. `src/sase/ace/tui/widgets/agent_info_panel.py:308` appends only the numeric count (`self._visible_agent_count`), then `_append_metric_strip` (lines 274-287) opens with `" ["`. The word "Agents" now appears only in the loading short-circuit as `Agents: …` (line 304-306). So the strip renders e.g. `1 [1 running] …`, not `1 Agents [...]`.
- Fix: change the documented form to `N [S stopped · R running · W waiting · F failed · U unread · D done]` (the loading text `Agents: …` on line 554 is still correct). Note also (commit 97f34fa98) the leading count `N` is now the STARTING-inclusive top-level total (`AgentPanelIndex.top_level_total`), not the rendered/selectable row count — worth a clarifying phrase.

## GAPS (missing coverage of new behavior)

### 3. Tab guide modal is undocumented (commits bde21558c, 3767e7ff7) — MEDIUM
A new leader-mode contextual tab guide exists but appears nowhere in ace.md (no match for "tab guide", "guide modal", or the chord).
- Binding: leader `,?` — `src/sase/default_config.yml:205` `tab_guide: "question_mark"` under `leader_mode.keys`; dispatch at `src/sase/ace/tui/actions/agent_workflow/_leader_mode.py:71-73`; helper docstring at line 265 ("Open the current tab's guide (leader `,?` by default)"); modal `src/sase/ace/tui/modals/tab_guide_modal.py`.
- Behavior: opens a per-tab guide (PRs / Agents / AXE) surfaced in footer/help discovery, onboarding copy, and the AXE info panel; onboarding cards now also carry "learn more" doc-links (3767e7ff7).
- Fix: add `,?` "Open tab guide" to the leader-mode tables (PRs `docs/ace.md:202-217`, Agents `659-677`, Axe `819-828`) — it is a global leader command — and/or the Global Keybindings table (882-895).

### 4. Slow tool calls in agent metadata header are undocumented (commits 453641903, 5f29a7fdd, 2bde0b594) — MEDIUM
The "Agents Tab Metadata Panel" section (`docs/ace.md:1422-1459`) enumerates the panel's sections (Agent details, Wait state, OUTPUT VARIABLES, AGENT REPLY, WORKFLOW VARIABLES, PROMPT) but omits the new slow-tool-calls block now rendered in the agent detail metadata header.
- Evidence: `src/sase/ace/tui/widgets/prompt_panel/_agent_display_header_summary.py:112-139` (`supports_slow_tool_sources` / `build_slow_tool_sources`), selection/formatting in `src/sase/ace/tui/tools/slow.py` (threshold `SLOW_TOOL_CALL_THRESHOLD_MS`), root/child source scoping in `src/sase/ace/tui/tools/sources.py`.
- Fix: document that slow tool calls (calls exceeding the slow threshold) are surfaced in the metadata header, ordered by start time (5f29a7fdd), aggregated across a root agent's children while preserving child source attribution (2bde0b594).

### 5. No onboarding / empty-state coverage at all (commits 5ab9907f2, 9e77bd393, 1b9395b05, 282fc6ccf, f7832045b) — MEDIUM
ace.md has zero "onboarding" content (no matches). Missing surfaces:
- PRs-tab first-use onboarding empty state when there are no ChangeSpecs and no saved queries (5ab9907f2).
- Agents-tab onboarding: Admin Center plugin recommendation when no third-party plugins are installed (9e77bd393); `+` launch-hint gated on launch-target availability (1b9395b05); empty-state gated on filtered *visible* rows (f7832045b).
- Fix: add a short "Onboarding / empty states" section covering both PRs and Agents empty states.

### 6. Vim editing in modal inputs is under-documented (commits 085054e32, 1c21d266a) — LOW
`docs/ace.md:382` documents only readline keybindings for the WaitModal. The broader adoption of `VimTextArea` / `SingleLineVimTextArea` across ACE modal inputs (agent name, agent tag, query edit, rename CL, save-agent-group, command input, custom model, xprompt name, etc.) and the Admin Center config-edit inputs is not documented. Low severity for ace.md; the config-edit modal specifics (multiline expansion f56f137fc, capped previews 46f5f4c05, richer navigation 2e38f97a8) belong to configuration.md's Config-tab section, which ace.md does not cover.

## VERIFIED CURRENT — no doc change needed (called out because the task asked)

- **Idle/activity tracking removed (a39f52401):** commit already edited `docs/ace.md` (28 lines). No stale references remain — the surviving "idle/inactive/activity" matches (lines 450, 624, 770, 946-975, etc.) are unrelated legitimate uses (PDF progress, approval-gap wording, AXE idle marker, project lifecycle filters).
- **Repo-key / sibling_repos migration UI removed (b453ab7e5):** no stale reference in ace.md. The `linked_repos`/`sibling_repos` mentions (lines 356, 690) are agent-metadata behavior, not the removed Config Center migration action. (ace.md has no Config-tab editing section, so nothing to fix here.)
- **Plugin update keybindings reworked (c095d438d):** already correct. `docs/ace.md:2164-2165` and `docs/configuration.md:119-120` both document `u` = comprehensive SASE update, `U` = update selected plugin. No stale `S` or update-all references. Note: `src/sase/default_config.yml:226` `update_sase: "U"` is the *leader* `,U` binding (documented at ace.md:212/670), unrelated to the Plugins-tab keys.
- **PID → version in TUI title (9deb01206):** ace.md never documented a "PID" title, so no contradiction. The only "PID" mentions (lines 791, 793-794) are AXE lumberjack/chop PIDs and remain correct. Optional enhancement only: no title-format section exists to update.
- **Agent neighbor `~` includes ancestors (4ffd1f144):** already reflected — `docs/ace.md:281` and `291-295` explicitly say `~` jumps among "ancestors, descendants, and neighbors".
- **Tools panel test split (1caf496db):** the Tools panel itself is documented at `docs/ace.md:1461-1498`. No doc impact (tests only).
- **Updates badge moved left of model indicator (afb7b7414):** ace.md does not assert a precise top-bar indicator order, so no contradiction (potential minor addition only).
- **STARTING in headline total (97f34fa98) / concise wait countdown (1261bfeae):** no contradicting statement in ace.md; adequately covered by existing wait/countdown wording (lines 1437-1440). See finding #2 for the one nuance worth adding.

I have all the evidence needed. Here is my audit report.

---

# Documentation Accuracy Audit — install/update/plugin/dev docs

Scope audited: `README.md`, `INSTALL.md`, `docs/development.md`, `docs/plugins.md`, `docs/rust_backend.md`. Findings ordered by severity. Nothing was edited.

## Source ground truth (verified from code)

**Install mode switching** (commits `5131ec849`, `672c3cea8`):
- Two install modes: **PyPI (managed)** = published wheels via `uv tool install` (normal path); **Dev (editable)** = editable git checkouts + locally-built `sase-core-rs`. Detected mode may also be **mixed** (`src/sase/mode_switch/models.py:8-10, 99-110`).
- CLI: `sase update -t/--to dev|pypi`, with `-n/--dry-run` preview and `-y/--yes` to skip the confirmation prompt (`src/sase/main/parser_update.py:61-72`, `src/sase/main/update_handler.py:133-151, 227-232`). Without `-y` an interactive confirm is required; cancel exits non-zero.
- A changed switch restarts axe (and ACE+axe when driven from the TUI) via the shared restart path, with restart-toast support (`update_handler.py:244-248`).
- TUI: the Updates tab binds **`m` = "Switch mode"** (`src/sase/ace/tui/modals/plugins_browser_pane.py:159`), showing current mode/dev_root, a confirm modal, background execution, restart toast (`plugins_browser_mode_switch.py`).
- Config key **`update.dev_root`**, default `~/projects/github` (`src/sase/default_config.yml:13-14`, `src/sase/mode_switch/repos.py:14`). Dev checkouts materialize owner-nested at `<dev_root>/<owner>/<repo>` — e.g. `~/projects/github/sase-org/sase` (host) and `~/projects/github/sase-org/sase-core` (for `sase-core-rs`) — cloned via SSH URLs (`repos.py:27-33, 85-101`). The legacy flat layout `~/projects/git/<repo>` is now only detected in order to warn (`repos.py:15`, `plan.py:390-402`).
- `672c3cea8` is a **BREAKING** change: flat `~/projects/git/<repo>` → owner-nested `~/projects/github/<owner>/<repo>`.

---

## Finding 1 — HIGH: Install mode switching is entirely undocumented (whole feature missing)

`sase update -t/--to dev|pypi` and the Updates-tab `m` "Switch mode" action appear in **no** doc (confirmed by grep across all of `docs/`, `README.md`, `INSTALL.md`).

- **README.md:111** — "Common commands" lists `sase update -n` only. Missing the mode-switch flag.
- **README.md:136-140** — "Update workflow" bullet documents Updates-tab keys `u`/`U` but omits the new `m` "Switch mode" key and the whole managed↔dev concept.
- **INSTALL.md:86-97** — Updates-tab bullets list `u`, `U`, `r`, `o` but not `m` (Switch mode).
- **INSTALL.md:101-105** — "CLI equivalent" block lists `sase update`, `sase update -n`, `sase plugin update -a`; missing `sase update --to dev|pypi`.
- **docs/plugins.md:168-173** — `sase update` flag list documents `-n/-q/-j`; missing `-t/--to`.
- **docs/plugins.md:219-237** — "Dev / editable installs" describes *updating an already-existing* editable checkout and even says dev state is set up manually via `uv tool install -e` (line 221-222). It never mentions that `sase update --to dev` now establishes that state for you (clone/fast-forward + editable reinstall + Rust rebuild), nor `--to pypi` to return to managed.

**Facts to add:** document `sase update -t/--to dev|pypi` (`-n` preview, `-y` skip confirm, non-op when already in the target mode, axe/ACE restart on change) and the Updates-tab `m` "Switch mode" action, in README update bullet, INSTALL "Keeping SASE up to date", and plugins.md "Updating sase and plugins" / "Dev / editable installs".

## Finding 2 — MEDIUM: `update.dev_root` config + owner-nested dev-checkout layout undocumented, and a BREAKING layout change has no migration note

The `update.dev_root` config key and the `~/projects/github/<owner>/<repo>` layout are documented nowhere in the audited docs. The `672c3cea8` BREAKING change (flat `~/projects/git/<repo>` → owner-nested) has no user-facing note anywhere.

- No mention of `update.dev_root` in `docs/plugins.md`, `INSTALL.md`, `README.md`, or `docs/development.md`.
- Note (not a bug): `docs/project_spec.md:103-108` and `docs/xprompt.md:335` reference `~/projects/github/<owner>/<repo>`, but only as the **GitHub workspace-provider `WORKSPACE_DIR`** convention — unrelated to mode-switch and not stale.

**Facts to add:** document `update.dev_root` (default `~/projects/github`), the owner-nested `<dev_root>/<owner>/<repo>` checkout location, SSH clone URLs, and a migration note for users with legacy `~/projects/git/<repo>` checkouts (they are warned about, not reused — set `update.dev_root` or move the tree). Best placed in plugins.md "Dev / editable installs" and/or `docs/configuration.md`.

## Finding 3 — MEDIUM: Restart-after-plugin-change (commit `6910d1842`) not documented for `sase plugin install/update/uninstall`

`docs/plugins.md` documents automatic restart only for `sase update` (lines 203-205, 232). Since `6910d1842`, `sase plugin install`, `update`, and `uninstall` also write restart receipts, restart AXE from the CLI when uv changes installed packages, and show operation-specific post-restart toasts in ACE.

- **docs/plugins.md:239-300** ("Installing and updating plugins" and "Removing a plugin") — no mention of the new restart-on-package-change behavior or the restart status in JSON output.
- **INSTALL.md:53-54** — says only that "the plugin's entry points are discovered on the next `sase` run"; omits the new automatic axe restart / post-restart toast.

**Facts to add:** note that `sase plugin install/update/uninstall` restart axe (CLI) and surface a post-restart toast (ACE) when uv actually changes packages, and that the JSON payload now carries the shared restart status shape.

## Finding 4 — LOW: `u`/`U` plugin-update keybindings are CORRECT (no fix)

Task-3 verification. Current bindings in `src/sase/ace/tui/modals/plugins_browser_pane.py:160-161`: `("u", "update_sase", …)` = comprehensive SASE update; `("U", "update", …)` = highlighted plugin. This matches the `c095d438d` rework and is correctly reflected in **README.md:139**, **INSTALL.md:90-92**, and **docs/plugins.md:206-207**. No stale `S` (SASE update) or `U` (update-all) references remain in any doc. Accurate — the only gap is that these sections omit the newer `m` key (covered by Finding 1).

## Finding 5 — LOW: `sase-core-rs` version requirement is CORRECT in the two named docs (no fix); stale pin only in non-prose image artifacts

Task-4 verification. `pyproject.toml:48` pins `sase-core-rs>=0.3.2,<0.4.0` (consistent with commit `5474f4491`).

- **docs/rust_backend.md:6** — defers to pyproject ("see `pyproject.toml` for the pinned range"), no hardcoded number → accurate.
- **docs/development.md** — states no version → accurate.

Aside (outside the 5-file scope): the infographic build artifacts `docs/images/rust-backend-boundary-infographic.critique.md:104,155`, `…prompt.md:59`, and `docs/images/sase-rust-core-integration.critique.md:95` still cite the old pin `sase-core-rs>=0.1.1,<0.2.0`. These are image-generation notes, not user-facing prose, but they are stale versus the current `>=0.3.2,<0.4.0` if that infographic is ever regenerated.

---

### Summary table

| # | Severity | Doc + line | Issue |
|---|----------|-----------|-------|
| 1 | HIGH | README.md:111,136-140; INSTALL.md:86-97,101-105; plugins.md:168-173,219-237 | Install mode switching (`sase update --to dev|pypi`, Updates-tab `m`) entirely undocumented |
| 2 | MEDIUM | plugins.md:219-237 (and configuration.md); no note anywhere | `update.dev_root` + owner-nested `~/projects/github/<owner>/<repo>` layout undocumented; BREAKING flat→nested migration has no note |
| 3 | MEDIUM | plugins.md:239-300; INSTALL.md:53-54 | Restart-after-plugin-change (`sase plugin install/update/uninstall`) not documented |
| 4 | LOW | README.md:139; INSTALL.md:90-92; plugins.md:206-207 | `u`/`U` keybindings correct — no fix (but omit new `m`) |
| 5 | LOW | rust_backend.md:6; development.md | Version pin accurate in named docs; stale `0.1.1` only in `docs/images/*.critique.md`/`*.prompt.md` |

The `<provider>_coder` fallback test only covers the case where `coder` is unconfigured, so it doesn't actually exercise the intermediate `@coder` hop the docstring claims. Let me verify a few remaining facts: the doctor check IDs, and the `%m` short directive.

I have completed the audit. Here is the structured report.

---

# Documentation Accuracy Audit

## 1. docs/init.md — skills check mode (4a23371ec) + outside-VCS skip (08ef0f246)

**New CLI surface determined:** There is no `--check-skills` flag on `sase init`. Instead, `sase skill init` (and its alias `sase init skills`) gained a scoped `-c/--check` read-only drift-check mode, distinct from the pre-existing `-n/--dry-run`. Evidence: `src/sase/main/parser_init.py:10-16` (`-c/--check`, help "Report generated skill-file drift without writing files") and `src/sase/main/init_skills_handler.py:568-572` (routes `check` to the shared `run_init_check`).

**Finding 1a — MISSING flag (skill init --check).** docs/init.md never documents `sase skill init --check` / `-c`.
- The Commands table (docs/init.md:76-84) lists `sase skill init --dry-run` (line 79), `--force` (80), `-p <provider>` (81), but has no `sase skill init --check` / `-c` row.
- The example blocks (docs/init.md:35-38 and 234-238) show `sase skill init --dry-run` but not `--check`.
- Fix: add a row/example for `sase skill init -c, --check` = "Report generated skill-file drift without writing files" (read-only, same shared check path as memory/SDD).

**Finding 1b — STALE/incomplete claim.** docs/init.md:87-88 states: "Scoped `--check` flags also live on explicit subcommands when you want to validate only memory or only SDD generated files." This is now inaccurate — skills also has a scoped `--check`. Fix: change "only memory or only SDD" to "memory, SDD, or skills".

**Finding 1c — provider surface (no doc error, note only).** The commit changed `-p/--provider` from a fixed enum to runtime validation against registered providers (`parser_init.py:47-52`, now `metavar="PROVIDER"`, help "Only deploy for a registered provider"). docs/init.md:81 already says `-p <provider>` generically, so no fix needed.

**Finding 1d — undocumented behavior (08ef0f246, minor).** Bare `sase init` now skips SDD/project-scoped setup and runs memory init in home-only mode when the current dir is not inside a version-controlled project. docs/init.md (intro lines 3-19) does not mention this outside-VCS behavior. This is behavior-only (no new flag); optional to add.

## 2. docs/beads.md — `sase bead list` limit + closed fallback (4d3264c36, b9266887d)

**New behavior determined** (`src/sase/main/parser_bead.py:88-97`): `sase bead list` gained `-n/--limit` (help: "Maximum beads to print; closed listings default to 20, 0 means unlimited"). When the default open/in-progress query is empty and no explicit `--status` was given, it falls back to closed beads; whenever the final scope includes closed and `--limit` is omitted, only the newest 20 print; `--limit 0` = unlimited; open/in-progress default stays unlimited.

**Finding 2a — MISSING flag.** docs/beads.md `sase bead list` flag table (lines 179-183) omits `-n, --limit`. (Inconsistent: the `sase bead search` table at lines 204-211 already documents `-n, --limit`.) Fix: add `-n, --limit` row.

**Finding 2b — MISSING behavior.** docs/beads.md:176-177 only says "Without `--status`, the command lists `open` and `in_progress` issues; pass `--status=closed` when you need closed history." It should additionally describe: (1) the implicit closed fallback when open/in-progress is empty and no explicit status filter; (2) the newest-20 default cap whenever the status scope includes closed and `--limit` is omitted; (3) `--limit 0` = unlimited, `--limit N` = slice to N, open/in-progress default remains unlimited.

**Finding 2c — minor.** Quick Start comment (docs/beads.md:36) "# List open and in-progress issues" is now incomplete (can fall back to closed). Optional.

## 3. docs/cli.md — command inventory

**Maintenance model:** cli.md is hand-written (self-described "command index" at line 3), not generated.

**Finding 3a — MISSING top-level command: `sase launch`.** The `sase launch` group (registered `src/sase/main/parser.py:420`; defined `src/sase/main/parser_launch.py`) resolves pending LaunchApproval requests and has three subcommands:
- `sase launch approve <selector>` (parser_launch.py:22-30)
- `sase launch reject <selector> [-f/--feedback]` (parser_launch.py:32-45)
- `sase launch request <payload> [...]` — creates a LaunchApproval request, previewed/registered but no agent spawned until approved (parser_launch.py:47-101)

`git grep "sase launch" docs/ README.md` returns nothing — it is entirely undocumented. This is the "plan approvals" surface the task flagged. Fix: add to cli.md, best under "Work Tracking And Planning" near `sase plan` (lines 88-93).

**Verified present (no gaps):** All other 41 registered top-level parsers appear in cli.md, including the recent additions the task called out — `sase agent index` (cli.md:20), all `sase workspace` subcommands incl. `migrate` (224-229), and `sase plan approve/propose/reject/search` (88-92). No removed/phantom commands: every command listed in cli.md maps to a live parser. (cli.md is a subcommand-level index, so flag-level omissions like `skill init --check` are out of its scope.)

## 4. docs/index.md + mkdocs.yml nav — CLEAN

- All 33 top-level `docs/*.md` pages are present in the mkdocs.yml nav.
- Every nav entry exists on disk (spot of note: `troubleshooting/agent-revival.md`, `series/agentic-software-engineering.md`, `blog/index.md`, `blog/posts/why-coding-agents-need-orchestration.md`, `blog/posts/hello-sase-your-first-15-minutes.md` — all exist).
- The 8 blog posts under `docs/blog/posts/` not explicitly in nav (axe-background-daemon, beads-and-sdd, changespecs-in-practice, commit-workflows-plugins, prompt-widget-and-nvim, telegram-mobile-agents, whats-next-memory-mobile-web, xprompts-in-depth) are managed by the mkdocs `blog` plugin (mkdocs.yml:98-101), so they are not orphans.
- No missing-on-disk nav entries, no orphaned top-level pages. No action.

## 5. docs/xprompt.md + removed packaged research xprompts (bc6a9cc87)

**Finding 5a — STALE reference (in docs/sdd.md, not xprompt.md).** docs/sdd.md:114: "The built-in `#research` xprompt tells the agent to create a new markdown file in the current month directory". Commit bc6a9cc87 (BREAKING) removed `#research`, `#research/image`, `#research/more`, `#research/prompt`, `#research_swarm`, and `#old_research_swarm` as packaged defaults ("no longer package defaults. Define them in user or project config when needed"). Calling `#research` "built-in" is now inaccurate. Fix: drop "built-in" and note `#research` must now be user/project-defined (or reword the sentence).

**Verified clean:**
- docs/xprompt.md itself has no stale research references — bc6a9cc87 already updated it (`git grep` for research names returns no xprompt.md hits).
- docs/blog/posts/why-coding-agents-need-orchestration.md:207 ("Research swarms, because they need fan-out…") is generic prose, not a reference to the removed `#research_swarm` xprompt. Acceptable, no fix.
- The other two xprompt commits are behavior/code only: d698779c6 (diagnostics) already shipped its own docs/xprompt.md addition; d1bc30f9c (completion-space fix) has no doc surface.

## 6. Stale references to removed features — ALL CLEAN

- **idle** (removal a39f52401): docs/ace.md:450 ("looking idle"), :624 ("idle approval gap"), :770 ("running/error/idle marker" for lumberjacks) are all unrelated legitimate prose, not the removed ACE idle activity-tracking feature (that commit already updated ace.md). No fix.
- **sibling_repos**: README.md:170, docs/configuration.md:81/482/521, docs/init.md:140 — every occurrence describes it as a deprecated/legacy alias for `linked_repos`. Correct. No fix.
- **repo-key / repo key** (migration UI removal b453ab7e5): `git grep` returns no matches in docs/ or README.md. No stale references. No fix.

---

### Summary of actionable fixes
| # | File:line | Issue |
|---|-----------|-------|
| 1a | docs/init.md:76-84, 35-38 | Add undocumented `sase skill init -c/--check` drift-check mode |
| 1b | docs/init.md:87-88 | "only memory or only SDD" → include skills (scoped `--check` now exists on skills) |
| 1d | docs/init.md:3-19 | (Optional) note outside-VCS-dir skip behavior |
| 2a | docs/beads.md:179-183 | Add `-n, --limit` to `sase bead list` flag table |
| 2b | docs/beads.md:176-177 | Document implicit closed fallback + newest-20 default cap + `--limit 0` unlimited |
| 3a | docs/cli.md (~88-93) | Add missing `sase launch approve/reject/request` command group |
| 5a | docs/sdd.md:114 | `#research` is no longer "built-in"/packaged; reword to user/project-defined |

Areas 4 (nav) and 6 (idle/sibling_repos/repo-key) require no changes.

Let me do a final sweep across all docs for any lingering pre-migration config descriptions and verify the completion menu terminology.

I now have a comprehensive picture. Let me do one final verification of the two provenance/edit-path helpers to nail down the Reset behavior citation.

Now let me add the `,?` tab-guide binding to the leader-mode tables:

Now the metadata-panel section (slow tool calls) and the plan-approval modal section (agent-family member toggles):

I have completed a thorough audit. Here are my findings.

---

# Model-Alias Docs Audit (sase-5d / sase-5e)

## Important premise correction (read first)

The task states the epics "landed 2026-06-30 without touching docs/." That is **not accurate for the current tree**. The feature commits (`4d1a4b71f`, `829b43d25`, `9f933053e`, `df160e361`, `aebfbf247`, `c1cd66291`) indeed skipped docs, but the epics each shipped a **docs commit** that *is* an ancestor of HEAD (`master` @ `75e4470f2`):

- `a27b4572e` — `docs(llm_provider): align docs and shipped config with role-alias model (sase-5d.5)`
- `37b8257d2` — `docs(ace): document unified Models panel and per-alias overrides (sase-5e.5)`

And the two commits the task calls "earlier" are actually **later** (2026-07-03, after the 06-30 epics) and also updated docs:

- `72c62642a` — `feat: Add support for custom model aliases` (docs/ace.md, configuration.md, llms.md)
- `8b0ff2c9f` — `feat!: unify model alias config` (docs/ace.md, beads.md, configuration.md, llms.md, xprompt.md)

Net effect: `docs/llms.md`, `docs/configuration.md`, and `docs/ace.md` are **largely current and correct** for the post-migration alias system. The working tree is clean. There is **no lingering pre-`829b43d25` config presented as current** — the flat `model_aliases`, `custom_model_aliases`, `worker_models`, `default_model`, `@worker`, `@other` are referenced only inside correctly-framed migration/removal notes (llms.md:655-658, :818-819; configuration.md:388-390). So the doc author should treat this as a **light touch-up**, not a rewrite.

Below are the genuine discrepancies/gaps I found, ranked.

---

## D1 — WRONG (substantive): `@<provider>_coder` fallback chain is misdescribed

**Docs say:**
- `docs/llms.md:638` (implicit-role table): `| @<provider>_coder | ... | @coder |` — i.e. fallback is `@coder`.
- `docs/llms.md:795`: "…use `@<provider>_coder` for the planner's provider (for example `@claude_coder`), **falling back to `@coder` and then `@default`**."
- `docs/configuration.md:382` implies the same chain ("`@coder` and the per-provider `@<provider>_coder`").

**What the code actually does:** an unconfigured `<provider>_coder` alias falls back **directly to `@default`**, *not* through `@coder`. Evidence in `src/sase/llm_provider/config.py`:
- `_ROLE_ALIAS_FALLBACKS` (lines 60-65) maps `"coder" -> "@default"`.
- In `resolve_model_alias` (lines 482-490):
  ```python
  fallback = _ROLE_ALIAS_FALLBACKS.get(bare)          # "claude_coder" -> None
  if fallback is None and _is_provider_coder_alias(bare):
      fallback = _ROLE_ALIAS_FALLBACKS[CODER_MODEL_ALIAS_NAME]  # == "@default"
  ...
  current = fallback                                   # jumps straight to @default
  ```
  It assigns the *value* `"@default"`, not the name `"@coder"`, so the chain never revisits `coder`.

**Practical consequence:** if a user configures only `llm_provider.model_aliases.builtin.coder: X` (and not the provider-specific alias), then `@claude_coder` resolves to `@default`, **ignoring `X`**. To make a per-provider coder alias honor a shared coder target you must configure each `<provider>_coder` explicitly (or `builtin.default`).

**Caveat for the author:** the code's *own* docstrings also claim the two-hop chain (`config.py:43-44` "`<provider>_coder` falls back to this [coder]"; module comment lines 28-33), and the only test (`tests/llm_provider/test_config_aliases.py:237-251`, `test_provider_coder_alias_chains_to_coder`) only exercises the case where `coder` is unconfigured — so both routes coincidentally reach `@default` and the divergence is untested. This is therefore **likely a latent code bug, not just a doc error**. Confirm with engineering which is authoritative before rewording. If the docs are made to match today's code, the fix is: fallback column → `@default` (not `@coder`), and llms.md:795 → "falling back directly to `@default` (a configured `@coder` is only used if the per-provider alias references it)".

---

## D2 — STALE TERMINOLOGY: "reserved aliases" in the completion-menu description

- `docs/configuration.md:332`: "It lists inline-typable model names, **reserved aliases**, and configured model aliases…"

The term "reserved aliases" is pre-migration vocabulary. The current code calls these **implicit role aliases**, and explicitly notes the old reserved names were retired: `src/sase/xprompt/model_completion.py:33` ("the migration replacements for the retired reserved `@worker`/`@other`") and `:68`/`:195` ("The implicit role aliases (`@default`, `@coder`, …)"). Fix: replace "reserved aliases" with "implicit role aliases (`@default`, `@coder`, `@<provider>_coder`, `@epic_creator`, `@epic_lander`, `@phase_worker`)".

---

## D3 — IMPRECISE: Models-panel `Reset` "back to `@default`"

- `docs/ace.md:1058`: "Highlight an alias, `x` — clear its temporary override; `r` — **unset its configured value back to `@default`**."

`Reset` (`r`) issues `ConfigEditOp.unset()`, reverting to each alias's **implicit fallback**, which is *not* uniformly `@default`:
- For the `default` alias itself the fallback is the provider's requested-tier default, **not** `@default` (`config.py:393-414` `_resolve_default_alias_target`; state tag shows plain `implicit` vs `implicit → @default` in `models_panel_rendering.py:75-77`).
- For a **user/custom** alias, Reset **deletes the whole custom entry** (`models_panel.py:337-340` `reset_deletes_alias`; `models_panel_edit_helpers.py:80-89` `alias_reset_path`), it does not set it to `@default`.

Note ace.md is internally inconsistent: line 1010 ("unset the configured value back to its implicit fallback") and line 1047 ("reset by deleting the whole custom alias entry") are both correct; only the line-1058 example overreaches. Fix line 1058 to say "unset its configured value back to its implicit fallback" (matching line 1010).

---

## D4 — UNDOCUMENTED behavior: `Enter` on a Models-panel row = Override

The keybinding table at `docs/ace.md:1005-1011` lists `o/x/e/r` and `Esc`/`q`, but not `Enter`. In code, selecting a row (`Enter`) invokes Override: `src/sase/ace/tui/modals/models_panel.py:490-492` (`on_option_list_option_selected` → `action_override`). Also, the navigation keys `Ctrl+N`/`Ctrl+P` are documented (line 1003) — good — but `Enter` should be added as a synonym for `o`.

---

## D5 — INCOMPLETE: violet top-bar pill single-override format

- `docs/ace.md:1021`: "…surfaced by a distinct, concise **violet top-bar pill summarizing how many non-default overrides are active**."

That only describes the multi-override case. Per `src/sase/ace/tui/widgets/alias_overrides_indicator.py:82-91`:
- exactly one non-`default` override → `Override @<alias> <remaining>` (alias name + countdown), not a count;
- several → `Overrides ×N` (the count form);
- none → empty/zero-width.

Consider tightening the sentence to mention the single-override "`Override @<alias> <time-left>`" form. (This top-bar indicator is the `sase-5e.4` / `c1cd66291` feature; it *is* otherwise documented here, so this is a minor completeness nit, not a gap.)

---

## Areas confirmed ACCURATE / well-covered (do not touch)

For efficiency, these doc claims were checked against code and are correct as of HEAD:

- **Config shape** (`builtin` string-map vs `custom` `{model, description}` objects): `docs/llms.md:549-569`, `configuration.md:355-372`, `default_config.yml:287-313`, schema `src/sase/config/sase.schema.json:716-732`, and `config.py:165-214`. Custom wins collisions (`config.py:217-219`; llms.md:615). ✓
- **`@` is directive-only surface syntax; alias keys/values stay bare; `@alias` usable in `%model:`/`%m:` values (not free prompt text)**: llms.md:601-613. `%m` is a real alias for `%model` (`src/sase/xprompt/_directive_types.py:68 "m": "model"`); `%model` values resolve aliases via `model_alias_names()` (`src/sase/xprompt/_directive_values.py:301-303`). ✓
- **Implicit role aliases set** (`default`, `coder`, `<provider>_coder`, `epic_creator`, `epic_lander`, `phase_worker`): llms.md:628-641 vs `config.py:40-85, 299-346`. ✓ (only the `<provider>_coder` *fallback target* is wrong — see D1).
- **`@default` semantics**: no-`%model` launch default; explicit `@default` ignores the `default` temporary override: llms.md:837, :853, ace.md:1025 vs `config.py:434-438,479-480` and `temporary_override.py:436-458`. ✓
- **Per-alias temporary overrides — set/clear/persistence**: `~/.sase/llm_override.json`, versioned `{"version":2,"overrides":{...}}`, v1→v2 migration, atomic writes, self-cleaning, "until cleared" = no-expiry-but-still-temporary: llms.md:821-938, ace.md:1013-1030 vs `temporary_override.py` (`_STATE_VERSION=2` line 43, schema/migration lines 169-199, `set_alias_override`/`clear_alias_override` lines 307-399, duration parsing lines 75-105). ✓ The public-API table (llms.md:917-927) matches the actual function signatures. ✓
- **Models panel — open with `,m`, keys `o/x/e/r`, `j/k`/arrows/`Ctrl+N`/`Ctrl+P`, `Esc`/`q`; two-line description strip; kind badges `default/role/coder/user`; state tags `configured` / `implicit` / `implicit → @default` / `override · … left` / `override · until cleared`; sort order**: ace.md:987-1011, :993-997 vs `models_panel.py:94-107,135-143` and `models_panel_rendering.py:29-77`, `alias_view.py:93-109`. ✓
- **Persistent Edit + commit/push (Rust source-preserving edit, preview, chezmoi-aware commit/push)**: ace.md:1036-1047 vs `models_panel.py:306-486` and `models_panel_edit_helpers.py:43-88`. ✓
- **`sase doctor` alias checks**: both referenced check IDs exist — `config.model_aliases` (`src/sase/doctor/checks_config_model_aliases.py:268`, registered `checks_config.py:43`) covering all the cases llms.md:615-618 lists; and `config.model_xprompts` (`checks_config_xprompts.py:106`, registered `checks_config.py:49`) producing exactly the "does not resolve to a provider; it will fall back to the default provider" message quoted in llms.md:621-626. ✓
- **Removed-key migration notes** (`worker_models`, `default_model`, `custom_model_aliases`, `@worker`, `@other`, `~/.sase/llm_worker_override.json`): llms.md:655-658,:818-819, configuration.md:388-390 vs `checks_config_model_aliases.py:55-86` and `checks_config_common.py:12-13`. ✓

---

### One-line summary for the doc author
The alias docs are in good shape and current. Make one substantive fix (**D1**, after confirming code-vs-docs intent on the `<provider>_coder` → `@coder` vs `@default` fallback with engineering), one terminology swap (**D2**, "reserved aliases" → "implicit role aliases" in configuration.md:332), and three small precision/coverage touch-ups (**D3** ace.md:1058, **D4** add `Enter`=Override to ace.md:1005-1011, **D5** ace.md:1021 single-override pill text).

Now docs/plugins.md — install mode switching, `sase update --to`, and restart-after-plugin-change:

Now the init.md and beads.md fixes:

Now the nav entry, README, and index updates:

Now the remaining ace.md additions (onboarding/empty states, launch-approval modal), the xprompt.md glossary-note cleanup, and anchor verification:

All planned edits are in. Now let me validate: strict docs build first, then the repo's required checks.

Strict docs build passes. Now the required `just check` (per repo rules for file changes):

While that runs, let me check whether the repo enforces markdown formatting (my table column widths are uneven):

`just check` finished — but the exit code passed through `tail`, so let me verify the actual output:

Prettier wants the markdown reformatted. Running the auto-formatter, then re-checking:

Prettier normalized the tables. Re-running the full check:

These are my changes from this session's documentation review, so I'll commit them with the commit skill as instructed.

The status matches the files I edited this session. Writing the commit message and committing:

Committed and pushed. Commit `2b4d8e9ae` — `docs: refresh docs for recent features and add agent families page` — landed on `master`, the working tree is clean, and the branch is in sync with `origin/master` (the `sase commit` workflow pushed it). All 12 files from the finalizer list were staged explicitly, including the new untracked `docs/agent_families.md`.

Recap of what the documentation review produced (487 insertions, 108 deletions):

- **New page `docs/agent_families.md`** (266 lines, added to the mkdocs nav under "Beyond the Basics") covering the full dynamic agent families feature: `%n(parent, suffix)` extension, `#with_feedback`/`#with_q_and_a`, custom `kind: agent_family` YAML roles, plan-gate member selection, sticky `default_members` config, and agent-initiated launches via LaunchApproval.
- **Accuracy fixes** — corrected the stale PRs-first tab order throughout `docs/ace.md` (now Agents/PRs/AXE), the agents info-strip format, the Models panel Reset/pill/Enter details, the "reserved aliases" terminology, and the no-longer-packaged `#research` xprompt in `docs/sdd.md`.
- **Gap fills** — `sase launch` command group and `sase plan approve --with/--without` in `docs/cli.md`; install mode switching (`sase update --to dev|pypi`, Updates-tab `m`) plus `update.dev_root` and plugin-change restarts in `docs/plugins.md`/`INSTALL.md`/`README.md`; `sase skill init --check` in `docs/init.md`; `sase bead list --limit` and the closed-bead fallback in `docs/beads.md`; tab guide (`,?`), onboarding/empty states, and slow-tool-call metadata in `docs/ace.md`.

Everything was validated before committing: the strict MkDocs build passes, prettier formatting was applied, and `just check`'s static gates ran clean (the pre-commit `just fix` hook ran again during the commit).

One item I'd flag for follow-up rather than a doc fix: the documented `@<provider>_coder` → `@coder` → `@default` fallback chain doesn't match the code, which falls back directly to `@default`. Since the code's own docstrings claim the two-hop chain, that looks like a latent code bug rather than a doc error — I left `docs/llms.md` as-is pending your call on which behavior is intended.
