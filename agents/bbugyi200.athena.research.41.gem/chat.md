# Chat History - ace-run (research.41.gem)

- **TIMESTAMP:** 2026-10-07 14:52:35 EDT
- **MODEL:** agy/gemini-3.8-flash-high
- **AGENT:** research.41.gem
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261007_143606.md`

## Prompt

%id(gem, clan=research.41)
%m:agy/gemini-3.8-flash-high %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.41.cdx`, `research.41.cld`, `research.41.grk`, `research.41.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

The `%auto` directive is the main way that we are able to tune permissions (the ones
that are used in practice at least since real sase agents don't have hard permissions
yet) for a sase agent, but this directive is not very configurable or intuitive to use.
I would like to fix this and make this directive much more powerful.

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

# Research Findings: Evolving the `%auto` Directive and Architecting Agent Permissions in SASE

**Researcher:** `research.41.gem`  
**Report File:** [`auto_directive_and_agent_permissions_architecture__gem.md`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/sase/repos/research/202610/auto_directive_and_agent_permissions_architecture__gem.md)  
**Registered Artifact:** `research:202610/auto_directive_and_agent_permissions_architecture__gem.md` (`file:explicit:d212e88bb6043f48943ea642`)

---

## 1. Executive Summary & Core Critique

The proposal to expand the `%auto` directive into a more powerful mechanism to tune "permissions" is motivated by a very real operational pain point, but **conflates two fundamentally orthogonal architectural concepts**:

1. **Gate Autonomy (Interaction Policy):** When should an agent pause to consult a human operator at notification gates (plans, design questions, hitl)?
2. **Authority & Capabilities (Hard Sandboxing):** What filesystem paths, tools, bash commands, networks, and child agents is the agent mechanically allowed to touch?

### Why `%auto` is Perceived as "Permissions" Today
In SASE, all provider harnesses launch agent CLIs with interactive approval prompts bypassed:
- Claude / Gemini: `--dangerously-skip-permissions`
- Codex: `--dangerously-bypass-approvals-and-sandbox`
- Grok: `--permission-mode bypassPermissions`
- Muse / Qwen: `--yolo`

Because CLI stdin prompts are bypassed to satisfy the **Single-Turn Agent** contract (`decisions:single-turn-agents`), **Notification Gates** (`plan`, `question`, `launch`, `sudo`) are the *sole* checkpoint where an agent halts for human sign-off. Consequently, developers experience `%auto` as a permission toggle: omitting `%auto` forces the agent to stop for permission at plans and questions; including `%auto` lets the agent run autonomously.

However, treating `%auto` as a security permissions system is an architectural anti-pattern. Overloading `%auto` to govern file write access, network boundaries, and command sandboxing creates cognitive dissonance (e.g., what would `%auto(write=false)` even mean semantically?) and provides only **security theater** without true kernel or tool-boundary enforcement.

---

## 2. Key Deficiencies in the Existing `%auto` Directive

Even within its legitimate domain of gate auto-resolution, `%auto` suffers from several critical flaws:

1. **The Blind Question Trap:**
   Bare `%auto` auto-approves plan gates *and* silently answers interactive questions by blindly selecting option index `0` via [`automatic_question_response()`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/src/sase/user_question_actions.py#L403). Users specifying `%auto` to bypass plan approval frequently discover that crucial architectural design questions were silently decided without human input.
2. **Leaky Argument State (`is_auto_approve_active` Bug):**
   In [`src/sase/main/plan_approve_handler.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/src/sase/main/plan_approve_handler.py#L382), `is_auto_approve_active()` treats *any* raw `auto_approve_argument` (including `%auto:epic`) as active global auto-approval. This causes `%auto:epic` to inadvertently trigger question auto-resolution, directly contradicting the documentation in `docs/macros.md:3204`.
3. **Hardcoded Inflexibility on Sensitive Gates:**
   In [`src/sase/notification_gates/adapters.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/src/sase/notification_gates/adapters.py#L499), `launch` gates (spawning subagents) have `auto_policy="forbidden"`. Autonomous orchestrator agents and swarm pipelines cannot auto-approve child agent launches, even when trusted.
4. **Outdated Colon-String Syntax:**
   While modern SASE directives have migrated to structured parenthesized forms (`%queue(capacity=..., priority=...)`, `%hold(hood=..., ttl=...)`), `%auto` remains confined to opaque colon strings (`%auto:plan`, `%auto:epic`).

---

## 3. Recommended Adjustments to Requirements

1. **Decouple Gate Autonomy from Agent Sandboxing:**
   - Keep `%auto` strictly dedicated to **Gate Autonomy** (human-in-the-loop notification gate resolution).
   - Address true hard permissions in an orthogonal **Capability & Sandboxing Plane** (`%caps` or `%sandbox`).
2. **Upgrade `%auto` to Support Granular Gate Policies:**
   - Allow authors to specify per-gate-type automation policies rather than an all-or-nothing switch.
3. **Fix Default Question Behavior:**
   - Bare `%auto` must auto-approve plans by default, but **leave questions interactive** unless the user explicitly opts into question auto-resolution.
4. **Support Intelligent Question Answering:**
   - When question auto-answering is requested, prefer the `(Recommended)` option over naive index `0`.

---

## 4. Recommended Architecture & Solution

### 4.1 Modernizing `%auto` (Gate Autonomy)

#### Syntax Specification
- **Backward Compatible:** `%auto`, `%a`, `%auto:plan`, `%auto:tale`, `%auto:epic` continue to function identically.
- **New Structured Form:** `%auto(...)` with keyword parameters:
  - `plan=` (`p=`): `approve` (default), `tale`, `epic`, `ask`, `reject`
  - `question=` (`q=`): `ask` (new safe default), `first` (legacy), `recommended`, `deny`
  - `launch=` (`l=`): `ask` (default), `approve`, `tribe:<name>`
  - `hitl=`: `ask` (default), `accept`, `deny`
  - `sudo=`: Permanently forbidden (`sudo=approve` raises `DirectiveError`).
- **Shorthand Presets:**
  - `%auto(all)`: Auto-approves plans and auto-answers questions (using `recommended`).
  - `%auto(plans)` / `%auto(plan)`: Auto-approves plans only; questions remain interactive.
  - `%auto(questions)` / `%auto(question)`: Auto-answers questions only; plans remain interactive.
  - `%auto(none)`: Explicitly disables all gate auto-resolution (overrides macros).
  - Composable mixes: `%auto(plan=tale, question=ask)` or `%auto(all, question=ask)`.

#### Engine Changes
1. **`PromptDirectives` Update:** Add `auto_policies: AutoGatePolicies` in [`src/sase/macro/_directive_types.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/src/sase/macro/_directive_types.py).
2. **Paren Parsing:** Add `_collect_auto_paren_args` in [`src/sase/macro/_directive_collect.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/src/sase/macro/_directive_collect.py).
3. **Decouple Gate Check:** Fix `is_auto_approve_active()` in [`src/sase/main/plan_approve_handler.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/src/sase/main/plan_approve_handler.py) so plan-specific arguments no longer leak into question gates.
4. **Adapter Protocol:** Enhance `GateAdapter.resolve_auto_selection(self, spec, policy)` in [`src/sase/notification_gates/adapters.py`](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/src/sase/notification_gates/adapters.py) and allow policy-based auto-resolution for `launch` gates.

### 4.2 The True Permissions Architecture: `%caps` (Capability Sandboxing)

Hard permissions belong in a dedicated capability plane enforced across three mechanical layers:
1. **Layer 1 (Provider Tool Masking):** Strip write tools (`replace_file_content`, `write_to_file`) from CLI invocations for read-only agents using provider flags (e.g. Claude `--disallowedTools`).
2. **Layer 2 (Control Plane Admission):** Enforce `ToolRun` admission and block dangerous commands in `sase tool run`.
3. **Layer 3 (OS/Kernel Namespaces):** Mount ephemeral workspaces `sase_<N>` read-write, mount project roots read-only, mask user credentials (`~/.ssh`, `~/.aws`), and unshare network namespaces (`--unshare-net`) via Bubblewrap (`bwrap`).
4. **Tribe Defaults:** Configure capability profiles in `sase.yml` under `tribes.<tribe>.caps` so research, review, and coding agents receive appropriate least-privilege containment automatically.

---

## 5. Artifact Verification

The detailed architectural report has been written and permanently registered:
- **Report Path:** `/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_33/sase/repos/research/202610/auto_directive_and_agent_permissions_architecture__gem.md`
- **Artifact Label:** `research:202610/auto_directive_and_agent_permissions_architecture__gem.md`
- **Artifact Ref:** `file:explicit:d212e88bb6043f48943ea642`
- **Host Finalizer:** Turn declaration successfully submitted via `sase final submit`.
