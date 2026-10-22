# Chat History - ace-run (research.4w.gem)

- **TIMESTAMP:** 2026-10-19 07:34:35 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.4w.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261019_071704.md`

## Prompt

%id(gem, clan=research.4w)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.4w.cdx`, `research.4w.cld`, `research.4w.grk`, `research.4w.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to add hermes (see the https://github.com/nousresearch/hermes-agent GitHub repo for
context) as a new, fully supported sase LLM provider. Can you do some research with the
goal of helping me decide the best way to implement this? I believe there is another
research file in the research sidecar repo related to hermes that you should review if you
can find it. End your analysis with a recommended solution. 
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

# Research Report: Implementing Hermes Agent as a Fully Supported SASE LLM Provider

**Author:** Researcher Gem (`research.4w.gem`)  
**Artifact ID:** `explicit:e6348840de1507f60140581e`  
**Report Source:** [`hermes_llm_provider_architecture_and_implementation__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/research/202610/hermes_llm_provider_architecture_and_implementation__gem.md)  
**Artifact Ref:** `file:explicit:e6348840de1507f60140581e` (`research:202610/hermes_llm_provider_architecture_and_implementation__gem.md`)

---

## 1. Executive Summary & Recommended Solution

SASE operates under the guiding axiom *"One prompt is not an engineering system"* and the architectural contract that **adapters normalize harnesses** ([`adapters-normalize-harnesses`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/AGENTS.md)). SASE does not maintain an internal LLM tool-calling loop; rather, it coordinates autonomous vendor coding CLIs (`claude`, `codex`, `agy`, `opencode`, `qwen`, `grok`, `muse`) as single-turn execution engines within isolated, ephemeral numbered git worktrees (`sase_<N>`).

**Recommendation:** Add Hermes as **SASE's eighth native Agent CLI Provider** (`hermes`), directly wrapping the [`hermes`](https://github.com/nousresearch/hermes-agent) CLI in headless, streaming JSON mode:

```bash
hermes chat \
  --query-file <sase_managed_tmp_prompt> \
  --format stream-json \
  --oneshot \
  --yolo \
  --ignore-user-config \
  --ignore-rules \
  --source tool \
  --model <model_id> \
  [--reasoning <effort_level>]
```

This implementation allows SASE operators to run:
1. **Nous Research Frontier Models:** Native support for Nous Hermes 3 (405B, 70B, 8B) and Hermes 4 via Nous Portal endpoints.
2. **Local and Edge Inference:** Support for local models managed through Hermes's provider layer (Ollama, llama.cpp, vLLM, LM Studio).
3. **Multi-Model Routing:** Ability to dispatch to any of Hermes's ~40 inference backends while keeping SASE's host-owned completion, bead/patch tracking, and two-speed CI verification authoritative.

---

## 2. Review of Prior Research

We audited prior research within the SASE research repository:
- **[`research:202609/sase_vs_hermes_agent/sase_vs_hermes_agent__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/research/202609/sase_vs_hermes_agent/sase_vs_hermes_agent__gem.md):** Contrasted OpenClaw-descended personal assistant architectures with SASE's engineering control plane.
- **[`research:202610/can_hermes_replace_sase/can_hermes_replace_sase__final.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/research/202610/can_hermes_replace_sase/can_hermes_replace_sase__final.md):** The multi-researcher synthesis concluded that Hermes excels as a personal agent companion and local model orchestrator, but lacks SASE's engineering governance (host-owned commits with provenance, typed durable gates, work records in git). Section 9 recommended:
  > *"Complement, not rival... Making Hermes the eighth SASE provider would turn the main competitor in the overlap into a supplier. It would bring Hermes's local and any-model loop under SASE's workspaces, gates and finalizers."*

---

## 3. Architecture & Implementation Specification

### 3.1 Critical Technical Gotchas & Mitigations

1. **Meta React Native Binary Collision (High Severity):**  
   Meta's React Native JavaScript engine is also named `hermes` and frequently exists at `/usr/bin/hermes`. If SASE autodetected `hermes` on `PATH`, it would inadvertently invoke a JavaScript engine and crash.  
   *Mitigation:* In [`HermesProvider`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/llm_provider/base.py), implement `llm_autodetect_priority() -> None`, matching the precedent established by `muse`. Hermes must be explicitly configured via `llm_provider.provider: hermes`, `%model:hermes/...`, or `SASE_HERMES_PATH`.
2. **Instruction Isolation & Memory Contamination:**  
   Hermes automatically discovers and injects local `AGENTS.md`, `SOUL.md`, `.cursorrules`, and SQLite memory cards. SASE uses per-invocation instruction rendering ([`instructions-per-invocation`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/AGENTS.md)).  
   *Mitigation:* Always pass `--ignore-rules` and `--ignore-user-config`. SASE delivers its rendered instruction bundle via `CHANNEL_HERMES_ROOT = "hermes.prompt_prefix"` prepended to the prompt file.
3. **OS `ARG_MAX` Prompt Exceeded:**  
   Passing large engineering prompts with AST symbol tables and diffs via `-q` causes kernel `E2BIG` errors.  
   *Mitigation:* Always pass `--query-file <path>` referencing a managed temporary prompt file.
4. **Approval Deadlocks:**  
   Hermes prompts interactively for dangerous commands by default.  
   *Mitigation:* Always pass `--yolo` for headless execution.

### 3.2 Subprocess Streaming Parser (`_subprocess_hermes.py`)
Hermes's `StreamJsonEmitter` emits clean JSONL stdout lines:
- `{"type": "text", "text": "..."}` ➔ Streamed live to SASE's `live_reply` buffer for Textual TUI rendering.
- `{"type": "tool_use", "name": ..., "input": ...}` ➔ Emitted for real-time card activity tracking.
- `{"type": "tool_result", "output": ...}` ➔ Recorded for command duration and output diagnostics.
- `{"type": "result", "tokens": {...}, "exit_code": ..., "text": ...}` ➔ Terminal record capturing `input_tokens`, `output_tokens`, `cache_read_input_tokens`, `cache_creation_input_tokens`, and final text.

### 3.3 Reasoning Effort Parity
Hermes supports `--reasoning <LEVEL>` with levels matching SASE's canonical ladder (`none`, `minimal`, `low`, `medium`, `high`, `xhigh`, `max`).

### 3.4 Hook Implementations & Catalog Registration
- **Provider Class:** [`HermesProvider`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/llm_provider/base.py) under `src/sase/llm_provider/hermes.py` implementing `sase_llm` hook specifications:
  - Short name: `her`
  - Status color: `#E0A96D` (Nous brand gold/bronze)
  - Emoji badge: `☤` (Caduceus) or `🪽` in [`src/sase/integrations/provider_badges.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/integrations/provider_badges.py)
  - Native ask-tool: `clarify`
  - Skills directory: `.hermes` (deploys to `~/.hermes/skills/`)
  - Installer: `manager: "script"`, `install_script_url: "https://hermes-agent.nousresearch.com/install.sh"`
- **Model Catalog ([`src/sase/llm_provider/models.yml`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/src/sase/llm_provider/models.yml)):**
  - `nous/hermes-3-llama-3.1-405b` (Tier: `large`, short alias: `hermes405b`)
  - `nous/hermes-3-llama-3.1-70b` (Tier: `small`, short alias: `hermes70b`)
  - `nous/hermes-3-llama-3.1-8b` (short alias: `hermes8b`)
  - `nous/anthropic/claude-sonnet-4-6` (short alias: `hermes-sonnet`)
- **Pluggy Entry Point ([`pyproject.toml`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/pyproject.toml)):**
  - `hermes = "sase.llm_provider.hermes:HermesProvider"`

---

## 4. Deliverables & Snapshot Registration

1. **Research Report Written:**  
   [`hermes_llm_provider_architecture_and_implementation__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/research/202610/hermes_llm_provider_architecture_and_implementation__gem.md)  
   *(Path: `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_22/sase/repos/research/202610/hermes_llm_provider_architecture_and_implementation__gem.md`)*
2. **Artifact Snapshot Created:**
   - **ID:** `explicit:e6348840de1507f60140581e`
   - **Label:** `research:202610/hermes_llm_provider_architecture_and_implementation__gem.md`
   - **Reference:** `file:explicit:e6348840de1507f60140581e`
3. **Turn Finalizer Declaration Submitted:**  
   Host-owned finalizer declaration accepted for repository `sdd:research` to commit the new report deliverable.
