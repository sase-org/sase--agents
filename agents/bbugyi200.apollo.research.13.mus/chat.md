# Chat History - ace-run (research.13.mus)

- **TIMESTAMP:** 2026-10-13 16:38:28 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.13.mus
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261013_162421.md`

## Prompt

%id(mus, clan=research.13)
%m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 5-researcher swarm.
The other researchers, `research.13.cdx`, `research.13.cld`, `research.13.grk`, `research.13.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

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
`__mus` suffix, i.e. `<stem>__mus.md` (double underscore before the
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

Research complete. E3 is launchable now.

E1 (`sase-1gu`) and E2 (`sase-1h3`) are both closed since 2026-10-06. Entry gates hold: 7 days past E1 (gate was 3), parity clean (`render -p`: contract 1×, exit 0), coverage 100% on ordinary purpose with zero shadow errors and warm p95 under 170ms. No E3 cutover bead exists yet. Remaining work is E3.1 spikes by design: Muse still passes `--trust-workspace`, Codex lacks `project_doc_max_bytes=0`, auto-memory still on.

To reconstruct any completed agent's bundle: find `artifacts_dir` via [agent list](file:///home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/src/sase/ace/tui/models/_loaders/_meta_enrichment_filesystem.py), then read `<artifacts>/instructions/NN-<provider>.md` plus `.json` manifest. Check all `NN` files (00 ordinary, 01+ recovery/repair). `agent_meta.json` points at latest; same bytes live at `~/.sase/instructions/bundles/<sha>.md`. Use `sase instructions verify -a AGENT` for intent vs provider session record, and `render -a AGENT` only as a fresh preview. Gate/monitor turns have no manifests; pre-E2 runs use `instruction_snapshot` instead.

Report: [readiness guide](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/e3_explicit_delivery_cutover_readiness__mus.md). Registered as `file:explicit:4588af0981dbf931b9e54217`.
