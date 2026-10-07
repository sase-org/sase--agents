# Chat History - ace-run (research.0f.gem)

- **TIMESTAMP:** 2026-10-07 15:28:35 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.0f.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261007_151324.md`

## Prompt

%id(gem, clan=research.0f)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.0f.cdx`, `research.0f.cld`, `research.0f.grk`, `research.0f.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I
would like to give sase plans (i.e. tales and epics) the ability to embed sase gate
options within their frontmatter somehow.

- This will be useful, for example, to start requiring that all memory file changes be
  planned in plan files with explicit human gates (that should default to on iff the
  user explicitly requested those memory changes).
- This will also be useful if, for example, a sase agent has a question for the user
  that effects the plan but the agent has enough information to write a good plan
  without an immediate answer (i.e. the coder agent can implement the plan based on what
  gate selections the user made).
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

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

# Research Summary: Embedding Gate Options in SASE Plan Frontmatter

**Researcher:** `gem` (5-Researcher Swarm)  
**Report File:** [`plan_frontmatter_embedded_gate_options__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/plan_frontmatter_embedded_gate_options__gem.md)  
**Durable Artifact Label:** `research:202610/plan_frontmatter_embedded_gate_options__gem.md` (`file:explicit:86a700c07fdc37fef0a91d81`)

---

## 1. Executive Verdict & Concept Critique

### Is this a good idea?
**Yes, with specific architectural boundaries.**

Under SASE's current single-turn model, planners face a sharp and often costly dilemma:
1. **The `/sase_questions` detour**: When a planning agent identifies questions for the user or proposes modifying SASE memory files without prior explicit instruction, it must call `/sase_questions`. This immediately kills the agent via SIGTERM, generates a question gate turn, blocks on user input, and then respawns an entirely new planning agent. This is high-latency, costs double the LLM turns, and forces the user to answer questions in isolation without seeing the full implementation plan.
2. **All-or-nothing plan approval**: When `sase plan propose` is called, the reviewer can approve (launch coder / commit plan) or reject/feedback, but cannot toggle optional scope items or selectively authorize sensitive side-effects (like modifying `sase/memory/` notes).

Embedding declarative **gate options** directly in plan frontmatter eliminates this friction by unifying plan presentation and human-in-the-loop decision-making into a single review step.

### Risks and Adjustments to Requirements
- **Risk 1: "Choose-Your-Own-Adventure" Plan Dilution**: Gate options should be used for **policy authorizations (e.g. memory changes)**, **scope toggles (e.g. optional CLI flag/hook)**, and **discrete, bounded alternatives**. They must not become a crutch for uncommitted, vague plans where the agent does not know what to build. If the architecture is fundamentally unknown, `/sase_questions` before planning remains the right tool.
- **Risk 2: Epic DAG Invalidation Hazard**: In an epic plan, phase beads form a strict DAG (`phases: [...]` with `depends_on`). We **must not** allow gate options to dynamically delete or prune phase beads from the graph at review time, as this risks breaking dependency invariants or creating orphan beads. Instead, gate options must be passed as resolved context to phase workers, allowing conditional phases to adapt or no-op cleanly.
- **Risk 3: Memory Gate Default Gaming**: If an agent sets `default: true` on a memory gate option without the user having asked for it, it bypasses the principle that memory changes require user intent. We require that memory options default to `true` **iff** the initiating turn prompt or bead explicitly instructed memory changes, defaulting to `false` otherwise.

---

## 2. Technical Design & Specification

### 2.1 Frontmatter Schema (`gate_options`)
We propose extending plan frontmatter (validated strictly by `sase-core` in Rust) with a declarative `gate_options:` section:

```yaml
---
tier: tale # or epic
title: Add fast-path verification recipe
goal: Implement just check-fast and document it in CLI memory.
size: medium
gate_options:
  - id: update_memory
    label: "Update SASE memory (sase/memory/cli_rules.md)"
    kind: memory
    default: false
    files:
      - sase/memory/cli_rules.md

  - id: hook_integration
    label: "Install git pre-push hook for fast checks"
    description: "Configures .git/hooks/pre-push to run check-fast automatically."
    type: boolean
    default: true
---
```

#### Supported Fields:
- `id` (`string`, required): Unique identifier matching `^[a-z0-9_]{2,32}$`.
- `label` (`string`, required): Human-facing button text in the gate UI.
- `description` (`string`, optional): Subtitle or tooltip rendered in the modal.
- `type` (`enum`, default `boolean`): Control type (`boolean` checkbox toggle or `choice` radio enum).
- `default` (`bool | str`, required): Initial selection state.
- `kind` (`enum`, default `general`): Semantic category (`general` or `memory`).
- `files` (`list[str]`, conditional): Required when `kind: memory`.

---

## 3. Reviewer Experience & UI/UX

SASE's notification gate architecture already supports AND-group checkbox toggles through `GateBranchControls` and `GateOption`. When `build_plan_approval_gate_spec` creates the gate bundle:
- **Tale query**: `(approve AND commit AND opt_1 AND opt_2) OR reject OR feedback`
- **Epic query**: `(approve AND opt_1 AND opt_2) OR reject OR feedback`

### Textual TUI (`PlanApprovalModal`) Presentation
In the TUI, embedded options render naturally as interactive checkboxes right alongside host actions:

```
┌─ Decision ────────────────────────────────────────────────────────┐
│                                                                   │
│ ┌ Tale: Add fast-path verification recipe ──────────────────────┐ │
│ │                                                               │ │
│ │  Host Actions:                                                │ │
│ │  ☑️ 🚀 Launch coder agent                                      │ │
│ │  ☑️ 💾 Commit plan file to plans sidecar                      │ │
│ │                                                               │ │
│ │  ───────────────────────────────────────────────────────────  │ │
│ │                                                               │ │
│ │  Plan Options:                                                │ │
│ │  ⬜ 📝 Update SASE memory (sase/memory/cli_rules.md)          │ │
│ │     [dim]Authorizes modifying project memory notes[/dim]      │ │
│ │                                                               │ │
│ │  ☑️ ⚙️ Install git pre-push hook for fast checks               │ │
│ │     [dim]Configures .git/hooks/pre-push automatically[/dim]   │ │
│ │                                                               │ │
│ │  [ 1 ✅ Tale (Submit) ]                                       │ │
│ └───────────────────────────────────────────────────────────────┘ │
│                                                                   │
│ [ 2 ❌ Reject ]                                                   │
│ [ 3 💬 Send Feedback ]                                           │
│                                                                   │
│ [e] Edit plan in $EDITOR  [c] Coder options                       │
└───────────────────────────────────────────────────────────────────┘
```

The reviewer navigates with `j`/`k`, toggles checkboxes with `Space`, and presses `1` to submit.

---

## 4. Downstream Execution & Provenance

1. **Resolution Stamping in Plan Sidecar**:
   Before the plan is committed to the `plans` sidecar (`sase/repos/plans/YYYYMM/<plan_name>.md`), the host stamps the human's resolved choices into frontmatter:
   ```yaml
   gate_selections:
     update_memory: false
     hook_integration: true
   ```
   This guarantees that anyone inspecting the plan in git history has full auditability of what was authorized.

2. **Tale Handoff (Coder Successor)**:
   In `prepare_accepted_plan_successor`, the reviewer's choices are injected directly into the coder agent's prompt preamble:
   ```markdown
   The above plan has been reviewed and approved with the following reviewer gate selections:
   - [ ] `update_memory`: Rejected / Skipped (false)
   - [x] `hook_integration`: Approved / Enabled (true)

   Implement the plan strictly according to these selections.
   ```
   If `update_memory` is `false`, any attempt by the coder agent to edit `sase/memory/` is forbidden and rejected by the memory write guard.

3. **Epic Handoff**:
   The epic bead records `gate_selections` in its metadata, and phase workers reference the stamped plan (`@plan:...`) with the explicit choices.

---

## 5. Artifact Snapshot

The full research report was authored and registered as an audited SASE artifact:

- **Source Path:** [`/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/plan_frontmatter_embedded_gate_options__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/plan_frontmatter_embedded_gate_options__gem.md)
- **Label:** `research:202610/plan_frontmatter_embedded_gate_options__gem.md`
- **Artifact ID:** `explicit:86a700c07fdc37fef0a91d81`
- **Snapshot Path:** [`/home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261007151330/plan_frontmatter_embedded_gate_options__gem-c83a2535940e.md`](file:///home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261007151330/plan_frontmatter_embedded_gate_options__gem-c83a2535940e.md)

The finalizer declaration has been successfully submitted and accepted for the `commit` payload covering repository `sdd:research` (`repo-8caa19a02d02`). The host will finalize the commit upon turn completion.
