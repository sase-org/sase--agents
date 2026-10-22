# Chat History - ace-run (research.4w.mus)

- **TIMESTAMP:** 2026-10-19 07:28:36 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.4w.mus
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261019_071704.md`

## Prompt

%id(mus, clan=research.4w)
%m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 5-researcher swarm.
The other researchers, `research.4w.cdx`, `research.4w.cld`, `research.4w.grk`, `research.4w.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

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

Done. Report written to [hermes_llm_provider_design__mus.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202610/hermes_llm_provider_design__mus.md) and registered as `research:202610/hermes_llm_provider_design__mus.md` (artifact `explicit:84f3c77f66c5f08392480f20`).

Top finding: Hermes should be added as an 8th bundled, opt-in provider (`HermesProvider`, short name `her`) using `hermes chat --oneshot --query-file - --format stream-json` as transport — the only headless mode yielding reply text, tool calls, and token usage over one pipe — with `--yolo --ignore-rules --source tool`, the SASE bundle prepended Muse-style, and `hermes -z --usage-file` kept as fallback. Key evidence: both entry points verified in Hermes source at `8f5693af41` (`hermes_cli/oneshot.py`, `_parser.py`, cli-commands.md); `-z` blinds tool-call telemetry and takes prompts as argv, while the chat path supports stdin prompts and true headless `--resume`. V1 stays out of autodetect and size-alias pools; a Phase 0 live-CLI spike list covers the unverified items (stream-json shapes, version format, failure wording, skill path).

Declaration submitted; report commit authorized.
