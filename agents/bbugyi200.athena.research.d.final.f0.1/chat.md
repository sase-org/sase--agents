# Chat History - ace-run (research.d.final.f0.1--0)

- **TIMESTAMP:** 2026-07-16 14:27:46 EDT
- **AGENT:** research.d.final.f0.1--0

## Prompt

%name:research.d.final.f0.1
#gh:gh_sase-org__sase #fork:research.d.final Can you use your /sase_questions skill to ask me all of the design questions proposed by the previous agent and then help me implement this functionality by designing the required work using your /sase_plan skill?

## Response

%xprompts_enabled:false
### Questions and Answers

#### Q1: Family meaning

> What should “family” mean going forward, especially for ChangeSpec identity and the distinction between lifecycle phases and peer agents?

- [x] **Run group + lifecycle subtype (Recommended)** — Family means a general group; plan/QA/code phases are a controller-managed subtype that may share one ChangeSpec, while peer groups use explicit policies.
- [ ] **Peer group only** — Family means independent peers; the current phases-of-one-CL mechanism gets a separate product name and UI concept.
- [ ] **CL phases only** — Family retains its current lifecycle meaning; generic peer grouping remains a separate mechanism such as hoods.

#### Q2: Group identity

> May group membership become explicit persisted metadata, and what should own the authoritative aggregate state?

- [x] **Durable group record (Recommended)** — Persist authoritative group_id/node_id plus a synthetic group record; names and parent timestamps become compatibility/display projections.
- [ ] **Metadata, no group record** — Persist group_id/node_id on nodes but derive aggregate state from member records whenever it is needed.
- [ ] **Concrete root authoritative** — Keep one executable root row as the authoritative family record and attach all other members beneath it.

#### Q3: Workspaces

> What workspace and environment semantics should parallel members receive, including an update command whose effects later verifier agents must observe?

- [x] **Explicit per-node policy (Recommended)** — Nodes declare shared, isolated, or read-only access; ordered setup/verify nodes may use a group-owned shared workspace, while parallel writers require isolation or are rejected.
- [ ] **Always isolated** — Every parallel node gets a snapshot-derived workspace and explicit artifacts or commits must carry effects between nodes.
- [ ] **Always shared** — All members use one mutable checkout and environment, accepting synchronization requirements and writer-race risk.

#### Q4: Failures

> What failure semantics must v1 support for dependency edges?

- [x] **Success + terminal edges (Recommended)** — Support after-success and after-terminal/finally; failed prerequisites deterministically skip or cancel dependents, with retries and on-failure branches deferred.
- [ ] **Full failure control** — Also include on-failure branches, retry policies, and manual override or resume behavior in v1.
- [ ] **Success-only** — Keep only successful completion dependencies for v1 and leave failed dependents waiting or manually managed.

#### Q5: Scheduler

> Is a durable host-side compiled graph scheduler acceptable, and which Markdown workflow class must milestone 1 express?

- [x] **Static graph first (Recommended)** — Build the durable scheduler, ship static joins and update-then-verify first, and retain YAML adapters for conditionals such as fix_just.
- [ ] **Conditionals in milestone 1** — Build the scheduler and require fix_just-class output-driven conditional branches in the first Markdown milestone.
- [ ] **YAML remains controller** — Do not introduce a host graph scheduler yet; Markdown swarms delegate all deterministic control flow to YAML workflows.

#### Q6: Executable MD

> What executable-Markdown trust model and directive syntax should v1 use, including the proposed %name(wait=...) argument?

- [x] **Explicit nodes + edges (Recommended)** — Require an explicit command node kind/capability and LaunchApproval preview; allow shell plus registered Python helpers; use %wait edges and a separate workspace policy, not %name(wait=...).
- [ ] **Inline Python + name sugar** — Keep explicit executable nodes and previews, allow inline Python, and support %name(wait=...) as sugar over an edge.
- [ ] **Executable fences** — Treat designated Markdown code fences as executable with minimal extra declarations and retain %name(wait=...) as the primary sequencing control.

#### Q7: Capacity

> How should script roots and parallel family members participate in capacity limits?

- [ ] **Separate pools + group cap (Recommended)** — Every agent counts against the global LLM limit; bash/python use a separate command pool; groups may also enforce their own concurrency cap.
- [x] **One global pool** — All agent and command nodes consume the same global runner-slot limit.
- [ ] **Children are exempt** — Parallel family members remain exempt from the root-agent limit and script nodes consume no runner capacity.

---

> **Global Note:** Answered via Telegram

%xprompts_enabled:true
