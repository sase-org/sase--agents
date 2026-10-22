# Chat History - ace-run (research.3n.gem)

- **TIMESTAMP:** 2026-10-05 07:03:09 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.3n.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261005_065248.md`

## Prompt

%id(gem, clan=research.3n)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.3n.cdx`, `research.3n.cld`, `research.3n.grk`, `research.3n.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to migrate all existing agent instruction files to a single SASE.md file
that defines a spec for the agent instruction file that gets used to contruct the
appropirate agent instruction file dynamically in ephemeral workspaces before launching
sase agents in those workspaces.

- I think that this architecture change will allow us to fix a few bugs identified in
  the agent_instructions_budgeted_router.md file in the research sidecar repo (e.g. Grok
  reads both AGENTS.md and CLAUDE.md and codex doesn't read the ~/AGENTS.md file at
  all).
- Also, this would unlock the ability to specify that parts of the agent instruction
  file should only be rendered for certain agents. I'm not sure how we should identify
  these agents, but my first thought would be to use a new `%tag` directive to tag
  certain agents and then only render some parts of the agent instruction file for
  agents with certain tags. This is just my first instinct though. You should think hard
  about the best way to implement this.
- I think I'm probably forgetting a few other high-value use-cases (see if you can
  identify any that I missed).

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__gem` suffix, i.e. `<stem>__gem.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example `research:202609/topic__a.md`), including any subdirectory the steps above
put it in. Do not derive the label from the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

# Research Report: Dynamic Agent Instruction Architecture (`SASE.md`)

**Author:** researcher gem (`research.3n.gem`)  
**Report File:** [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/sase_md_dynamic_agent_instructions__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/sase_md_dynamic_agent_instructions__gem.md)  
**Registered Artifact:** `research:202610/sase_md_dynamic_agent_instructions__gem.md` (`file:explicit:4bee444a5e1925fd1ddef1d2`)

---

## 1. Executive Summary & Verdict

Migrating the repository's 20 static agent instruction files to a single canonical **`SASE.md`** specification and compiling specialized instruction files dynamically in ephemeral workspaces is **a high-value, necessary architectural evolution**. 

Treating instruction files as **compiled, ephemeral runtime artifacts** tailored to the specific consumer rather than static source code checked into version control directly eliminates persistent multi-agent bugs that static files cannot solve.

### Summary of Key Findings

1. **Defects Solved on Day One**:
   - **Grok Double-Load**: Grok natively reads `AGENTS.md` and discovers `CLAUDE.md`. In an ephemeral workspace for Grok, generating *only* `AGENTS.md` and ensuring `CLAUDE.md` is absent cuts ~4,300 duplicate tokens per turn.
   - **Antigravity CLI (`agy` / Gemini) Double-Load (Empirically Confirmed)**: In this active session, Antigravity discovered and loaded **both** `AGENTS.md` and `GEMINI.md` into `<user_rules>`, duplicating 283 lines and ~4,300 tokens on every LLM call. In an ephemeral workspace for Antigravity, generating *only* `GEMINI.md` (or *only* `AGENTS.md`) eliminates this 100% duplicate load.
   - **Codex Missing `~/AGENTS.md`**: OpenAI Codex CLI walks up only to the git repository root (`.git`) and stops, ignoring home instructions. Dynamic compilation allows SASE to layer `~/.sase/SASE.md` directly into the workspace's root `AGENTS.md`, making home rules visible to Codex for the first time.

2. **Essential Architectural Adjustments (Pitfalls Avoided)**:
   - **The Vanilla Developer Experience**: If `AGENTS.md` is completely deleted from git, developers running raw `claude`, `codex`, or Cursor in the primary repo checkout will have zero context. **Recommendation:** Git tracks `SASE.md`; `sase init` compiles a canonical baseline `AGENTS.md` in the primary checkout, while ephemeral workspaces compile specialized overlays.
   - **Workspace Preparation & Git Hygiene**: `prepare_workspace` executes `git reset --hard` and `git clean -fd`. Dynamic compilation must occur *after* workspace clean/sync, immediately prior to process launch. The generated target file must be registered in `.git/info/exclude` to avoid being wiped by `git clean` or showing up as untracked churn in `git status`.
   - **Two-Tier Agent Identification**: Relying solely on a manual prompt directive like `%tag` forces prompt authors into manual tag management. We recommend a **hybrid model**: automatic intrinsic properties (`provider`, `agent_type`, `model_tier`, `workflow_phase`) combined with an optional `%tag` directive.

---

## 2. Analysis of Targeted Defects & Empirical Findings

| Provider / Tool | Native Primary | Fallback / Also Discovered | SASE Today | SASE Issue / Behavior | Fix Under `SASE.md` Dynamic Architecture |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Grok (`grok`)** | `AGENTS.md` | `CLAUDE.md` (auto-detected) | Both exist on disk | **Double-loads `AGENTS.md` AND `CLAUDE.md`!** (~4.3k tok x 2) | Generate `AGENTS.md`; ensure `CLAUDE.md` does **not** exist in the workspace. |
| **Antigravity (`agy` / Gemini)** | `GEMINI.md`, `AGENTS.md` | Both discovered hierarchically | Both exist on disk | **Double-loads `AGENTS.md` AND `GEMINI.md`!** (~4.3k tok x 2) | Generate `GEMINI.md`; ensure `AGENTS.md` does **not** exist in the workspace. |
| **Codex (`codex`)** | `AGENTS.md` (git root down) | None (halts at `.git`) | `AGENTS.md` exists, `~/AGENTS.md` ignored | **Never sees `~/AGENTS.md`** because it stops at git root | Inline home `~/.sase/SASE.md` directly into workspace root `AGENTS.md`. |
| **Claude Code (`claude`)** | `CLAUDE.md` (walks to `~`) | `AGENTS.md` (newer builds) | `CLAUDE.md` exists | Reads `CLAUDE.md` + `~/CLAUDE.md` | Generate `CLAUDE.md`; suppress unused provider shims. |
| **OpenCode / Qwen** | `OPENCODE.md` / `QWEN.md` | `AGENTS.md` | Both exist on disk | Redundant static files | Compile single target file per provider; zero unused shims. |

---

## 3. Selective Rendering: Mechanism Design & Grammar

### Two-Tier Identification Model

Instead of requiring users to manually tag every prompt with `%tag`, the compiler should evaluate a two-tier context environment:

1. **Intrinsic Context Variables (Automatic)**:
   - `provider`: `"claude" | "codex" | "agy" | "grok" | "qwen" | "opencode"`
   - `agent_type`: `"planner" | "research" | "editor" | "swe" | "audit"`
   - `tier`: `"large" | "small"`
   - `model`: e.g. `"claude-3-5-sonnet"`, `"gemini-1.5-pro"`
   - `is_plan`: `bool`
   - `bead_type`: `"bug" | "feature" | "task" | "epic"`
2. **Extrinsic Tags (User / Macro Directives)**:
   - `%tag <tag1>,<tag2>` or `%tags [rust, frontend]` in the prompt.
   - Automatically populated by intrinsic attributes as well (e.g. `"claude" in tags`, `"research" in tags`).

### Recommended Grammar: HTML Comment Directives

HTML comments (`<!-- sase:if ... -->`) are strongly recommended over raw Jinja2 delimiters:
- **Clean Previews**: Invisible when viewed on GitHub, Markdown viewers, or documentation generators.
- **No Parser Breakage**: Does not break Markdown linters, code fences, or table alignment.
- **Safe Fallback**: External tools reading raw `SASE.md` treat directives as ordinary comments.

```markdown
# Structured Agentic Software Engineering (SASE) - Agent Instructions

## 1. Core Runtime Contract
- Before any normal response ending this turn, use your `/sase_final` skill.
- Ephemeral workspaces: do not write workspace numbers into plans.

<!-- sase:if provider == "codex" -->
## Codex Streaming Gotchas
- `exec_command` yields before completion. Poll with empty input until returncode.
<!-- sase:endif -->

<!-- sase:if agent_type != "research" -->
## Code Modification & Verification
- Read `lint_and_test.md` before changing tracked files.
- Guarded recipes: run `just check` only through `sase tool run`.
<!-- sase:endif -->

<!-- sase:if "rust" in tags or "sase-core" in tags -->
## Rust Core Boundary
- Shared backend behavior belongs in `sase-core`.
<!-- sase:endif -->

<!-- sase:if tier == "large" -->
## Reference Memory Catalog
1. `sase/memory/cli_rules.md` - Read before adding CLI subcommands.
2. `sase/memory/dispatch.md` - Read before `%dispatch`.
<!-- sase:else -->
## Reference Memory
- Read on demand via `/sase_memory_read <name>`.
<!-- sase:endif -->
```

---

## 4. Eight Additional High-Value Use Cases Unlocked

1. **Role-Based Progressive Disclosure**: Planners get planning conventions and bead rules; SWEs get testing/linter rules; researchers have commit/finalizer rules stripped.
2. **Model Tier & Context Budget Tuning**: Small/fast models (Flash, Haiku) receive a strict 40-line minimal contract, eliminating instruction dilution and reducing latency; large models receive full reference routers.
3. **Subsystem Scoping (Eradicating 20 Files)**: Eliminates 15 redundant nested instruction files across `src/sase/ace/`, `tools/`, and `demos/tapes/` by consolidating them into scoped blocks in `SASE.md`.
4. **Dynamic Sidecar & Linked Repo Path Resolution**: Injects exact runtime paths for sidecars and linked repos without hardcoding ephemeral paths into git.
5. **Unified Home + Project Layering**: Extends Claude's `~/CLAUDE.md` layering feature to all providers by layering `~/.sase/SASE.md` into every provider's compiled instructions.
6. **Provider Operational Caveats**: Restricts provider-specific caveats (Codex streaming polling, Antigravity print-mode non-interactive behavior) to the affected provider.
7. **Clean Git History & Zero Merge Conflicts**: PRs only touch `SASE.md`. Eliminates 5-file lockstep git diffs on memory updates.
8. **Security & Sandboxing**: Omits privileged instructions (e.g. `/sase_sudo`) for untrusted or external contributor runs.

---

## 5. Recommended Architecture & Phased Roadmap

```
1. Workspace Preparation (git reset/clean/sync)
2. SASE.md Compilation (evaluates provider, agent_type, tags, tier)
3. Workspace Write & Isolation (writes single target file; registers in .git/info/exclude)
4. Conflicting Shim Cleanup (unlinks CLAUDE.md for Grok; unlinks AGENTS.md for Antigravity)
5. Evidence Snapshot (captures compiled digest in launch_evidence.json)
6. Agent Process Launch (runs in clean, single-instruction workspace)
```

- **Phase 1: Spec Parser & Compiler (`src/sase/instructions/compiler.py`)**: Safe boolean evaluator for HTML comment directives against context variables.
- **Phase 2: Runner Launch Integration (`run_agent_runner_launch.py`)**: Hook compilation between `_prepare_workspace_and_repos()` and `capture_launch_evidence()`.
- **Phase 3: Shim Suppression (Grok & Antigravity Fixes)**: Ensure only the native file exists per provider; inline home instructions for Codex.
- **Phase 4: Primary Checkout Ergonomics & Migration**: Create root `SASE.md`; generate baseline `AGENTS.md` in primary checkout; remove the 20 tracked static shims from git.
- **Phase 5: Tagging Directives & Macro Autocompletion**: Wire `%tag <a,b>` into prompt preprocessing and ACE TUI.

---

*The complete research report with all technical diagrams and implementation details is available in the registered artifact:*  
`research:202610/sase_md_dynamic_agent_instructions__gem.md`
