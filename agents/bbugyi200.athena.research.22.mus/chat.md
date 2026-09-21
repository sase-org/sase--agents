# Chat History - ace-run (research.22.mus)

- **TIMESTAMP:** 2026-09-21 15:01:33 EDT
- **MODEL:** muse/muse-spark-1.3-contributor
- **AGENT:** research.22.mus
- **PROMPT:** `~/.sase/multi_prompts/202609/gh_sase_org__sase-multiprompt-260921_132041.md`

## Prompt

%id(mus, clan=research.22)
%m:muse/muse-spark-1.3-contributor@xhigh %q(w=0.25)
#gh:gh_sase-org__sase 
You are researcher mus in a 2-researcher swarm.
The other researcher, `research.22.cld`, is independently investigating the same request and will write its own self-named report ending in `__cld.md`. Your report will end in `__mus.md`.

Conduct your research independently and form your own conclusions. Do NOT attempt to
locate, open, read, or otherwise consult the other researcher's report from this swarm,
even if it becomes available before you finish. Do not obtain that peer's findings
indirectly through its chat transcript, summaries, or requests to the peer. You may
independently use the same external sources, shared input material, and unrelated prior
research. You may check filenames or file existence to avoid overwriting your own
output, but do not inspect the peer's report contents. If you encounter its filename,
leave the report alone. The lead researcher will read every report and synthesize their
findings after you have all finished.

The multi_cli_orchestration_vs_sase.md file in the
research sidecar repo recommended that sase "Add a generic ACP provider plugin.". Can
you do some research with the goal of helping me decide the best way to implement this?
Also, critique this plan in general. Is this a good idea? Would you take a different
approach? Make any adjustments to the requirements that you think are justified but
clearly call these out. End your analysis with a recommended solution. 
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

Done. Research complete and registered.

Report: [202609/generic_acp_provider_plugin__mus.md](/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_36/sase/repos/research/202609/generic_acp_provider_plugin__mus.md) — artifact `file:explicit:c378d814e7663c18061a9041`, final declaration accepted.

Verdict: yes, build it, but reframed. The plan is directionally right and wrong on three load-bearing claims: ACP launch argv is heterogeneous per agent (verified a 15-agent table from the registry checkout — `goose acp` vs `cline --acp` vs `droid exec --output-format acp-daemon`), `usage_update` carries context-window pressure not billing usage (Grok's billing came from a vendor extension, not standard ACP), and cross-process resume — the whole continuity payoff — is agent-dependent and must be spiked, not assumed. Recommended: one shared sync ACP client (full-duplex; the existing probe transport explicitly can't drive a turn) plus one entry point per validated agent on a shared base class, additive alongside natives, no SDK dependency, no Rust changes. I never opened the peer report or the prior-swarm reports; all findings are from first-hand code and checkout reads cited in the report.
