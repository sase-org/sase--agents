# Chat History - ace-run (research.1x.grk)

- **TIMESTAMP:** 2026-10-17 00:12:49 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** research.1x.grk
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261016_215631.md`

## Prompt

%id(grk, clan=research.1x)
%m:grok/grok-4.6@xhigh %wait:research.1w.linker %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher grk in a 5-researcher swarm.
The other researchers, `research.1x.cdx`, `research.1x.cld`, `research.1x.mus`, `research.1x.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__mus.md` and `__gem.md`. Your report will end in `__grk.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

Can you do some research with the goal of comparing sase with gascity (see recent
research in the research sidecar repo related to gascity and gastown for context)? In
particular, in what ways is gascity superior to sase? End your analysis with a ranked
list of recommended improvements you think I should consider making to sase based on
your report's findings. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__grk` suffix, i.e. `<stem>__grk.md` (double underscore before the
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

I'll start by reading the research and artifact skills, then open the research sidecar for the Gascity/Gastown context.

I'll record skill use, load artifact memory, and open the research sidecar so I can work from audited Gascity/Gastown sources.

The inventory is large, so I’ll isolate the research sidecar and list Gascity/Gastown artifacts next.

Prior Gascity and Gastown reports are in the sidecar. I’ll inventory filenames, open the Gascity source, and read those reports through audited artifact reads.

I’ll read the Gastown-vs-SASE synthesis and Gascity’s own design docs next, then compare those claims to SASE’s architecture.

I’ll verify Gascity’s graph, packs, and orders in source, then map those primitives onto SASE’s workflows, beads, and dispatch.

I’ll pull Gascity’s formula, order, and dashboard code next, then check whether SASE already has counterparts.

I have enough primary-source evidence. Next I’ll write the independent comparison and ranked SASE improvements.

The report is at `research:202610/gascity_vs_sase_factory_advantages__grk.md`. Snapshot: `file:explicit:e9144df43260e5c03f849c0b`.

Gascity is a software factory: a controller compiles a written method into a durable bead graph and drives that graph outside any chat session. SASE is a transaction host: one single-turn agent, host-owned completion, a human as the integration point. Gascity leads wherever unattended configurable graph work is the goal.

The largest Gascity advantages:

1. **Host-executed control over a durable work graph** (formula v2: check, retry, fan-out, drain, finalize). SASE workflows are typed DAGs that die with the executor.
2. **Mechanical "done"** — a script the orchestrator runs, not an agent declaration.
3. **User-authored orders** (cron, event, condition) that fire methods with no human dispatch. SASE’s scheduler is a system plane, not a drop-in order file.
4. **Packs** — TOML plus prompts plus formulas plus orders. SASE plugins are Python; macros are prompts; neither is a full topology.
5. **Ready-work pools** — standing workers claim `bd ready`. SASE pushes a prompt into a new agent and raises a human triage gate for ready tasks.

Steal Gascity’s **control plane**, not its long-lived tmux sessions. Yegge’s August reversal argues against reusable session harnesses; it does not argue against host-owned check/retry/dispatch. That split is already Gascity’s design: the orchestrator executes control beads, agents execute work beads. SASE already has the single-turn worker.

Ranked SASE improvements from the report:

1. Materialize workflows as host-executed bead graphs (formula-v2 analogue).
2. Close a step only when a host-run check passes; respawn on fail-with-budget.
3. User-authored orders on the scheduler.
4. Bounded ready-work pull (opt-in auto-launch under capacity and a daily budget, plus leases).
5. Failure policy as graph data (`retry` / `soft_fail` / `escalate`).
6. Code-free packs (extract research swarm and epic/lander first).
7. Multi-lane mixed-vendor review as a pack.
8. Mail as beads, injected at turn start.
9. Live-turn liveness and a Problems view.
10. Typed HTTP+SSE API as a `sase-core` projection.

Do not copy tmux keystroke injection, an LLM Deacon, Dolt, or an always-on Mayor. The TUI, gates, memory, goals, and artifacts are SASE strengths to keep.
