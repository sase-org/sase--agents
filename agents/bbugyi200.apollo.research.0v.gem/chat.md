# Chat History - ace-run (research.0v.gem)

- **TIMESTAMP:** 2026-10-11 10:13:44 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.0v.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261011_095836.md`

## Prompt

%id(gem, clan=research.0v)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.0v.cdx`, `research.0v.cld`, `research.0v.grk`, `research.0v.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you do some research on the pi repo (see https://github.com/earendil-works/pi)? How
does this product compare to sase? In what ways can sase learn from pi? End your
analysis with a ranked list of improvements to sase that you think I should consider
implementing to make sase more appealing to someone who already uses pi. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__gem` suffix, i.e. `<stem>__gem.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path and its path relative to the research repo root
(for example
`research:202609/topic__a.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

# Research Summary: Technical Analysis of Pi (`earendil-works/pi`) vs. SASE

**Researcher:** `research.0v.gem`  
**Report File:** [`pi_agent_harness_comparison_and_sase_learnings__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/sase/repos/research/202610/pi_agent_harness_comparison_and_sase_learnings__gem.md)  
**Artifact Registration:**
- **Absolute Path:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/sase/repos/research/202610/pi_agent_harness_comparison_and_sase_learnings__gem.md`
- **Label:** `research:202610/pi_agent_harness_comparison_and_sase_learnings__gem.md`
- **Artifact ID:** `explicit:2e5f0447e749fa7b248699fb` (`artifacts[0]`)

---

## 1. Executive Summary & Product Architecture

**Pi** (`https://github.com/earendil-works/pi`), developed by Mario Zechner and the Earendil Works team, is a **minimalist, highly extensible terminal agent harness**. Rather than enforcing complex agentic state machines, sub-agents, or autonomous planning out of the box, Pi provides a rock-solid, hackable pair-programming runtime.

Key subsystems of the Pi monorepo:
- **`@earendil-works/pi-coding-agent`**: The core CLI application supporting `interactive`, `print`, `json`, and `rpc` modes with in-process TypeScript extension loading (via `jiti`), session tree management, and standard tools (`read`, `write`, `edit`, `bash`, `find`, `grep`).
- **`@earendil-works/pi-codemode`**: Sandboxed JavaScript execution powered by QuickJS in WASI (`quickjs-wasi`). Allows the model to write scripts that run tool calls concurrently (`Promise.all()`), filter gigabytes of data locally, and return condensed results without blowing out the model context window.
- **`@earendil-works/pi-ai`**: A unified multi-provider LLM API supporting Anthropic, OpenAI, Google Generative AI, Bedrock, Mistral, Groq, Cerebras, DeepSeek, and custom gateways, with streaming, token planning, pricing, and dynamic **Virtual Model** routing.
- **`@earendil-works/pi-tui`**: A pure TypeScript terminal UI library with differential screen rendering, inline/alt-screen support, Kitty/Sixel/iTerm2 image display, and OKLab color spaces.
- **`@earendil-works/pi-protocol` & `@earendil-works/pi-client`**: Transport-neutral remote agent communication over framed CBOR bytes and JSONL RPC.
- **Distribution & Packages**: Community distribution of extensions, prompt templates, and skills (implementing the open [Agent Skills spec](https://agentskills.io)) via npm and git (`pi install npm:...` / `pi install git:...`).

---

## 2. Architectural Comparison: Pi vs. SASE

| Dimension | Pi (`earendil-works/pi`) | SASE (`sase`) | Core Trade-off |
| :--- | :--- | :--- | :--- |
| **System Identity** | Extensible Agent Harness / Interactive Pair Programmer | Structured Autonomous Software Engineering Factory | Pi optimizes for interactive hacker flow; SASE optimizes for autonomous, verifiable project lifecycle. |
| **Turn Contract** | Stateful multi-turn conversational loop in an append-only JSONL session tree (`id`/`parentId`). | Ephemeral, bounded single-turn agent execution with host-owned completion. | Pi keeps state in transcripts; SASE externalizes state to durable artifacts (Beads, SDD, Memory Webs). |
| **Workspace Isolation** | Runs by default directly in the user's CWD (host permissions). Optional micro-VM/Docker sandboxes. | Hermetic, numbered workspace clones (`sase_<N>`). Guarded recipes prevent accidental command execution. | SASE guarantees parallel safety and pristine git states; Pi requires careful manual user supervision. |
| **Completion & Commits** | Model/user commits directly via bash or extensions; relies on prose instructions in `AGENTS.md`. | **Host-Owned Completion**: agents submit a declaration; host runs two-speed verification (`just check`) and commits. | SASE prevents hallucinated/broken commits from ever polluting repository history. |
| **Task / Issue Tracking** | Explicitly omitted ("skips sub-agents and plan mode"). | First-class git-portable **Beads** (tasks, epics, dependency DAGs, triage life cycles). | SASE manages large multi-epic projects natively; Pi requires external trackers. |
| **Tool Execution** | **QuickJS Codemode**: models write local scripts to batch and filter tools before returning to LLM context. | Standard sequential tool/recipe calling; large terminal outputs can fill context quickly. | **Pi wins decisively** on tool efficiency, token density, and round-trip latency. |
| **Model Routing** | **Virtual Models**: dynamic per-request routing (e.g. cheap model for inspection, flagship for code, auto-fallback on error). | Static effort ladders and size aliases (`@small`, `@large`, `@xlarge`). | Pi provides dynamic runtime routing; SASE configures models at launch time. |
| **Extensibility Model** | Zero-build live TypeScript (`jiti`) in `~/.pi/agent/extensions/` + npm/git packages (`pi install`). | Python plugins, macro directives, and chezmoi-managed skills. | Pi's extension authoring and sharing is drastically more frictionless. |

---

## 3. What SASE Can Learn from Pi

1. **Programmatic Tool Chaining (The Codemode Paradigm):** Running a WebAssembly QuickJS sandbox where the model writes scripts to query files, grep patterns, and filter outputs locally slashes token consumption by 50–70% and eliminates multi-round turn delays.
2. **Dynamic Virtual Models & Per-Request Routing:** Separating user model intent from physical dispatch allows sub-turns (like linting or status checks) to run on lightweight models, while routing complex architectural generation to heavy models, with transparent error fallback across providers.
3. **Decentralized Package Distribution (`pi-package`):** Distributing skills, macros, and extensions via simple git repositories or npm packages (`sase package install <git-url>`) makes community sharing effortless compared to manual template copying.
4. **Framed Bi-Directional RPC Protocol:** Standardizing a clean JSONL/CBOR protocol over stdin/stdout and Unix domain sockets simplifies building Neovim, VSCode, and web UI integrations.
5. **Fast Interactive Single-Agent Ergonomics:** Providing an instant-startup terminal REPL with differential rendering fills the gap between casual brainstorming and heavy-duty autonomous execution.

---

## 4. Ranked Improvements to SASE for Pi Users

Prioritized specifically to appeal to developers who already use and love Pi:

1. **Rank 1: SASE Codemode — In-Sandbox Scripted Tool Execution**
   - *Rationale:* Solves the #1 complaint of Pi users switching to other harnesses: sequential tool fatigue and context bloat.
   - *Proposal:* Embed a QuickJS WASI sandbox in `sase_core_rs` exposing SASE tools (`read`, `write`, `edit`, `find`, `grep`, `bead`). Let agents write JS/Python scripts to execute multi-tool investigations locally, returning only the synthesized results to the LLM context.
2. **Rank 2: `sase repl` — Fast Interactive Single-Agent Mode with "Promote to Bead"**
   - *Rationale:* Pi users love launching their agent in under a second for immediate, keyboard-driven terminal pair programming.
   - *Proposal:* Build a lightweight CLI REPL (`sase repl`) with differential inline rendering. Include a one-key shortcut (`Ctrl+P` / `/promote`) that freezes the conversation, creates a formal SASE task bead, claims a numbered workspace clone, and hands execution off to SASE's autonomous background supervisor.
3. **Rank 3: Dynamic Virtual Model Routing in Runner & Macro Dispatch**
   - *Rationale:* Eliminates token waste and provider fragility by routing requests adaptively.
   - *Proposal:* Evolve SASE size aliases into dynamic Virtual Model Routers capable of routing exploratory turns to fast models (Flash/Haiku), coding turns to flagship models (Sonnet/Pro), and automatically retrying on alternate providers when encountering 429/503 errors.
4. **Rank 4: `sase package` — Portable Community Package & Skill Distribution**
   - *Rationale:* Makes sharing custom tools and prompt templates as simple as `pi install`.
   - *Proposal:* Introduce `sase package install github.com/user/sase-tools` to discover and manage third-party macros, memory strands, skills, and tools in user (`~/.config/sase/packages/`) and project (`.sase/packages/`) scopes.
5. **Rank 5: Unified Bi-Directional Framed RPC Protocol**
   - *Rationale:* Replaces ad-hoc screen-scraping and custom bridges with a rock-solid IPC contract.
   - *Proposal:* Standardize a framed JSONL/CBOR RPC mode for SASE daemons and child processes, providing native, responsive backends for `sase-nvim`, VSCode, and remote web control planes.
6. **Rank 6: Tree-Aware Session Branching & Visual Rewind in ACE (TUI)**
   - *Rationale:* Allows users to explore alternative implementation paths without restarting from scratch.
   - *Proposal:* Allow users inspecting agent runs in the ACE Agents tab to select any past tool or message step and "Fork from here", provisioning a clean numbered workspace matching that exact git snapshot.
7. **Rank 7: Hermetic Single-Binary CLI & Supply-Chain Hardening**
   - *Rationale:* Removes virtualenv/compiler onboarding friction and ensures bulletproof dependency security.
   - *Proposal:* Provide single-binary standalone distributions of SASE and incorporate Pi's `min-release-age` dependency aging policies into CI build gates.

---

*The complete, detailed report with extensive code citations, architectural diagrams, and analysis is saved and registered at `research:202610/pi_agent_harness_comparison_and_sase_learnings__gem.md`.*
