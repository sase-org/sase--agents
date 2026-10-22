# Chat History - ace-run (research.3p.cdx)

- **TIMESTAMP:** 2026-10-05 14:35:21 EDT
- **MODEL:** codex/gpt-6.1-sol
- **AGENT:** research.3p.cdx
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261005_141626.md`

## Prompt

%id(cdx, clan=research.3p)
%m:codex/gpt-6.1-sol@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cdx in a 5-researcher swarm.
The other researchers, `research.3p.cld`, `research.3p.grk`, `research.3p.mus`, `research.3p.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cld.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cdx.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to migrate all existing agent instruction files to use sase's memory files
dynamically to contruct instructions for each sase agent right before launching that
agent.

- I've already done some research on this. Review the sase_md_instruction_delivery.md,
  instruction_bundles_provider_parity_and_memory_ledger.md, and
  fresh_clone_bootstrap_and_native_subagent_instructions.md files in the research
  sidecar repo for context before performing your own research. I agree with all of the
  recommendations made in these research files for the most part, but you should call
  out any issues that you are able to identify.
- I think I want to split this work up into multiple epics with clear completion/exit
  criteria and verifiable results that are easy for me to confirm, but I'm not sure how
  this work should be split up or if it is even advisable to split this work up at all.

Can you do some research with the goal of helping me decide the best way to split this
work up (if at all)? End your analysis with a recommended set of epics (with clear
completion/exit criteria and verifiable results) or justification for why you don't
think that I should split up this work. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cdx` suffix, i.e. `<stem>__cdx.md` (double underscore before the
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

I’ll read the three prior reports, trace how SASE builds and delivers agent instructions, and assess where the migration can be split into independently verifiable epics. I’ll use the repository, artifact, and memory skills and keep this research independent of the other swarm reports.


The prior reports point toward a bundle rendered for each provider invocation, with separate instructions for SASE roots, native helpers, and interactive sessions. I’ll check the current launch paths and migration dependencies, especially which file changes must wait until replacement delivery is proven.


I’m also using the OpenAI Docs skill to verify Codex’s current instruction-loading behavior. The supplied reports disagree about whether project-file loading can be suppressed, and that affects the cutover plan.


A useful split is emerging: establish delivery evidence first, then build and roll out bundles, then retire the old files. I also found a potential gap in the Codex plan: setting the project-document byte limit to zero appears to suppress all project instructions, so it needs an explicit ownership check to preserve foreign repository rules.


I’ll include two corrections in the report: “exactly once” needs to account for the small stub that some providers will still load, and the full TUI ledger should be a separate epic. Immutable receipts and a CLI inspection path can provide enough evidence for the migration without delaying delivery fixes.


The offline Codex probe confirmed that `project_doc_max_bytes=0` removes the project instructions while preserving the global instructions. The shadow-home code also needs care: it currently symlinks existing files, so bundle delivery must create its own regular instruction file and account for any `AGENTS.override.md`.

I’m organizing the recommendation into six epics. Four complete the migration; the other two add the TUI ledger and optional audience tuning.


The report is written, and durable registration is underway. It recommends four epics to complete the migration, followed by separate ledger and audience-tuning epics. Each has exit criteria, a small user-verifiable demonstration, and a rollback boundary.


Durable registration succeeded, and the stored snapshot contains all six epics with exit criteria, review demonstrations, and rollback guidance. I’m using the SASE final-declaration skill to hand the research-sidecar change to the host finalizer.


Created and durably registered the [research report](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/sase/repos/research/202610/dynamic_instruction_migration_epic_boundaries__cdx.md).

It recommends six epics: four complete the migration; two separately add the memory ledger and audience tuning. Each includes clear exit criteria, verifiable demonstrations, and rollback guidance.
