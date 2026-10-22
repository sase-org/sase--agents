# Chat History - ace-run (research.3p.mus)

- **TIMESTAMP:** 2026-10-05 14:26:18 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.3p.mus
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261005_141626.md`

## Prompt

%id(mus, clan=research.3p)
%m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 5-researcher swarm.
The other researchers, `research.3p.cdx`, `research.3p.cld`, `research.3p.grk`, `research.3p.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

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
`__mus` suffix, i.e. `<stem>__mus.md` (double underscore before the
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

Top finding: split the migration into six capability-layered epics (E1–E6), not per-provider epics — full recommendation with exit criteria is in the registered report.

Report: [dynamic_memory_built_instructions_epic_split__mus.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/sase/repos/research/202610/dynamic_memory_built_instructions_epic_split__mus.md) — registered as `research:202610/dynamic_memory_built_instructions_epic_split__mus.md` (`file:explicit:e68c7af79845bf47386c9346`).

Key points: E1 observed-mode receipts + `sase doctor instructions` baseline; E2 renderer + provenance with dual-write (no behavior change); E3 flagged per-provider delivery with compliance metrics; E4 Claude subagent two-slot + root-only guard; E5 stub + sync + home migration as two separate gates; E6 audiences + Rust ledger/TUI last and severable. Stopping points after E1, E3, E5. Notable corrections to prior reports: R7's Codex rationale is falsified (knob exists), Grok file fallback is dead not disfavored, Claude subagent flag needs a version pin, and complement mode must be deleted in E5.

Final declaration accepted; host will commit the research sidecar.
