# Chat History - ace-run

- **TIMESTAMP:** 2026-07-07 12:22:21 EDT
- **MODEL:** claude/claude-fable-5
- **AGENT:** 0k
- **PROMPT:** `~/.sase/multi_prompts/202607/gh_sase_org__sase-multiprompt-260707_121356.md`

## Prompt

#gh:gh_sase-org__sase Xprompt skills and agent CLI skills in general are useful but one of their downsides is that the description for each skill gets added into the context window for every agent. Ideally I would like to support some kind of skill description progressive disclosure so that we could support potentially an infinite number of xprompt skills while keeping a tight bound on our agent's context window. Can you do some research to help me understand if this is possible and if so what types of solutions I could consider? End your analysis with a recommended approach. Write this research to a new markdown file under the sdd/research/$(date +%Y%m)/ directory.
 %m:claude/claude-fable-5

## Response

I'll research this. First, let me read the long-term memory on generated skills since this is squarely in that domain, and explore how xprompt skills currently work.

Now let me explore the codebase implementation and load web research tools in parallel.

I'll explore this repository thoroughly to answer your questions about xprompt skills. Let me start with parallel searches to map the territory.

The "deferred" hits are mostly about workspaces, not skills. Let me focus on the skills-specific code paths.

Now let me examine the provider plugins (Claude/Gemini/Codex deployment logic) and the XPrompt model.

Let me read the provider plugins and the hookspec, plus the XPrompt model definition.

Let me look at the providers that override deploy subpaths (agy, qwen, opencode) and the registry to map provider names.

Now let me read the XPrompt model, the loader (discovery), and the CLI parsers.

Now let me investigate agent launch code, HOME/settings isolation, and skill filtering/allowlists.

No existing skill allowlist or progressive disclosure. Let me examine the Codex shadow-HOME isolation (closest thing to per-run isolation) and how Claude/agy are launched.

Let me look at how the Claude CLI command is built and invoked, and how agy (Gemini) launches.

Let me see the rest of the Claude command args and check the frontmatter schema for the skill fields.

Let me capture the actual (multi-line) descriptions to gauge typical length, and check the config schema `xprompts` field plus how skills relate to xprompts.

Let me verify the xprompt search paths and confirm all skill xprompts live in the skills dir.

I have a comprehensive picture. Let me do two final confirmations: whether any skill restricts to specific providers (list form) and confirm no launch-time per-run skill injection exists.

While waiting on the codebase exploration, let me look at existing research docs to match their format conventions.

Format conventions noted. One more check on Gemini CLI's skill-listing behavior while the codebase exploration finishes.

I now have a complete picture. Here is my structured summary.

---

# xprompt skills: end-to-end map

## 1. Skill source templates

**Location:** `src/sase/xprompts/skills/*.md` — **14 files** today (all the skills you see listed as available). They are ordinary xprompt markdown files distinguished only by a `skill:` frontmatter key.

Files: `bob_dataview, sase_agents_status, sase_artifact, sase_beads, sase_changespecs, sase_chats, sase_git_commit, sase_hg_commit, sase_memory_read, sase_notify, sase_plan, sase_questions, sase_run, sase_var`.

**Frontmatter shape** (validated in `src/sase/config/sase.schema.json:1020-1036`, modeled in `src/sase/xprompt/models.py:168-170`):
- `name` (str), `description` (str), `skill` (bool **or** list of provider names), optional `log_skill_use` (bool, default `true`).

Example — `src/sase/xprompts/skills/sase_plan.md:1-6`:
```
---
name: sase_plan
description: Create an implementation plan. Use instead of plan mode (which is disabled).
skill: true
log_skill_use: false
---
```
Bodies use Jinja2 placeholders resolved per provider, e.g. `{{ provider_name }}`, `{{ provider_native_ask_tool }}` (sase_plan.md:8, sase_questions body). One skill (`sase_hg_commit.md:7`) uses the list form `skill: [gemini]` — but note "gemini" is **not** a registered provider name anymore (see §2), so that one currently deploys nowhere (stale).

**Description lengths:** typically one to three sentences, ~60-260 chars. Short ones: `sase_var` 60, `sase_plan` 76, `sase_run` 80, `bob_dataview` 85. Longer multi-line ones (`sase_chats`, `sase_git_commit`, `sase_notify`) run ~180-260 chars.

## 2. `sase skill init`

**CLI wiring:** `src/sase/main/parser_skills.py:8` registers the `skill` group (`init`/`list`/`log`/`use`); init flags come from `add_skills_init_arguments` (`src/sase/main/parser_init.py`). `sase init skills` is a compat alias (`init_skills_handler.py:659`).

**Handler:** `src/sase/main/init_skills_handler.py`
- `run_init_skills` (line 566) / `plan_init_skills` (519) drive it; source xprompts gathered by `_load_skill_xprompts` (184) = all loaded xprompts where `xp.skill` is truthy.
- Rendering: `_render_skill_targets` (343) → `_render_skill` (211, Jinja2 with `jinja2.StrictUndefined`) → `_build_output` (237) assembles the **SKILL.md** with YAML frontmatter, wrapping long/multi-line descriptions (246-258) and prepending a `sase skill use` audit directive unless `log_skill_use: false` (226-259).

**Per-provider render context** comes from the `llm_skill_template_context` hook:
- Claude `src/sase/llm_provider/claude.py:85` → `provider_name=Claude`, `provider_tool_name=Claude Code`, `provider_native_ask_tool=AskUserQuestion`
- Codex `src/sase/llm_provider/codex.py:251` → `Codex` / `ask_user`
- agy (Gemini/Antigravity) `src/sase/llm_provider/agy.py:303` → `Antigravity` / `ask_user`
- qwen `qwen.py:99`, opencode `opencode.py:112`

**Deploy paths** (`_skill_deploy_subpaths` 101, `_target_path_for_subpath` 156-164). Default subpath is `.{provider}`; providers override via `llm_skill_deploy_subpath`. Home mode → `~/<subpath>/skills/<name>/SKILL.md`:

| provider (entry point) | subpath hook | deployed file |
|---|---|---|
| claude | default | `~/.claude/skills/<name>/SKILL.md` |
| codex | default | `~/.codex/skills/<name>/SKILL.md` |
| agy (= "Gemini"/Antigravity) | `agy.py:311` → `.gemini/antigravity-cli` | `~/.gemini/antigravity-cli/skills/<name>/SKILL.md` |
| qwen | `qwen.py:107` → `.qwen` | `~/.qwen/skills/<name>/SKILL.md` |
| opencode | `opencode.py:120` → `.config/opencode` | `~/.config/opencode/skills/<name>/SKILL.md` |

Registered providers come from the `sase_llm` entry points in `pyproject.toml:117-122`: `agy, claude, codex, opencode, qwen`. There is **no separate "gemini" provider** — Gemini is served by `agy` (Antigravity), which "inherit[ed] the retired Gemini CLI slot" (agy.py:322).

**Important correction to your premise:** every provider uses the **same SKILL.md markdown-with-YAML-frontmatter format**. There is **no TOML/alternate format** for Gemini or Codex — the only per-provider variation is the Jinja context (§above) and the deploy subpath. I found no `llm_skill_format`-style hook. A `chezmoi` deploy mode also exists (`_target_path_for_subpath` 158-163, `_deploy_to_chezmoi` 486), which relocates the same files under `CHEZMOI_HOME` with a `dot_` prefix. There's also an unused `llm_additional_skill_deploy_subpaths` hook (`_hookspec.py:79`, consumed at init_skills_handler.py:119) — no provider implements it yet, but it's a ready extension point for extra locations.

## 3. xprompt definition & discovery, and skill↔xprompt relationship

- **Model:** `src/sase/xprompt/models.py:151` (`XPrompt`), skill fields at 168-170.
- **File discovery:** `src/sase/xprompt/loader_sources.py:160 get_xprompt_search_paths` searches, in order: `./.xprompts/`, `./xprompts/`, `~/.xprompts/`, `~/xprompts/`, then package built-ins `src/sase/default_xprompts/` and `src/sase/xprompts/` (163-183). Aggregated by `src/sase/xprompt/loader.py` (`get_all_xprompts`, `load_xprompts_from_internal`).
- **Config `xprompts:` field:** `~/.config/sase/sase.yml` (and overlays/plugin/local configs) via `load_xprompts_by_source` (`src/sase/config/core.py:226-284`); schema `sase.schema.json:982-1048` — each entry may carry `skill` (1020) and `log_skill_use` (1032).
- **Relationship:** It's a **1:1 opt-in**, not a wrapper and not a generic dispatcher skill. Any xprompt (built-in, file-based, or config-defined) that sets `skill: true` (or a provider list) becomes exactly **one generated SKILL.md per target provider**, whose body *is* the rendered xprompt content. `_get_target_providers` (init_skills_handler.py:146-153) expands `true`→all providers or filters the list to registered providers. The `skills/` subdirectory is just organizational; the `skill:` field is what makes an xprompt a skill.

## 4. Filtering / scoping which skills reach an agent — **none exists today**

- Skills deploy to **global per-user dotfile dirs** (`~/.claude/skills`, etc.), so every agent of a given runtime auto-loads **all** deployed skills. There is no per-agent allowlist, per-run subset, per-runtime selection table, or lazy/deferred skill loading anywhere in the code.
- The only selection knobs are **init-time**, not run-time: the `--provider` flag on `sase skill init` (init_skills_handler.py:522, 360-362) and the per-xprompt `skill: [providers]` list (which decides *which providers get the file at all*).
- The `skill_filter` machinery in `src/sase/skills/cli_log.py` and `use_log.py:187` is only for the `sase skill log` audit view — unrelated to context loading.
- The "deferred" hits throughout `src/sase/agent/` are all about **deferred workspaces** (`%wait` directives), not skills.

So progressive disclosure is greenfield.

## 5. Agent launch, HOME / settings isolation (the injection surface)

- **Claude** is launched (`src/sase/llm_provider/claude.py:223-234`, `_invoke_loop`) as:
  `claude -p --verbose --model <m> --output-format stream-json --dangerously-skip-permissions --session-id <uuid>` (+ effort args, + `SASE_LLM_*_ARGS`). **No `--settings` flag and no HOME override** → Claude reads the real `~/.claude/skills/`. To inject a per-run subset for Claude you'd need to add a `--settings` file or set an isolated `HOME`/`CLAUDE_CONFIG_DIR`; nothing does this today.
- **Codex** already has the isolation you'd want: `_codex_subprocess_env` (`src/sase/llm_provider/codex.py:183-199`) builds a **disposable per-run `CODEX_HOME`** via `_create_shadow_codex_home` (159-180). It symlinks every entry of `~/.codex` **except `config.toml`** (which is copied), then deletes the shadow home on exit. Because the `skills/` dir is currently symlinked wholesale (171-177), Codex sees all global skills — **but this is the natural hook**: replace that symlink with a generated/filtered per-run `skills/` dir to achieve progressive disclosure without touching the user's real home. `launch_spawn.py:15-23` also scrubs a stale `CODEX_HOME` from inherited env.
- **agy (Gemini)** honors `SASE_AGY_HOME`/`ANTIGRAVITY_HOME`/`AGY_HOME` (`_subprocess_agy.py:27-31`), i.e. its home is redirectable too.
- **No code writes skill files at launch time** — grep of `src/sase/agent/` and `src/sase/axe/` for `skills/`/`SKILL.md` found nothing. Skill files are only written by `sase skill init`.

## 6. Existing progressive-disclosure / context-window discussion — **none**

No code or docs discuss skill-description overhead or progressive disclosure. Searches for "progressive", "disclosure", "context window", "token budget", "description overhead" turned up only unrelated hits: `docs/sdd.md:9` and `docs/acknowledgements.md:29` ("a single session's context window", about plan persistence), and `src/sase/axe/run_agent_retry_spawn.py:109` / `run_agent_exec_plan_accept.py:580` (retry on "context window" errors / fresh-context coder). All "deferred*" symbols are workspace-launch machinery.

---

### Design implications (concise)
- Today: 14 skills → one global SKILL.md each, per provider, all always in-context. Descriptions are short (~60-260 chars) but every agent pays for all of them.
- The cleanest injection point already exists for **Codex** (per-run shadow `CODEX_HOME`, codex.py:159) and **agy** (redirectable HOME). **Claude** would need a new isolated `HOME`/config-dir or `--settings` at launch (claude.py:223) since it currently uses the real home.
- The render/deploy layer (`init_skills_handler.render_skill_targets`, and the `RenderedSkillTarget` targets) is provider-parameterized and could be reused to emit a *filtered* per-run skill set; the unused `llm_additional_skill_deploy_subpaths` hook (`_hookspec.py:79`) shows the plugin API is already designed to grow more deploy locations.

Done — the research is written to `sdd/research/202607/xprompt_skill_description_progressive_disclosure.md`. Since the only change is a research markdown file, `just check` isn't needed per the stated exceptions.

**TL;DR: Yes, description-level progressive disclosure is possible, and the recommended approach is a two-tier catalog: keep a small "core" set of always-deployed skills plus one generated `sase_skill_find` meta-skill that searches the unbounded remainder on demand** — the same pattern Claude Code already uses to defer MCP tool definitions behind its ToolSearch tool (~85% reported token savings).

Key findings that shaped this:

- **Today in sase, disclosure is all-or-nothing.** All 14 xprompt skills deploy 1:1 to global per-provider home dirs via `sase skill init`, every agent loads every name+description, and there is no per-run scoping or lazy loading anywhere — this is greenfield. Cost today is modest (~1–2k tokens/agent), but grows linearly.
- **The runtimes already do body-level progressive disclosure** (name+description upfront, SKILL.md body on activation) but handle the description listing itself by silently degrading: Claude Code truncates/drops descriptions past a 1%-of-context budget (least-used first), Codex caps at 2%/8,000 chars then omits skills, and Gemini/agy injects everything with no budget at all. Silent truncation kills implicit triggering, so "infinite skills + runtime defaults" fails quietly — research literature (SkillFlow/GOSKILLS) confirms description-only matching breaks down at scale and converges on retrieval-on-demand.
- **The doc weighs five options**: runtime-knob tuning (A), the searchable catalog + finder skill (B), launch-time per-run skill selection (C — notably Codex already launches with a disposable shadow `CODEX_HOME` and agy's home is redirectable, so injection surfaces partly exist; Claude would need `CLAUDE_CONFIG_DIR`/`--settings`/`skillOverrides`), per-prompt hook injection (D), and hierarchical grouping (E).
- **Why B wins**: it's the only option with O(1) context cost, it retrieves with the full task in view rather than predicting at launch, it fails loudly instead of silently, and it's one uniform CLI+markdown mechanism across all five providers — no runtime special-casing. The doc phases it: tiering + `sase skill search` + finder skill first, then usage-driven tier promotion via the existing `sase skill use` audit log, with optional per-run seeding (C) later. It also flags the Rust-core boundary: catalog search is domain behavior that likely belongs in `sase-core` eventually.

One incidental bug surfaced during research: `sase_hg_commit.md` declares `skill: [gemini]`, but "gemini" is no longer a registered provider entry point (agy inherited that slot), so that skill currently deploys nowhere.

Sources: [Claude Code skills docs](https://code.claude.com/docs/en/skills), [tool search docs](https://code.claude.com/docs/en/agent-sdk/tool-search), [Anthropic engineering on Agent Skills](https://www.anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills), [Codex Agent Skills](https://developers.openai.com/codex/skills), [Gemini CLI Agent Skills](https://geminicli.com/docs/cli/skills/), [SkillFlow](https://arxiv.org/pdf/2504.06188), [Group of Skills](https://arxiv.org/pdf/2605.06978).

The finalizer flagged the research file I created this session, so I'll commit it with the sase_git_commit skill.

Committed. The finalizer flagged the research file I created this session (`sdd/research/202607/xprompt_skill_description_progressive_disclosure.md`), so I committed it via the `/sase_git_commit` skill as `chore: Add research on xprompt skill description progressive disclosure` (type `create_commit`, staging only that file). The working tree is now clean and `master` is in sync with `origin/master`.
