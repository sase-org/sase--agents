# Chat History - ace-run (research.6e.gem)

- **TIMESTAMP:** 2026-11-25 14:34:14 EST
- **MODEL:** agy/gemini-4-neon-xhigh
- **AGENT:** research.6e.gem
- **PROMPT:** `~/.sase/multi_prompts/202611/gh_sase_org__sase-multiprompt-261125_141135.md`

## Prompt

%id(gem, clan=research.6e)
%m:agy/gemini-4-neon-xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher gem in a 5-researcher swarm.
The other researchers, `research.6e.cdx`, `research.6e.cld`, `research.6e.grk`, `research.6e.mus`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__mus.md`. Your report will end in `__gem.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

The decisions memory web for this project and the bob-cli project is taking up way too
much context for each sase agent. I would like to mitigate this somehow.

- These decisions should probably only be read by planner agents (i.e. agents that use
  the /sase_plan skill). Note, however, that we can not modify the /sase_plan skill
  directly with these instructions since it is used by all sase projects (most of which
  will not have this custom decisions memory web).
- It follows that we should stop rendering the full decisions roster in agent
  instruction bundles.
- The decisions memory is just a specific memory web though, which we should not add
  custom support for, so we need to be able to handle memory webs like this generically
  (i.e. for any memory web we want).
- The best solution I can think of is to configure the decisions memory so it stops
  rendering the roster and instead renders instructions that state that any agent that
  is writing a SASE plan (i.e. invoked the /sase_plan skill) MUST read the decisions
  memory roster. This "decisions memory roster" should be retrievable by running a
  `sase memory` command and should look a lot like the roster that is currently in the
  AGENTS.md file. I'm not sure if we have an appropriate `sase memory` command for this
  yet (if not, you should add one).
- We will need to make sure that we audit this memory web roster read and display it in
  the TUI in the appropriate place.
- As a part of this change, we should update the decisions memories appropriately for
  both of these projects (sase and bob-cli).
- I want you to lead the design on this one. Make sure you design this feature so it is intuitive, reliable, and (last but not least) beautiful!

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
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

Research is complete, registered as a durable artifact, and declared for commit via `/sase_final`.

### Report & Artifact
- **Report:** [deferred_memory_web_rosters__gem.md](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202611/deferred_memory_web_rosters__gem.md)
- **Artifact Ref:** `file:explicit:d205084a03d0bad9f81838b8` (`research:202611/deferred_memory_web_rosters__gem.md`, `artifacts[0]`)
- **Stored Snapshot:** [deferred_memory_web_rosters__gem-867afeecec81.md](file:///home/bryan/.sase/artifacts/agents/gh_sase-org__sase/20261125141141/deferred_memory_web_rosters__gem-867afeecec81.md)

---

### Executive Summary

#### 1. Empirical Baseline
- **Severe bundle bloat, already overflowing Codex in `bob-cli`:**
  - `sase`: `proj.web.decisions` (31 strands) is **8,408 B (~2,102 tok)** — **38.3%** of the 21,972 B Claude instruction bundle. Deferring the roster saves **~7.3 KiB (~33%)**.
  - `bob-cli`: `proj.web.decisions` (77 strands) is **25,641 B (~6,394 tok)** — **69.1%** of the 37,090 B Claude bundle. On Codex (32,768 B cap), `bob-cli` is already **4,516 B over cap** (`37,284 B` uncompacted), forcing `superseded_summaries` compaction on every run. Deferring the roster saves **~24.2 KiB (~65%)** and restores **~19.6 KiB** of Codex headroom with zero compaction.
- **Who actually reads `decisions` (`memory_reads.jsonl`):**
  - `sase` (217 reads across 170 agents): **Researchers 77.9%**, Planners 12.4%, Other 9.7%.
  - `bob-cli` (1,412 reads across 1,055 agents): **Researchers 45.8%**, Planners 26.8%, Other/coders 27.4%.
- **Existing production footgun:** Bare `sase memory read decisions` dumps every strand body (`63.5 KiB` in `sase`, `202.6 KiB` in `bob-cli`). Six+ real `bob-cli` agents accidentally dumped `142–205 KiB` trying to fetch the decisions list/index.

#### 2. Critique & Key Adjustments to the Initial Requirements
The core idea — making roster inlining an orthogonal, generic memory-web capability rather than special-casing `decisions` or `/sase_plan` — is **strongly recommended**, with six justified adjustments:
1. **Broaden the audience beyond `/sase_plan` planners:** Researchers account for 46–78% of real `decisions` reads, and non-plan coders touching decision-governed subsystems need filtered lookups. Descriptor prose should direct **planners (`/sase_plan`) + researchers** to read the full roster, and **non-plan coders** to run filtered roster lookups when changing governed areas.
2. **Strip `<!-- sase:strands -->` from `sase/memory/<web>.md` on disk too** (not only at `AGENTS.md`/bundle render time), eliminating descriptor churn, fixing `sase memory` token accounting, and ensuring live project-over-home scope merges on read.
3. **Add a generic one-line reminder in `/sase_plan` Step 1** (referencing *"any on-demand memory web rosters whose instructions say to consult them when planning"*) — zero project-specific coupling, much higher planner compliance.
4. **Add keyword filtering (`PATTERN`, `-b/--bodies`) to the roster read command** so non-plan agents and large webs (77+ strands) don't pay ~6.4k tokens when they only need 4–8 matching entries.
5. **Fail closed on bare `sase memory read <web>` for `on_demand` webs** (directing agents to `sase memory web read <web>` or `-a/--all-strands`), neutralizing the 200 KiB context-bomb trap.
6. **Plan for the `sase-core` Rust backend boundary first:** `crates/sase_core/src/audit_query.rs` currently enforces `schema_version in 1..=3` and `kind in {"note", "web", "strand"}`, silently dropping any newer audit event from the TUI until `sase-core` is updated and `sase-core-revision.txt` is bumped.

#### 3. Recommended Solution
- **Frontmatter (orthogonal axis):** Add `roster_loading: always | on_demand` (default `always`) alongside `roster: inline | list`. Keep `roster` strictly about presentation format (`inline` vs `list`).
- **CLI surface:**
  - `sase memory web read WEB [PATTERN] [-b] [-f {json,markdown,rich}] [-p REF] -r REASON` — audited agent-facing command outputting the canonical roster (default `markdown`, identical to the current `AGENTS.md` format, with `superseded` / `partly superseded` annotations).
  - Upgrade `sase memory web show WEB [PATTERN]` with `-f markdown | rich` (keeping `table` default for human inspection) and add a `Roster` column to `sase memory web list`.
- **Audit schema (`schema_version = 4`):** Emit `kind = "roster"`, `canonical_path = "roster:<web>"`, `resolved_targets = ["roster:<web>"]`, `blob_oid = git_blob_oid(rendered_markdown_bytes)`, plus optional `filter_pattern`, `filter_bodies`, `roster_matched_count`, and `roster_total_count`. Update `sase-core/crates/sase_core/src/audit_query.rs` and `agent_stats/activity.rs` to accept v4 and `"roster"`.
- **TUI display:**
  - **Agents tab (`SASE CONTEXT → MEMORY` lane):** Show roster reads alongside note/strand reads with `ROSTER_GLYPH = "☰"`, compact label (`roster · 31 decisions` or `roster · 6/77 · "capture"`), live freshness indicator (`≡ now` vs `⟲ roster changed`), and a clickable hint opening a full read report via `write_memory_read_report`.
  - **Memory Panel (`M`):** Add an `ON-DEMAND ROSTER` badge on the card, `Roster: list · on-demand` in metadata, and `Last roster read` / filtered roster preview support.
- **Project migrations (`sase` & `bob-cli`):** Set `roster_loading: on_demand` in both `decisions.md` descriptors, update prose with explicit planner/researcher/coder trigger rules and exact `sase memory web read decisions` commands, regenerate `AGENTS.md`/`CLAUDE.md`, and optionally extract a tiny (~80 tok) `gotchas.md` core note in `bob-cli` for its 3–4 universal coder invariants.

#### 4. Open Decisions Highlighted in the Report
1. **Command verb:** `sase memory web read` (recommended, pairs with `web show`/`web list`) vs `sase memory roster` (shorter).
2. **Generic `/sase_plan` nudge:** Include the one-line project-agnostic reminder in `/sase_plan` Step 1 vs keep `/sase_plan` completely untouched.
3. **Bare-web guard:** Fail closed on `sase memory read <on_demand_web>` with `-a/--all-strands` escape hatch (recommended) vs allow with warning.
4. **Disk vs render-only omission:** Omit `<!-- sase:strands -->` from `sase/memory/<web>.md` on disk (recommended) vs keep the block on disk and strip only during bundle/AGENTS compilation.
