# Chat History - ace-run (research.2y.cdx)

- **TIMESTAMP:** 2026-09-30 06:55:08 EDT
- **MODEL:** codex/gpt-5.6-sol
- **AGENT:** research.2y.cdx
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260930_062946.md`

## Prompt

%id(cdx, clan=research.2y)
%m:codex/gpt-5.6-sol@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cdx in a 5-researcher swarm.
The other researchers, `research.2y.cld`, `research.2y.grk`, `research.2y.mus`, `research.2y.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cld.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cdx.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

We currently store
too many prompts in prompt history (see the ~/tmp/screenshots/20260930_062115.png
screenshot for an example of a prompt that likely shouldn't have been stored).

- Namely, prompt history is meant to be used to store user prompts, each of which is
  supposed to correlate with a specific request made by a human being (by using the
  prompt input widget in the TUI or the `sase run` command to launch a sase agent, for
  example).
- Any prompt used to launch agents that belong to an xprompt swarm should not be saved
  to prompt history, but the prompt containing the xprompt swarm invokation
  (`#research_swarm`, for example) which was used by the user to launch the swarm should
  be saved to prompt history.
- Any prompt used to launch agents from routines should not be saved to prompt history.

Can you do some research with the goal of helping me decide the best way to implement
this? Also, critique this plan in general. Is this a good idea? Would you take a
different approach? Make any adjustments to the requirements that you think are
justified but clearly call these out. End your analysis with a recommended solution. 
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

I’m using the repository-access and audited-memory skills first because the report belongs to the linked research repo and its artifact registration has project-specific rules. I’ll inspect the screenshot and trace every prompt-history write path independently, then write and register only my `__cdx.md` report.

The screenshot confirms the noise pattern: one human swarm invocation is followed by many near-empty `+sase` rows whose previews are generated phase prompts. I’m now tracing where history is written versus where swarm/routine prompts are expanded, with special attention to whether provenance already exists and can be used instead of inferring from prompt text.

The code already has the right discriminator: every launch is now tagged `typed` or `generated`, and agent context forcibly downgrades a claimed `typed` launch to `generated`. The current design uses that marker only to protect next-word prediction; prompt history itself still persists and displays both classes. I’m validating the live shard and edge cases before recommending whether to filter, stop writing, or migrate.

I’m also checking the Rust-core boundary because “what belongs in history” is shared domain policy, while the current persistence code is Python. This will determine whether the clean fix is a local write guard or a typed policy carried through the core launch contract.

The live data pinpoints the amplification: at the screenshot’s 01:58 timestamp, one generated nine-segment bead-work bundle produced ten history rows. Across the newest 100 rows, 79 are explicitly marked `generated`, so this is primarily a provenance-policy bug, not a rendering problem. I’m writing the report around a centralized “user-submitted roots only” invariant, including cleanup and regression coverage.

The report is written and passes a whitespace/diff check. I’m now registering the exact file as the requested immutable research snapshot, using its repository-relative label.

Research completed and registered.

- Report: [human_intent_prompt_history__cdx.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19/sase/repos/research/202609/human_intent_prompt_history__cdx.md)
- Durable snapshot: `file:explicit:be723f40ed6745f13d134862`

Core recommendation: record only user-submitted root prompts; centrally reject all `origin="generated"` history writes before placeholder learning or failed-launch stashing. Preserve typed swarm invocations, and conservatively prune only existing rows explicitly marked generated.
