# Chat History - ace-run (research.26.gem)

- **TIMESTAMP:** 2026-09-21 19:02:11 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.26.gem
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260921_185249.md`

## Prompt

%id(gem, clan=research.26)
%m:agy/gemini-3.8-flash-high %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 3-researcher swarm.
The other researchers, `research.26.cld`, `research.26.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cld.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I'm not sure what the
best solution for multi-agent collaboration is when it comes to sase agents. Can you do
some research with the goal of helping me decide the best way to implement this? End
your analysis with a recommended solution. Review the multi_cli_orchestration_vs_sase.md
and family_channel_delivery.md files in the research sidecar repo for context and
inspiration before peforming your own research. 
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

# Research Report: Multi-Agent Collaboration Architecture for SASE

- **Author / Agent:** `research.26.gem`
- **Report Location:** [`multi_agent_collaboration_architecture__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_41/sase/repos/research/202609/multi_agent_collaboration_architecture__gem.md)
- **Durable Artifact Reference:** `research:202609/multi_agent_collaboration_architecture__gem.md` (`file:explicit:efd5284fcc54f41cf893959a`)

---

## 1. Executive Summary & Recommended Solution

Mainstream multi-agent approaches frequently adopt either unconstrained conversational forums ("agents chatting freely in a loop") or synchronous nested tool calls (`invoke_subagent`). **Both paradigms are fundamentally incompatible with SASE's core architectural tenets:**
1. **Single-Turn Execution (`decisions:single-turn-agents`):** Agent runs are strictly single provider turns; there are no persistent background daemon processes or in-process sleeps.
2. **Non-Blocking Gates (`decisions:gates-never-block`):** Human decision points terminate the calling agent immediately, delegating the decision to a non-LLM gate shell.
3. **Host-Owned Completion (`decisions:host-owned-completion`):** Finalizers and landing are host-verified and host-executed; agents submit declarations (`/sase_final`).
4. **Isolated Ephemeral Workspaces (`sase_<N>`):** Parallel agents run in separate repository clones; concurrent file changes are invisible across workspaces until shared.
5. **Context Economics & Prompt Bounding:** As demonstrated in the `016` supervision experiment, unconstrained message boards cause severe prompt bloat (70–110 KB per turn), which degrades reasoning and inflates token spend by 15x–20x.

### The Recommended Solution

The recommended solution is a **Durable, Asynchronous, Four-Layer Collaboration Architecture** anchored in the Rust core (`sase-core`):

```
+------------------------------------------------------------------------------------+
|                      SASE MULTI-AGENT COLLABORATION ARCHITECTURE                   |
+------------------------------------------------------------------------------------+

  [ LAYER 1: TOPOLOGY & ORCHESTRATION ]
  * Supervisor/Worker Fan-In: Coordinator dispatches Clan (%clan:<name>) +
    schedules Synthesizer shell with barrier wait (%wait:clan:<name>)
  * Sequential Relays: Agent Families with Structured Handoff Capsules
  * Cross-Vendor Mentor Review: Bounded 2-turn debate loop (Claude <-> Codex)

  [ LAYER 2: ASYNCHRONOUS MESSAGING (RUST CORE) ]
  * SQLite WAL Store (~/.sase/channels/channels.db)
  * Monotonic Sequence ID + Idempotency Keys + Explicit Subscriptions
  * Bounded Next-Shell Prompt Injection (< 4 KB / 1,000 tokens)
  * Voluntary Tool-Driven In-Turn Reads: `sase channel read/post`

  [ LAYER 3: CONCURRENCY & COLLISION AVOIDANCE ]
  * Advisory File Leases: `sase lease acquire <glob>` (inspired by NTM Agent Mail)
  * Pre-dispatch conflict detection in AXE Runner
  * Host-owned landing queue

  [ LAYER 4: DATA & ARTIFACT BUS ]
  * Heavy Data: Immutable `sase artifact` (Plans, Diffs, Test logs, Reports)
  * Scalar State: Typed `sase var` (Jinja output namespaces for downstream agents)
+------------------------------------------------------------------------------------+
```

---

## 2. Core Architecture Breakdown

### Component A: Asynchronous Family and Clan Channels
- **Storage:** Host-local SQLite database (`~/.sase/channels/channels.db`) in WAL mode with `synchronous=FULL` in `sase-core`, ensuring durable local acceptance independent of transient workspace checkouts.
- **Bounded Delivery:** At shell startup, the runner injects only unacknowledged messages up to a strict **4 KB budget (~1,000 tokens)**. If older unread messages remain, a truncation notice directs the agent to voluntary tool inspection (`sase channel read`).
- **Host-Owned Receipts:** When a turn completes successfully, the host advances the subscriber cursor (`last_acknowledged_seq`). Crashed turns do not advance the cursor, guaranteeing automatic retry replay.
- **Attribution & Provenance:** Strictly separates authenticated human steering from peer agent advice.

### Component B: Structured Handoff Capsules (`sase pipe --capsule`)
- Replaces raw conversation replay (`#fork:<agent>`) with structured handoff summaries containing:
  - Objectives completed and unresolved blockers.
  - Files modified and key diff statistics.
  - Primary artifact references.
  - Explicit directives for the successor shell.
- Reduces prompt overhead across sequential shells by **>= 80%** while preserving critical execution context.

### Component C: Advisory File Reservations (`sase lease`)
- Provides an advisory reservation mechanism: `sase lease acquire "src/auth/**" --duration 30m`.
- The AXE runner inspects planned target files prior to launching Clan members across parallel workspaces. If overlapping file edits are detected, AXE issues conflict warnings or automatically serializes execution to prevent costly Git merge conflicts.

### Component D: Formalized Fan-In & Cross-Vendor Mentor Debate
- **Supervisor/Worker Fan-In:** A supervisor decomposes work and launches a parallel workforce via `%clan:<name>`. A synthesizer shell is parked behind a wait barrier (`%wait:clan:<name>`). Workers emit structured JSON artifacts, which the synthesizer aggregates into a unified landing Patch.
- **Cross-Vendor Mentor Debate:** Extends `MentorConfig` with a `model` field and `max_debate_turns = 2`. This enables pairings such as **Claude-author / Codex-reviewer** in a closed-loop critique-and-fix cycle before final patch acceptance.

---

## 3. Implementation Roadmap

1. **Phase 1 (Weeks 1–3):** SQLite channel store in `sase-core`, bounded next-shell injection (< 4 KB), and host-owned receipt tracking.
2. **Phase 2 (Weeks 4–5):** Structured Handoff Capsules in `/sase_pipe` (`--capsule`).
3. **Phase 3 (Weeks 6–7):** Cross-vendor model pinning and bounded debate loops in `MentorConfig`.
4. **Phase 4 (Weeks 8–9):** Advisory file leases (`sase lease`) and AXE pre-dispatch collision checking.
5. **Phase 5 (Weeks 10–11):** ACE TUI Channels & Leases observability pane.

---

## 4. Deliverables & Provenance

- **Written Report:** [`multi_agent_collaboration_architecture__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_41/sase/repos/research/202609/multi_agent_collaboration_architecture__gem.md)
- **Audited Artifact Registration:**
  ```bash
  sase artifact create -p "/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_41/sase/repos/research/202609/multi_agent_collaboration_architecture__gem.md" -l "research:202609/multi_agent_collaboration_architecture__gem.md"
  ```
  - **Artifact ID:** `explicit:efd5284fcc54f41cf893959a`
  - **Resolution Status:** `exact` (verified via `sase artifact read`)
- **Final Turn Declaration:** Submitted and accepted via `sase final submit` (`commit` obligation satisfied for `sdd:research`).
