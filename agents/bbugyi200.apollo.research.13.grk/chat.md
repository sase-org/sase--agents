# Chat History - ace-run (research.13.grk)

- **TIMESTAMP:** 2026-10-13 16:46:29 EDT
- **MODEL:** grok/grok-4.6
- **AGENT:** research.13.grk
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261013_162421.md`

## Prompt

%id(grk, clan=research.13)
%m:grok/grok-4.6@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher grk in a 5-researcher swarm.
The other researchers, `research.13.cdx`, `research.13.cld`, `research.13.mus`, `research.13.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__mus.md` and `__gem.md`. Your report will end in `__grk.md`.

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
am considering launching agents to implement the E3 epic described in the
memory_built_instruction_migration_epics.md file in the research sidecar repo. Can you
do some research with the goal of helping me understand if we are ready for this work?
Also, explain how I would be able to figure out what a given sase agents instruction
bundle's contents looked like (for a completed agent on the "Agents" tab, for example). 
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

I'll start by reading the research workflow, opening the research sidecar, and locating the E3 epic so I can judge readiness independently.

I'll record skill use, open the research sidecar, and pull the memory notes that cover artifacts, generated skills, and agent instruction bundles.

The swarm already assigned me as researcher grk, so I’ll research directly: open the sidecar, read the required memory, and locate the E3 epic.

The research sidecar opened. Next I’ll resolve the E3 epic artifact and pull the glossary terms that define instruction bundles.

The epic file is in the sidecar. I’ll read it through the audited artifact path and inspect how instruction bundles are stored.

The epic file is in. I’ll extract the E3 section and check whether E1/E2 and related beads are already landed.

E1 and E2 are closed. Next I’ll pull the E3 spec, check its entry gates, and map how instruction bundles are stored for completed agents.

E1 and E2 landed about a week ago. I’ll pull the full E3 spec, current flags, and the live instruction CLI next.

I’ll inspect the live `sase instructions` CLI, how completed-agent artifacts store bundles, and whether an E3 plan already exists.

I have this run’s artifacts path. Next I’ll inspect a real shadow bundle and the Agents-tab surfaces that expose it.

I have the evidence. Next I’ll write the readiness report, then register it as a durable artifact.

E3’s **entry gates are met**. The **E3 epic itself has not been created**, so the next step is to write and approve its plan, then launch E3.1.

The report is at `sase/repos/research/202610/e3_explicit_delivery_cutover_readiness__grk.md`, registered as `research:202610/e3_explicit_delivery_cutover_readiness__grk.md` (`file:explicit:c7c8bd12fab5e3cf50ae9f4c`).

**Ready now:** E1 (`sase-1gu`) and E2 (`sase-1h3`) have been closed for a week. Live `sase instructions verify --since 7d` still shows the expected pre-cutover scoreboard (Claude/Codex contract 2×, Muse/Grok home missing, Grok 1× via `--rules`, Claude helpers 0 accepted). Ordinary shadow coverage is N/N with zero errors. `sase instructions render -p` is clean. Grok completed non-research declaration rate recovered from 26% to 74% after the E1 stopgap.

**Missing for a launch:** there is no E3 plan or bead. E3.1 spikes are still open in code (Muse `--trust-workspace`, Claude excludes/auto-memory, Codex `project_doc_max_bytes`). E1/E2 sunset flags were already retired by `sase-1jc.10`; E3 needs **new** per-provider sunset flags. Shadow render is already unconditional and still shadow-only.

**Inspecting a completed agent’s bundle** (E6 TUI cards and `sase instructions show` do not exist yet):

1. `sase agent show NAME` → Artifacts dir (Agents-tab copy target `d` also copies it).
2. Read `$ART/instructions/NN-<provider>.md` and `.json` (immutable copy also at `~/.sase/instructions/bundles/<sha[:2]>/<sha>.md`).
3. `sase instructions verify -a NAME` compares that bundle to what the provider actually loaded.
4. `sase instructions render -a NAME` recompiles from **today’s** memory; stderr reports whether it matches the recorded sha256.

The Agents-tab MEMORY lane `◇ AGENTS.md as launched` row is the native file snapshot, not the compiler bundle. The `a` artifact-files picker does not list instruction files.
