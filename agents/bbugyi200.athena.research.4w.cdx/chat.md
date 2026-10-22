# Chat History - ace-run (research.4w.cdx)

- **TIMESTAMP:** 2026-10-19 07:36:11 EDT
- **MODEL:** codex/gpt-6-astra
- **AGENT:** research.4w.cdx
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261019_071704.md`

## Prompt

%id(cdx, clan=research.4w)
%m:gpt-6-astra %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher cdx in a 5-researcher swarm.
The other researchers, `research.4w.cld`, `research.4w.grk`, `research.4w.mus`, `research.4w.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cld.md` and `__grk.md` and `__mus.md` and `__gem.md`. Your report will end in `__cdx.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to add hermes (see the https://github.com/nousresearch/hermes-agent GitHub repo for
context) as a new, fully supported sase LLM provider. Can you do some research with the
goal of helping me decide the best way to implement this? I believe there is another
research file in the research sidecar repo related to hermes that you should review if you
can find it. End your analysis with a recommended solution. 
Write this research to a new markdown file under the $(sase repo path research --ensure)/$(date +%Y%m)/ directory.
Choose a descriptive filename stem yourself, but the filename MUST end with the
`__cdx` suffix, i.e. `<stem>__cdx.md` (double underscore before the
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

I’ll inspect SASE’s provider contract, Hermes’s interfaces, and any earlier Hermes research, then write an independent report with a recommended implementation and register it as a durable snapshot. I’ll use the `sase_repo` and `sase_memory_read` skills for repository and research access.


SASE already has provider hooks for invocation, model routing, instructions, skills, diagnostics, and usage. I also found earlier Hermes comparisons. I’m checking Hermes’s current execution interfaces to see which can satisfy SASE’s single-turn contract and expose reliable results, tool activity, and failures.


Hermes’s current CLI documents a useful structured stream: initialization, text, tool calls, tool results, usage, and a terminal result with an exit code. Its newer CLI also relies on a gateway, so I’m checking who owns the actual worker and how cancellation behaves before recommending that interface.


The source confirms a significant compatibility issue: both structured chat and `hermes -z` now run through Hermes’s shared gateway, and closing the client leaves accepted work running. SASE’s per-run environment also is not forwarded by default. I’m comparing an adapter-owned gateway with a small supervised Hermes worker; this is more than a stream-parser addition.


There’s an important version split: the `v0.22.2` release tag still constructs the agent in the CLI process, while current `main` routes through the gateway. The release also has native background-completion loops that need constraining. I’m shaping the recommendation around a supervised worker contract, with a pinned CLI prototype to test the integration cheaply.


My recommendation is an official `sase-hermes` provider backed by a small foreground Hermes companion command, with an explicit version contract. That preserves Hermes’s agent loop while letting SASE own the worker lifecycle. The report will also cover the cheaper pinned-CLI prototype, the gaps it leaves, and the tests required before calling the provider fully supported.


The report is written and registered as a durable snapshot. It covers the stable/main lifecycle difference, the recommended provider-and-companion design, and acceptance tests for full support. I’m using `sase_final` now to declare the research-file change for host-owned completion.


Created the independent [research report](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_18/sase/repos/research/202610/hermes_provider_supervised_execution_contract__cdx.md).

Recommendation: an official `sase-hermes` provider with a supervised foreground companion command. The report explains the crucial lifecycle difference between stable Hermes and current main.

Durable snapshot registered: `file:explicit:9c8afbce3d4347dff411e6a2`.
