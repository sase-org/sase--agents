# Chat History - ace-run (research.6g.gem)

- **TIMESTAMP:** 2026-11-25 17:08:39 EST
- **MODEL:** agy/gemini-4-neon-xhigh
- **AGENT:** research.6g.gem
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261125_165222.md`

## Prompt

%id(gem, clan=research.6g)
%m:agy/gemini-4-neon-xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.6g.cdx`, `research.6g.cld`, `research.6g.grk`, `research.6g.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I'm working on filling the ~/bob/sase_blog_zettel.md Obsidian album note in preperation
for writing the blog post that introduces SASE to the world. Can you do some research
with the goal of helping me find / think of any records that should be added to this
album? End your analysis with a ranked list of recommended new records that you think I
should consider adding. 
First run `sase repo open research -r "Write this research report"` and use the path it prints as `<research checkout>`. Write this research to a new markdown file under `<research checkout>/202611/`.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__gem` suffix, i.e. `<stem>__gem.md` (double underscore before the
suffix). Create the report without overwrite: if the exact file already exists, pick a
different stem instead of replacing it.


After the write succeeds, register the report as a durable snapshot:

sase artifact create -p "<absolute-report-path>" -l "research:<repo-relative-report-path>"

Use the report's actual absolute path under the opened research checkout and its path relative to the research repo root
(for example
`research:202609/topic__a.md`),
including any subdirectory the steps above put it in. Do not derive the label from
the current month, the clock, or a guessed name.
Do not pass `--move`; the source stays in the research repo for later reorganization. If
registration itself fails, report that failure — do not report the research task as
fully complete.

## Response

Completed independent research on [sase_blog_zettel.md](file:///home/bryan/bob/sase_blog_zettel.md) and wrote the full report to [sase_blog_zettel_new_records__gem.md](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202611/sase_blog_zettel_new_records__gem.md).

### Artifact Registration
- **Source path:** [sase_blog_zettel_new_records__gem.md](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202611/sase_blog_zettel_new_records__gem.md)
- **Label:** `research:202611/sase_blog_zettel_new_records__gem.md`
- **Artifact ID / Ref:** `explicit:ba3942ceebfc60fed8aae558` (`file:explicit:ba3942ceebfc60fed8aae558`)
- **Stored snapshot:** [sase_blog_zettel_new_records__gem-c122309523d4.md](file:///home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261125165228/sase_blog_zettel_new_records__gem-c122309523d4.md)

### Key Findings
- **8 of 18 sections have zero records:** `gate`, `tools`, `fleet`, `automation`, `plugins`, `how_i_use_sase`, `demos`, and `close`.
- **4 populated sections are missing their load-bearing core thesis:**
  - `the_agent_cli` lacks *"Wrap Agent CLIs, Not Model APIs"* and adapter harness normalization / outage retries.
  - `turn` (literally titled `Turn < Session < Clan < Tribe`) lacks both *"Agents Are Single-Turn"* and the *Session / Clan / Hood / Tribe* taxonomy (and currently holds the Satya Nadella quote, which fits `the_agent_cli` better).
  - `plan` (`🎨 Artifacts`) lacks **Plans, Epics, and Plan Decisions** themselves.
  - `project` (`💾 VCS`) lacks **Ephemeral Numbered Workspaces (`sase_<N>`) & Audited `sase repo open`**.
- **High-leverage uncaptured SASE inventions:** mechanical anti-slop defenses (`sase footprint` + sunset flag beads / `FlagTriage`), reviewed `/sase_sudo` gates, guarded `sase tool` runs + failure-triage witnesses + zero-turn prepared host completion, the `#research_swarm` → `sase-listen` podcast → Bob highlights → epic loop, and deleting the Git agent-import leg (`agents-sync-publish-only`).
- **Scope guardrail:** The album already has 29 seeds (only 1 with a `## Draft`). Adding **Tier 1 (Ranks 1–14)** alone reaches **43 records with zero empty sections** and covers every missing core thesis; Tiers 2 and 3 are optional high-leverage differentiators and `⏭️ Later` candidates.

### Ranked List of Recommended New Records (Summary)

**Tier 1 — Essential Load-Bearing Additions (Ranks 1–14)**
1. **Plan Mode Is Just One Kind of Gate** (`plan_mode_is_a_gate` · `gate`) — Plan mode is one instance of command-backed, hash-verified gates generalizing 12 interaction kinds.
2. **Wrap Agent CLIs, Not Model APIs** (`wrap_agent_clis_not_apis` · `the_agent_cli`) — Wrap existing coding CLIs to inherit lab velocity while owning the durable control plane above them.
3. **Agents Are Single-Turn** (`agents_are_single_turn` · `turn`) — Every run is one provider turn; work that outlives a turn uses mechanical host continuation, never promises to resume.
4. **"Sub-Agent" Doesn't Cut It: Sessions, Clans, Hoods, and Tribes** (`turn_session_clan_tribe_taxonomy` · `turn`) — "Sub-agent" collapses four distinct structures: sequential sessions, parallel clans, dotted hoods, and cross-cutting tribes.
5. **Expensive Commands Are Named Tools, Not Ambient Shell Calls** (`named_tools_and_toolruns` · `tools`) — Project-owned tool catalogs guard raw agent runs, record fingerprints and resource demand, and cap host-wide concurrency.
6. **Deterministic Scripts Propose; The Scheduler Launches** (`scheduler_routines_and_jobs` · `automation`) — Cheap deterministic job scripts watch files, commits, and trackers and emit structured launch proposals instead of always-on LLM loops.
7. **One TUI Over a Private Tailscale Fleet** (`tailnet_fleet_dispatch` · `fleet`) — `%dispatch:<machine>` controls your own multi-machine fleet over Tailscale from one TUI with explicit bootstrap credentials and portable-source preflight.
8. **Keep Core Neutral: Thirteen Plugin Seams and a GitHub-Topic Catalog** (`pluggable_core_and_topic_catalog` · `plugins`) — Keep GitHub, Telegram, Neovim, research, and subcommands out of core via entry points and `topic:sase--plugin` discovery.
9. **The Research Swarm → Podcast → Highlights → Epic Loop** (`research_swarm_to_podcast_loop` · `how_i_use_sase`) — Fanning hard questions out to five frontier labs, listening via `sase-listen`, and feeding highlights into the next plan.
10. **Plans That Outlive the Chat — With Structured Plan Decisions** (`plans_epics_and_plan_decisions` · `plan`) — Version-controlled tales/epics with typed `decisions:` frontmatter (and quote-verified human provenance for memory edits) stamped into the archive and handed mechanically to coders.
11. **Ephemeral Numbered Workspaces and Audited Repo Opens** (`ephemeral_numbered_workspaces` · `project`) — Self-healing pooled `sase_<N>` clones backed by Git alternates, verified rescue snapshots, and audited `sase repo open`.
12. **A Gate Never Blocks an Agent** (`gates_never_block` · `gate`) — Creating a gate stages the handoff, finishes the turn via `/sase_final`, and becomes a non-LLM `--gate` turn holding zero runner slots.
13. **Demo: One Prompt Fans Out Across Competing Frontier CLIs** (`demo_multi_model_fanout` · `demos`) — Visual proof using existing VHS assets showing alternations launching competing frontier CLIs into isolated workspaces on one screen.
14. **I Need Your Help — I'm Out of Tokens** (`out_of_tokens_call_to_action` · `close`) — Candid ~1-user CTA opening SASE's design questions via `type:poll` GitHub issues.

**Tier 2 — High-Leverage Differentiators & Hard-Won Lessons (Ranks 15–23)**
15. **Fighting Slop Mechanically: Sunset Flags and `sase footprint`** (`fighting_slop_mechanically` · `not_ready`)
16. **Spending Different Types of Tokens Deliberately** (`different_types_of_tokens` · `how_i_use_sase`)
17. **Optimal Experience, Not Optimal Performance** (`optimal_experience_not_performance` · `what`)
18. **No Mayor: Deterministic Plumbing Over Agent-Run Orchestration** (`no_mayor_deterministic_plumbing` · `what`)
19. **Inline-Then-Escalate: Monitors and Zero-Model-Turn Prepared Completion** (`inline_then_escalate_monitors` · `tools`)
20. **Triage Annotates; It Never Changes an Exit Code** (`failure_triage_witnesses` · `tools`)
21. **Reviewed Sudo Without Passwordless Root** (`reviewed_sudo_gates` · `gate`)
22. **Adapters Normalize Harnesses — And Survive Provider Outages** (`adapter_normalization_and_outage_retries` · `the_agent_cli`)
23. **Memory Webs, Per-Invocation Bundles, and No Retrieval Before Its Corpus** (`memory_webs_and_corpus_first` · `memory`)

**Tier 3 — Strong Optional Additions & `Later` Candidates (Ranks 24–30)**
24. **Live Fleet Over RPC, History Over Git (Why I Deleted Agent Import)** (`fleet_live_vs_publish_only_archive` · `fleet`)
25. **Telegram as a Zero-UI Mobile Frontend (And Why a Native App Still Matters)** (`telegram_as_mobile_plugin` · `plugins`)
26. **Python for the Cockpit, Rust for the Engine Room** (`rust_core_boundary` · `what`)
27. **Agent Hijack: Stop a Runaway Agent Without Throwing Away Its Work** (`agent_hijack_and_recovery` · `turn`)
28. **No Weasels; Just Work** (`no_weasels_just_work` · `close`)
29. **Built for an Audience of One (Rough Edges and Honest Limits)** (`audience_of_one_rough_edges` · `not_ready`)
30. **Demo: Plan Gate → Approved Epic → Parallel Waves** (`demo_gate_to_epic_waves` · `demos`)

The report also includes per-record claims, evidence/notes seeds, album hygiene fixes (including updated live stats of `17,235` commits / `~3.39M` lines), deliberate exclusions honoring your 2026-11-22 cancellations in [sase_blog_annotations.md](file:///home/bryan/bob/sase_blog_annotations.md), and a dry-run `bob capture` starter batch for Tier 1.
