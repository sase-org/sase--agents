# Chat History - ace-run (research.4v.mus)

- **TIMESTAMP:** 2026-10-19 07:23:18 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.4v.mus
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261019_071316.md`

## Prompt

%id(mus, clan=research.4v)
%m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 5-researcher swarm.
The other researchers, `research.4v.cdx`, `research.4v.cld`, `research.4v.grk`, `research.4v.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

I would like to add pi (see the https://github.com/earendil-works/pi GitHub repo for
context) as a new, fully supported sase LLM provider. Can you do some research with the
goal of helping me decide the best way to implement this? I believe there is another
research file in the research sidecar repo related to pi that you should review if you
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

Done. The research task is fully complete.

I wrote [pi_provider_integration__mus.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_16/sase/repos/research/202610/pi_provider_integration__mus.md) (423 lines) and registered it as a durable snapshot (`research:202610/pi_provider_integration__mus.md`, artifact `explicit:58be9316c545669b4e30e379`).

Top finding: pi's `--mode json` transport fits SASE's single-turn contract almost exactly — the OpenCode adapter (`pi.py` + `_subprocess_pi.py` reusing `stream_json_lines`) is the direct template — but exit code 0 is meaningless in pi's JSON mode, so the adapter must derive failure from events (`agent_settled(aborted)`, `auto_retry_end`, error stopReasons). That event-based failure check is the single most important correctness detail.

Recommended solution, phased: Phase 1, JSON-mode provider slice (thin `models.yml` entry + verbatim `--model` pass-through, `none→off` effort mapping, SASE-owned `--session-dir`, no daemon across turns); Phase 2, a `sase-pi` extension loaded via `-e` making contracts mechanical (`sase_final` typed tool with `terminate:true`, one-shot `agent_before_settle` guard, fail-safe `tool_call` block on commits/PRs/raw recipes, root-token helper refusal) plus per-project trust for `-a`; Phase 3, an `observe_pi` for `sase instructions verify` (pi persists full system-prompt sections in session files, so verification can be exact) and a home for pi's priced cost telemetry. Deferred: RPC steering, SASE-native Codemode, adopting pi-ai/Durable. I verified each load-bearing claim against the current trees (pi 1.3.0, SASE 8-provider hook inventory) rather than carrying the prior `sase_for_pi_users` report's claims forward, and noted where it is now stale.

Final declaration accepted for the research repo commit.
