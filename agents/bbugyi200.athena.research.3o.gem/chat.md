# Chat History - ace-run (research.3o.gem)

- **TIMESTAMP:** 2026-10-05 12:45:50 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.3o.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261005_122744.md`

## Prompt

%id(gem, clan=research.3o)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.3o.cdx`, `research.3o.cld`, `research.3o.grk`, `research.3o.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to migrate all existing agent instruction files to use sase's memory files
dynamically to contruct instructions for each sase agent right before launching that
agent.

- I've already done some research on this. Review the sase_md_instruction_delivery.md
  file in the research sidecar repo for context before performing your own research. I
  agree with all of the recommendations made in that research file I think (see below
  bullets).
- One thing I'm not sure the previous research addresses is how we will ensure that when
  another developer clones the sase repo and runs `claude` (or any other LLM provider
  that we support) that this interactive instance of claude has a reasonably good
  CLAUDE.md (or some equivalent to work with). I was thinking maybe we could instruct
  agents (where though?) to run the appropriate `sase / `uvx run sase` command to
  generate this file if it doesn't exist?
- Also, it is not clear to me how a specific provider's subagents are given agent
  instructions that are equivalent to (or better/fixed) what they get today with our
  current agent instruction files.

Can you do some research with the goal of helping me decide the best way to address each
of these issues? End your analysis with a recommended solution. 
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

# Research Report: Dynamic Instruction Delivery for Interactive Clones and Provider Subagents

I have completed the research into both open issues regarding the migration to dynamic, per-invocation instruction delivery. The full report has been written to disk and registered as a durable artifact:

- **Report Path:** [`instruction_delivery_interactive_clones_and_subagents__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_28/sase/repos/research/202610/instruction_delivery_interactive_clones_and_subagents__gem.md)
- **Artifact Reference:** `file:explicit:f4a1cc7f43775a783df1d36a`
- **Artifact Label:** `research:202610/instruction_delivery_interactive_clones_and_subagents__gem.md`

---

### Key Findings & Answers to Your Questions

#### 1. Fresh Clones & Interactive Developer Experience (`claude`, `codex`, `agy`)
* **The "Ancestor `~/CLAUDE.md`" Trap:** In Claude Code 2.1+, fallback from `CLAUDE.md` to `AGENTS.md` is disabled whenever an ancestor directory contains a `CLAUDE.md`. Because active Claude Code users almost always have a personal `~/CLAUDE.md`, omitting `CLAUDE.md` from the repo root results in Claude loading `~/CLAUDE.md` and completely ignoring `AGENTS.md`. A tracked project-level `CLAUDE.md` is strictly required.
* **The Perils of Agent-Driven Overwrite:** Instructing an interactive agent to run `sase / uvx run sase` to overwrite a tracked `CLAUDE.md` dirties `git status`, corrupts pull requests, and recreates the 111-commit churn problem that the architecture sought to eliminate. Furthermore, Claude Code renders its prompt *before* the first prompt turn; writing files on turn 1 does not update the active session's context.
* **Recommended Pattern: Self-Sufficient Stubs + Gitignored Local Overlays:**
  - **Committed Permanent Stubs (~35 lines):** Track concise, static stubs for both `CLAUDE.md` and `AGENTS.md`. They supply immediate answers to what every human/AI needs out of the box without running setup commands: verification recipes (`just check`, `just test`), core architecture (the Rust `sase-core` backend boundary vs Python Textual TUI), and direct pointers to `sase/memory/`.
  - **Gitignored Local Overlays (`CLAUDE.local.md`):** Claude Code natively discovers `CLAUDE.local.md` for local configuration, which is **already ignored** in SASE's `.gitignore` (line 58). Running `just sync-instructions` (or `uv run sase instructions sync`) compiles the full dynamic bundle into `CLAUDE.local.md`, preserving clean git status.
  - **Automated SASE Exclusion:** In automated SASE runs, the runner suppresses both committed stubs via Claude's `--settings '{"claudeMdExcludes": ["CLAUDE.md", "AGENTS.md"]}'` and Codex's shadow home, delivering the authoritative bundle through explicit channels.

---

#### 2. Provider Subagents: Instruction Parity & Role Specialization
* **Today's Subagent Reality & Bugs:** Subagents in Claude Code currently read `CLAUDE.md` from disk and inherit `/sase_final`, creating dangerous attempts by subagents to finalize turns and commit code. Antigravity subagents miss prompt prefixes passed only to the root agent. Grok subagents receive zero instructions because the folder is untrusted.
* **Claude Code Breakthrough:** Direct inspection of the Claude Code 2.1.289 executable reveals first-class CLI flags:
  `--append-subagent-system-prompt <prompt>` and `--append-subagent-system-prompt-file <path>`.
* **Recommended Role-Specialized Delivery:**
  - **Claude Code:** Render a specialized bundle with `role: subagent` and pass it via `--append-subagent-system-prompt-file <path>`. This bundle includes all core memory, repo rules, and memory triggers, but **strictly omits `/sase_final`**, gate continuations, and monitor directives.
  - **Antigravity (`agy`):** Write the rendered bundle to `.agents/rules/sase.md` and register `.agents/` in `.git/info/exclude`. Antigravity natively loads `.agents/rules/*.md` for the parent and all subagents (`self`, `research`, custom), guaranteeing deduplicated parity without git dirtiness.
  - **xAI Grok:** Deliver instructions via session-level `--rules <bundle>`, inherited by all `spawn_subagent` calls while keeping workspaces untrusted.
  - **OpenAI Codex:** Deliver via `$CODEX_HOME/AGENTS.md`, which cascades to all internal multi-agent execution branches.
  - **Muse:** Maintain the single-turn invariant (subagents prohibited).

---

### Implementation Phases

1. **Phase 1 (Adapters):** Add `--append-subagent-system-prompt-file` in `claude.py` with a `role: subagent` bundle filter; write `.agents/rules/sase.md` in `agy.py` with `.git/info/exclude` isolation.
2. **Phase 2 (Repo Stubs & Sync):** Replace the 20 generated files with two permanent 35-line stubs (`CLAUDE.md` and `AGENTS.md`); update `sase instructions sync` to write `CLAUDE.local.md` and `AGENTS.local.md`.
3. **Phase 3 (Verification):** Extend `sase doctor instructions` to verify that subagents across all providers receive their specialized bundles without duplicate native file loads.
