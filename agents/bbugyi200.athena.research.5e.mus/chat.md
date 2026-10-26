# Chat History - ace-run (research.5e.mus)

- **TIMESTAMP:** 2026-10-26 17:50:53 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.5e.mus
- **PROMPT:** `~/.sase/multi_prompts/202610/gh_sase_org__sase-multiprompt-261026_174150.md`

## Prompt

%id(mus, clan=research.5e)
%m:muse/muse-spark-1.3-contributor@xhigh %q(1.5x, w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 5-researcher swarm.
The other researchers, `research.5e.cdx`, `research.5e.cld`, `research.5e.grk`, `research.5e.gem`, are independently investigating the same request and will write their own self-named reports ending in `__cdx.md` and `__cld.md` and `__grk.md` and `__gem.md`. Your report will end in `__mus.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

There is not nearly enough transparancy about how the load is determined for the current
machine. For example, in the ~/tmp/screenshots/20261026_172751.png screenshot you can
see that there are 6 agents running (from the agent count at the top), but the load is
only at 3/8. This seems like it is probably a mistake/bug (I only see 1 agent that is
running a waiting monitor, so I would expect a load of 5 I think--I'm not sure), but the
bigger problem is that it is very unclear what error we are making right now, if any
(which nodes do not have any weight associated with them, for example).

Can you do some research with the goal of helping me decide on the best UX changes to
make this state clearer and helping to resolve the issues with the way the machine's
load is calculated (if any)? End your analysis with a recommended UX and solutions to
any issues you find with machine load calculations. 
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

Top finding: `load: 3/8` is very likely correct, not a bug — it is 3.0 **weighted capacity units** of an 8-unit local budget, while `6 running` counts **lanes**, and live data shows five RUNNING swarm researchers at 0.25 weight each. The defect is transparency, not arithmetic.

Report written and registered:

- [machine_load_transparency__mus.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_20/sase/repos/research/202610/machine_load_transparency__mus.md) — artifact `explicit:f14f6c9563a7026a801b2eed`, label `research:202610/machine_load_transparency__mus.md`.

Key evidence gathered:

- Gauge = `AgentLoadIndicator` rendering `occupied_capacity / effective_limit` from the Rust `sase_core_rs.runner_capacity_snapshot` over the local roster before fleet projection — so it is athena-local; apollo agents never move it.
- `/8` comes from a live override (`~/.sase/max_running_agents_override.json`, limit 8, source ace), not the configured default 10. Nothing in the UI says so.
- `sase agent list -j` on athena showed the confusion mechanism directly: five RUNNING researchers at explicit 0.25, a TESTING monitor occupying at 1.0, and a WAITING CUTOVER monitor at 0.0. The "subtract 1 for the waiting monitor" mental model fails both ways.
- Biggest UX gap: default-1.0 rows render no weight badge at all, and the only composition view is a hover-only tooltip capped at 12 holders with no exempt-row reasons.

Recommendations in the report, highest value first: render one decimal (`3.0/8`), add a keyboard-openable load breakdown (holders plus running-but-not-holding rows with reasons), mark override-sourced limits, label local scope, and legend the badge silence.

Declaration submitted for the research report commit.
