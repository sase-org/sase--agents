# Chat History - ace-run (research.3g.mus)

- **TIMESTAMP:** 2026-10-03 13:37:03 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.3g.mus
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261003_132117.md`

## Prompt

%id(mus, clan=research.3g)
%m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 5-researcher swarm.
The other researchers, `research.3g.cdx`, `research.3g.cld`, `research.3g.grk`, `research.3g.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

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
would like to add support to the Muse LLM provider for streaming its output.

- I'm pretty sure we used to support this but then fixed a related bug which caused Muse
  agent replies to be chunked poorly.
- Unfortunately, I don't think that reply streaming has worked for the Muse provider
  ever since.

Can you do some research with the goal of helping me decide the best way to implement
this? End your analysis with a recommended solution. 
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

Research complete. Report written, registered, and final declaration accepted.

Top finding: the Muse provider already streams — the chunk-coalescing fix did not break forwarding. Live runs against `muse exec` 1.4.2-R4684.1 prove every `run.output.delta` is forwarded immediately to console and `live_reply.md` (e.g. 10%→100% across t=3–10s of a 13.5s run, one timestamped chunk). The "streaming never worked" perception is best explained by CLI-side pacing: the same binary burst 26 deltas in ~40ms for a 950-char reply but spread 430 deltas over 16.7s for a 4561-char reply — short replies always look unstreamed, and no SASE change can fix that.

Recommended solution (in the report): keep the coalesced-chunk design; route Muse console fragments through the Rich console so they coexist with the `Live` timer (the one unverified Muse-specific display risk); document CLI-controlled pacing; add a provider-neutral `on_delta` callback only if API-level streaming is truly wanted.

Report: `202610/muse_provider_streaming__mus.md` in the research repo, registered as artifact `explicit:28c4c5da92c65a01671c15d4`. Existing stream/chunk tests: 18 passed.
